# GUÍA TÉCNICA Y ARQUITECTURA - LTI
**Lean Talent Intelligence - Decisiones Técnicas y Best Practices**

---

## 📋 ÍNDICE
1. [Stack Tecnológico Recomendado](#stack-tecnológico)
2. [Arquitectura del Sistema](#arquitectura-del-sistema)
3. [Decisiones Técnicas por Sprint](#decisiones-por-sprint)
4. [Patrones de Diseño y Best Practices](#patrones-y-best-practices)
5. [Consideraciones de Seguridad](#seguridad)
6. [Performance y Escalabilidad](#performance)
7. [DevOps y Deployment](#devops)
8. [Testing Strategy](#testing)
9. [Monitoreo y Observabilidad](#monitoreo)
10. [Consideraciones Específicas de IA/ML](#ia-ml)

---

## 🛠️ STACK TECNOLÓGICO RECOMENDADO {#stack-tecnológico}

### **Frontend (React Ecosystem)**
```typescript
// Stack Principal
- React 18+ (Hooks, Concurrent Features)
- TypeScript 5+ (Type Safety)
- Vite (Build Tool - más rápido que CRA)
- TailwindCSS + HeadlessUI (Styling)
- React Query/TanStack Query (State Management)
- React Hook Form + Zod (Form Validation)
- React Router v6 (Navigation)

// Librerías Específicas
- React DnD (Drag & Drop para Pipeline)
- Chart.js/Recharts (Visualizaciones)
- React PDF Viewer (Visualización CVs)
- Socket.io-client (Real-time)
```

**Justificación Frontend:**
- **React 18**: Server Components y Concurrent Features para mejor UX
- **TypeScript**: Crítico para aplicaciones con lógica compleja de IA
- **Vite**: Build times 10x más rápidos que Webpack
- **TailwindCSS**: Desarrollo rápido sin comprometer customización

### **Backend (Microservicios Híbridos)**
```python
# Core Services (Node.js)
- Node.js 20+ LTS (Auth, Offers, Collaboration)
- Express.js + TypeScript
- Prisma ORM (Type-safe DB access)
- JWT + Passport.js (Authentication)

# AI/ML Services (Python)
- Python 3.11+ (ML Services)
- FastAPI (Alto performance, async)
- Pydantic (Data validation)
- SQLAlchemy 2.0 (Database ORM)

# Message Queue & Cache
- Redis (Cache + Session Store)
- RabbitMQ (Message Broker)
- Socket.io (Real-time communications)
```

**Justificación Backend:**
- **Node.js para Business Logic**: Ecosystem maduro, mismo lenguaje que frontend
- **Python para IA**: Ecosystem ML/AI superior, librerías especializadas
- **FastAPI**: Performance comparable a Node.js con tipado fuerte

### **Base de Datos (Polyglot Persistence)**
```sql
# Datos Estructurados
- PostgreSQL 15+ (Primary Database)
- Redis (Cache, Sessions, Job Queue)

# Datos No Estructurados
- MongoDB/DocumentDB (Logs, Analytics)
- S3/MinIO (File Storage)

# Vectores para IA
- Pinecone (Managed Vector DB)
- Alternativa: Weaviate (Self-hosted)
```

### **IA/ML Stack**
```python
# Librerías Core
- sentence-transformers (Embeddings)
- scikit-learn (ML tradicional)
- spaCy (NLP)
- transformers (Hugging Face)

# Infraestructura ML
- Docker + GPU Support
- MLflow (Experiment tracking)
- DVC (Data Version Control)
```

---

## 🏗️ ARQUITECTURA DEL SISTEMA {#arquitectura-del-sistema}

### **Patrón Arquitectónico: Microservicios con API Gateway**

```mermaid
graph TB
    subgraph "Client Layer"
        WEB[Web App React]
        MOB[Mobile App Future]
    end
    
    subgraph "API Gateway"
        GATEWAY[NGINX + API Gateway]
    end
    
    subgraph "Business Services"
        AUTH[Auth Service<br/>Node.js]
        CORE[Core ATS Service<br/>Node.js]
        COLLAB[Collaboration Service<br/>Node.js]
    end
    
    subgraph "AI/ML Services"
        AI[AI Service<br/>Python/FastAPI]
        ENRICH[Enrichment Service<br/>Python]
    end
    
    subgraph "Data Layer"
        POSTGRES[(PostgreSQL)]
        REDIS[(Redis)]
        VECTOR[(Vector DB)]
        S3[(File Storage)]
    end
    
    WEB --> GATEWAY
    GATEWAY --> AUTH
    GATEWAY --> CORE
    GATEWAY --> COLLAB
    GATEWAY --> AI
    
    AUTH --> POSTGRES
    CORE --> POSTGRES
    COLLAB --> REDIS
    AI --> VECTOR
    ENRICH --> S3
```

### **Principios Arquitectónicos**

1. **Domain-Driven Design (DDD)**
   - Bounded Contexts por dominio de negocio
   - Agregados para consistencia transaccional
   - Events para comunicación entre dominios

2. **CQRS (Command Query Responsibility Segregation)**
   - Separación de operaciones de lectura/escritura
   - Especialmente crítico para Analytics (US-010, US-011)

3. **Event Sourcing (Parcial)**
   - Solo para Pipeline de candidatos (trazabilidad completa)
   - Estados y transiciones como eventos inmutables

---

## 🚀 DECISIONES TÉCNICAS POR SPRINT {#decisiones-por-sprint}

### **SPRINT 1: Foundation & Core IA**

#### T-001: Sistema de Autenticación (8 SP)
```typescript
// Decisiones Técnicas
- JWT con refresh tokens (security + UX)
- Passport.js strategies (local, future OAuth)
- bcrypt para password hashing
- Rate limiting con express-rate-limit

// Estructura recomendada
interface AuthTokens {
  accessToken: string;  // 15 min expiry
  refreshToken: string; // 7 days expiry
  user: UserProfile;
}

// Best Practice: Middleware de auth
const authenticateToken = (req: Request, res: Response, next: NextFunction) => {
  // Validación JWT + rate limiting
};
```

#### T-002: Dashboard Principal (5 SP)
```typescript
// Decisiones de Estado
- React Query para server state
- Zustand para client state (ligero vs Redux)
- Suspense boundaries para loading states

// Performance Considerations
- Lazy loading de componentes pesados
- Virtualization para listas largas
- Memoization con React.memo
```

#### T-006: Formulario de Aplicación (13 SP)
```typescript
// Upload de archivos
- Multipart uploads para archivos grandes
- Validación de tipos MIME
- Virus scanning con ClamAV
- Compresión automática de imágenes

// Parser de CV
- Apache Tika para extracción texto
- Regex patterns para secciones comunes
- Fallback manual si parsing falla
```

#### T-007: Enriquecimiento Automático (21 SP)
```python
# Arquitectura de Jobs
- Celery + Redis para async processing
- Rate limiting respeta GitHub API limits
- Retry logic con exponential backoff
- Circuit breaker para servicios externos

# Estructura de datos
class EnrichmentResult:
    github_stats: GitHubProfile
    repositories: List[Repository]
    skills_extracted: List[Skill]
    confidence_score: float
```

### **SPRINT 2: Matching Engine & Ofertas**

#### T-008: Algoritmo de Matching MVP (34 SP) - TICKET MÁS COMPLEJO
```python
# Decisiones críticas de Arquitectura ML
class MatchingEngine:
    def __init__(self):
        self.embedder = SentenceTransformer('all-MiniLM-L6-v2')
        self.vector_store = PineconeIndex()
        
    async def calculate_match(self, candidate: Candidate, job: JobOffer) -> MatchResult:
        # 1. Feature extraction
        candidate_vector = await self.create_candidate_embedding(candidate)
        job_vector = await self.create_job_embedding(job)
        
        # 2. Similarity calculation
        similarity = cosine_similarity(candidate_vector, job_vector)
        
        # 3. Business rules adjustment
        adjusted_score = self.apply_business_rules(similarity, candidate, job)
        
        return MatchResult(score=adjusted_score, explanation=self.explain_score())

# Performance crítico: Caching de embeddings
@cached(ttl=3600)  # 1 hora cache
async def create_candidate_embedding(self, candidate: Candidate):
    # Embedding solo si perfil cambió
    pass
```

**Consideraciones Específicas T-008:**
- **Latencia objetivo**: <500ms para matching
- **Batch processing**: Para recalcular scores en ofertas actualizadas
- **A/B Testing**: Framework para probar algoritmos
- **Explainability**: Logs detallados de por qué un score es X

#### T-003 & T-005: Gestión de Ofertas
```typescript
// State Management para ofertas
interface OfferState {
  offers: Offer[];
  filters: OfferFilters;
  pagination: PaginationState;
  selectedOffer: Offer | null;
}

// Optimistic updates
const useOfferMutations = () => {
  return useMutation({
    mutationFn: updateOffer,
    onMutate: (variables) => {
      // Update UI immediately
      queryClient.setQueryData(['offers'], oldData => 
        updateOfferInList(oldData, variables)
      );
    },
    onError: (error, variables, context) => {
      // Revert on error
      queryClient.setQueryData(['offers'], context.previousOffers);
    }
  });
};
```

### **SPRINT 3: UX/UI & Pipeline**

#### T-009: Interfaz de Criba Inteligente (13 SP)
```typescript
// Virtualization para listas grandes
import { FixedSizeList } from 'react-window';

const CandidateList = ({ candidates }: { candidates: Candidate[] }) => {
  return (
    <FixedSizeList
      height={600}
      itemCount={candidates.length}
      itemSize={120}
      itemData={candidates}
    >
      {CandidateRow}
    </FixedSizeList>
  );
};

// Infinite scroll con React Query
const useCandidates = (filters: CandidateFilters) => {
  return useInfiniteQuery({
    queryKey: ['candidates', filters],
    queryFn: ({ pageParam = 0 }) => fetchCandidates(filters, pageParam),
    getNextPageParam: (lastPage) => lastPage.nextCursor,
  });
};
```

#### T-010: Vista Kanban del Pipeline (13 SP)
```typescript
// React DnD para drag & drop
import { DndProvider, useDrag, useDrop } from 'react-dnd';

const CandidateCard = ({ candidate }: { candidate: Candidate }) => {
  const [{ isDragging }, drag] = useDrag({
    type: 'candidate',
    item: { id: candidate.id, currentStage: candidate.stage },
    collect: (monitor) => ({
      isDragging: monitor.isDragging(),
    }),
  });

  return <div ref={drag} className={isDragging ? 'opacity-50' : ''}></div>;
};

// Optimistic updates para UX fluida
const moveCandidateToStage = async (candidateId: string, newStage: PipelineStage) => {
  // Update UI immediately
  updateCandidateStageOptimistically(candidateId, newStage);
  
  try {
    await apiClient.moveCandidateToStage(candidateId, newStage);
  } catch (error) {
    // Revert and show error
    revertCandidateStage(candidateId);
    showErrorToast('Failed to move candidate');
  }
};
```

---

## 🎯 PATRONES DE DISEÑO Y BEST PRACTICES {#patrones-y-best-practices}

### **Backend Patterns**

#### 1. Repository Pattern
```typescript
// Abstracción de acceso a datos
interface CandidateRepository {
  findById(id: string): Promise<Candidate | null>;
  findByFilters(filters: CandidateFilters): Promise<PaginatedResult<Candidate>>;
  save(candidate: Candidate): Promise<Candidate>;
  delete(id: string): Promise<void>;
}

class PostgresCandidateRepository implements CandidateRepository {
  constructor(private db: PrismaClient) {}
  
  async findById(id: string): Promise<Candidate | null> {
    const candidate = await this.db.candidate.findUnique({
      where: { id },
      include: { applications: true, enrichmentData: true }
    });
    return candidate ? this.toDomain(candidate) : null;
  }
}
```

#### 2. Command Pattern para Operaciones Complejas
```typescript
// Para operaciones que requieren múltiples pasos
interface Command {
  execute(): Promise<void>;
  undo(): Promise<void>;
}

class MoveCandidateThroughPipelineCommand implements Command {
  constructor(
    private candidateId: string,
    private fromStage: PipelineStage,
    private toStage: PipelineStage,
    private eventBus: EventBus
  ) {}

  async execute(): Promise<void> {
    // 1. Validate transition
    // 2. Update candidate
    // 3. Emit event
    // 4. Send notifications
  }

  async undo(): Promise<void> {
    // Revert all changes
  }
}
```

#### 3. Event-Driven Architecture
```typescript
// Para comunicación entre servicios
interface DomainEvent {
  aggregateId: string;
  eventType: string;
  occurredOn: Date;
  payload: any;
}

class CandidateMovedToInterviewEvent implements DomainEvent {
  constructor(
    public aggregateId: string,
    public payload: { candidateId: string; jobOfferId: string; stage: string }
  ) {
    this.eventType = 'CandidateMovedToInterview';
    this.occurredOn = new Date();
  }
}

// Event handlers
class NotificationEventHandler {
  handle(event: CandidateMovedToInterviewEvent): Promise<void> {
    // Send email to hiring manager
    // Create in-app notification
    // Update collaboration system
  }
}
```

### **Frontend Patterns**

#### 1. Custom Hooks para Lógica Reutilizable
```typescript
// Abstrae lógica compleja del componente
const useMatchingScore = (candidateId: string, jobOfferId: string) => {
  return useQuery({
    queryKey: ['matching-score', candidateId, jobOfferId],
    queryFn: () => aiService.calculateMatchingScore(candidateId, jobOfferId),
    staleTime: 5 * 60 * 1000, // 5 minutes
    retry: 3,
  });
};

const useCandidatePipelineActions = (candidateId: string) => {
  const queryClient = useQueryClient();
  
  const moveToStage = useMutation({
    mutationFn: (stage: PipelineStage) => 
      candidateService.moveToStage(candidateId, stage),
    onSuccess: () => {
      queryClient.invalidateQueries(['candidates']);
      queryClient.invalidateQueries(['pipeline']);
    },
  });

  return { moveToStage };
};
```

#### 2. Error Boundaries Especializados
```typescript
class AIServiceErrorBoundary extends React.Component {
  state = { hasError: false, error: null };

  static getDerivedStateFromError(error: Error) {
    // AI failures shouldn't crash the app
    return { hasError: true, error };
  }

  componentDidCatch(error: Error, errorInfo: React.ErrorInfo) {
    // Log to monitoring service
    logger.error('AI Service Error', { error, errorInfo });
  }

  render() {
    if (this.state.hasError) {
      return <AIServiceFallback onRetry={() => this.setState({ hasError: false })} />;
    }

    return this.props.children;
  }
}
```

---

## 🔒 CONSIDERACIONES DE SEGURIDAD {#seguridad}

### **Autenticación y Autorización**
```typescript
// JWT Security Best Practices
const JWT_CONFIG = {
  accessTokenExpiry: '15m',
  refreshTokenExpiry: '7d',
  algorithm: 'RS256', // Asymmetric keys
  issuer: 'lti-platform',
  audience: 'lti-users'
};

// Role-based access control
enum Permission {
  VIEW_CANDIDATES = 'view:candidates',
  MANAGE_OFFERS = 'manage:offers',
  VIEW_ANALYTICS = 'view:analytics',
  ADMIN_USERS = 'admin:users'
}

const hasPermission = (user: User, permission: Permission): boolean => {
  return user.role.permissions.includes(permission);
};
```

### **Data Protection**
```typescript
// PII Encryption
class EncryptionService {
  private readonly algorithm = 'aes-256-gcm';
  
  encrypt(text: string): { encrypted: string; iv: string; tag: string } {
    const iv = crypto.randomBytes(16);
    const cipher = crypto.createCipher(this.algorithm, process.env.ENCRYPTION_KEY!);
    // Implementation...
  }
}

// Database level encryption for sensitive fields
const candidateSchema = {
  email: { type: 'varchar', encrypted: true },
  phone: { type: 'varchar', encrypted: true },
  cv_content: { type: 'text', encrypted: true }
};
```

### **API Security**
```typescript
// Rate limiting por endpoint
const rateLimits = {
  '/api/auth/login': { max: 5, window: '15m' },
  '/api/candidates': { max: 100, window: '1h' },
  '/api/ai/match': { max: 50, window: '1h' }, // Costoso computacionalmente
};

// Input validation con Zod
const createOfferSchema = z.object({
  title: z.string().min(5).max(100),
  description: z.string().min(50).max(5000),
  requirements: z.array(z.string()).max(20),
  // XSS protection built-in
});
```

---

## ⚡ PERFORMANCE Y ESCALABILIDAD {#performance}

### **Database Optimization**
```sql
-- Índices críticos para queries frecuentes
CREATE INDEX CONCURRENTLY idx_applications_job_offer_id_status 
ON applications (job_offer_id, status_pipeline) 
WHERE status_pipeline != 'archived';

CREATE INDEX CONCURRENTLY idx_candidates_ai_score 
ON applications (ai_match_score DESC) 
WHERE ai_match_score IS NOT NULL;

-- Particionado para tabla de eventos (audit log)
CREATE TABLE pipeline_events_2024 PARTITION OF pipeline_events
FOR VALUES FROM ('2024-01-01') TO ('2025-01-01');
```

### **Caching Strategy**
```typescript
// Cache layers
interface CacheStrategy {
  // Level 1: Application cache (Redis)
  candidateProfile: { ttl: '1h', key: 'candidate:{id}' };
  matchingScores: { ttl: '30m', key: 'match:{candidateId}:{jobId}' };
  
  // Level 2: CDN cache
  staticAssets: { ttl: '1y' };
  cvFiles: { ttl: '1d' };
  
  // Level 3: Browser cache
  userPreferences: { storage: 'localStorage' };
  recentSearches: { storage: 'sessionStorage' };
}

// Cache invalidation patterns
const invalidateCandidateCache = async (candidateId: string) => {
  await redis.del(`candidate:${candidateId}`);
  await redis.del(`match:${candidateId}:*`); // Pattern deletion
  
  // Notify other services
  eventBus.emit('candidate-updated', { candidateId });
};
```

### **Asynchronous Processing**
```python
# Job queue para operaciones pesadas
from celery import Celery

app = Celery('lti-worker')

@app.task(bind=True, max_retries=3)
def enrich_candidate_profile(self, candidate_id: str):
    try:
        # GitHub API calls
        # CV parsing
        # Skill extraction
        pass
    except Exception as exc:
        # Exponential backoff retry
        raise self.retry(exc=exc, countdown=60 * (2 ** self.request.retries))

@app.task
def recalculate_all_matching_scores(job_offer_id: str):
    # Batch process when job requirements change
    candidates = get_candidates_for_job(job_offer_id)
    
    for candidate in candidates:
        calculate_matching_score.delay(candidate.id, job_offer_id)
```

### **Frontend Performance**
```typescript
// Code splitting por rutas
const CandidateListPage = lazy(() => import('./pages/CandidateListPage'));
const AnalyticsPage = lazy(() => import('./pages/AnalyticsPage'));

// Bundle analysis
// webpack-bundle-analyzer para identificar bloat

// Performance monitoring
import { getCLS, getFID, getFCP, getLCP, getTTFB } from 'web-vitals';

getCLS(console.log);
getFID(console.log);
getFCP(console.log);
getLCP(console.log);
getTTFB(console.log);
```

---

## 🚀 DEVOPS Y DEPLOYMENT {#devops}

### **Containerización**
```dockerfile
# Multi-stage build para frontend
FROM node:20-alpine AS frontend-builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build

FROM nginx:alpine AS frontend
COPY --from=frontend-builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

# Backend services
FROM node:20-alpine AS backend
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### **Docker Compose para Desarrollo**
```yaml
version: '3.8'
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    volumes:
      - ./frontend:/app
      - /app/node_modules
    environment:
      - REACT_APP_API_URL=http://localhost:8000

  backend:
    build: ./backend
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=postgresql://user:pass@postgres:5432/lti
      - REDIS_URL=redis://redis:6379
    depends_on:
      - postgres
      - redis

  ai-service:
    build: ./ai-service
    ports:
      - "8001:8001"
    environment:
      - VECTOR_DB_URL=${PINECONE_API_KEY}
    volumes:
      - ./models:/app/models
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: 1
              capabilities: [gpu]

  postgres:
    image: postgres:15
    environment:
      - POSTGRES_DB=lti
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=pass
    volumes:
      - postgres_data:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    volumes:
      - redis_data:/data
```

### **CI/CD Pipeline**
```yaml
# .github/workflows/deploy.yml
name: Deploy LTI Platform

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run Tests
        run: |
          npm test
          npm run test:e2e
          
  security-scan:
    runs-on: ubuntu-latest
    steps:
      - name: Run Snyk Security Scan
        run: snyk test --severity-threshold=high

  build-and-deploy:
    needs: [test, security-scan]
    runs-on: ubuntu-latest
    steps:
      - name: Build Docker Images
        run: |
          docker build -t lti-frontend ./frontend
          docker build -t lti-backend ./backend
          docker build -t lti-ai ./ai-service
          
      - name: Deploy to AWS ECS
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        run: |
          aws ecs update-service --cluster lti-cluster --service lti-frontend --force-new-deployment
```

---

## 🧪 TESTING STRATEGY {#testing}

### **Pyramid de Testing**
```typescript
// Unit Tests (70%)
describe('MatchingEngine', () => {
  it('should calculate correct similarity score', async () => {
    const engine = new MatchingEngine();
    const result = await engine.calculateMatch(mockCandidate, mockJob);
    
    expect(result.score).toBeGreaterThan(0.8);
    expect(result.explanation).toContain('Python experience');
  });
});

// Integration Tests (20%)
describe('Candidate Application Flow', () => {
  it('should enrich profile after application', async () => {
    const response = await request(app)
      .post('/api/applications')
      .send(mockApplicationData)
      .expect(201);
      
    // Verify async enrichment job was queued
    expect(mockJobQueue.add).toHaveBeenCalledWith('enrichProfile', {
      candidateId: response.body.candidateId
    });
  });
});

// E2E Tests (10%)
describe('Complete Hiring Flow', () => {
  it('should allow hiring manager to create offer and see matched candidates', async () => {
    await page.goto('/offers/new');
    await page.fill('#title', 'Senior ML Engineer');
    await page.fill('#description', 'Looking for ML expert...');
    await page.click('#submit');
    
    await expect(page.locator('.success-message')).toBeVisible();
    
    // Navigate to candidates and verify matching
    await page.goto('/candidates');
    await expect(page.locator('.candidate-card')).toHaveCount(5);
  });
});
```

### **AI/ML Testing Específico**
```python
# Model performance tests
def test_matching_algorithm_accuracy():
    """Test that matching algorithm meets accuracy requirements"""
    test_cases = load_test_dataset()
    
    total_correct = 0
    for candidate, job_offer, expected_match in test_cases:
        predicted_score = matching_engine.calculate_match(candidate, job_offer)
        
        # Binary classification: match > 0.7 is positive
        predicted_match = predicted_score > 0.7
        if predicted_match == expected_match:
            total_correct += 1
    
    accuracy = total_correct / len(test_cases)
    assert accuracy > 0.85, f"Matching accuracy {accuracy} below threshold"

# Performance tests
def test_matching_performance():
    """Ensure matching completes within SLA"""
    start_time = time.time()
    
    score = matching_engine.calculate_match(large_candidate_profile, complex_job)
    
    elapsed = time.time() - start_time
    assert elapsed < 0.5, f"Matching took {elapsed}s, exceeds 500ms SLA"
```

---

## 📊 MONITOREO Y OBSERVABILIDAD {#monitoreo}

### **Logging Strategy**
```typescript
// Structured logging
import winston from 'winston';

const logger = winston.createLogger({
  level: 'info',
  format: winston.format.combine(
    winston.format.timestamp(),
    winston.format.errors({ stack: true }),
    winston.format.json()
  ),
  transports: [
    new winston.transports.File({ filename: 'error.log', level: 'error' }),
    new winston.transports.File({ filename: 'combined.log' }),
  ],
});

// Business metrics logging
logger.info('candidate.matched', {
  candidateId: 'uuid',
  jobOfferId: 'uuid',
  matchingScore: 0.87,
  processingTimeMs: 245,
  algorithmVersion: 'v1.2.3'
});
```

### **Métricas de Aplicación**
```typescript
// Custom metrics para Prometheus
import { Counter, Histogram, Gauge } from 'prom-client';

const matchingRequestsTotal = new Counter({
  name: 'matching_requests_total',
  help: 'Total number of matching requests',
  labelNames: ['status', 'algorithm_version']
});

const matchingDuration = new Histogram({
  name: 'matching_duration_seconds',
  help: 'Duration of matching calculations',
  buckets: [0.1, 0.5, 1, 2, 5]
});

const activeApplications = new Gauge({
  name: 'active_applications_total',
  help: 'Number of active applications in the system'
});

// Usage in code
const timer = matchingDuration.startTimer();
try {
  const result = await calculateMatching(candidate, job);
  matchingRequestsTotal.inc({ status: 'success', algorithm_version: 'v1.2' });
  return result;
} catch (error) {
  matchingRequestsTotal.inc({ status: 'error', algorithm_version: 'v1.2' });
  throw error;
} finally {
  timer();
}
```

### **Health Checks**
```typescript
// Health endpoint con dependencias
app.get('/health', async (req, res) => {
  const checks = await Promise.allSettled([
    checkDatabase(),
    checkRedis(),
    checkVectorDB(),
    checkAIService(),
    checkFileStorage()
  ]);

  const health = {
    status: 'healthy',
    timestamp: new Date().toISOString(),
    services: {}
  };

  let allHealthy = true;
  
  checks.forEach((check, index) => {
    const serviceName = ['database', 'redis', 'vectordb', 'ai', 'storage'][index];
    
    if (check.status === 'fulfilled') {
      health.services[serviceName] = { status: 'healthy', latency: check.value.latency };
    } else {
      health.services[serviceName] = { status: 'unhealthy', error: check.reason.message };
      allHealthy = false;
    }
  });

  if (!allHealthy) {
    health.status = 'degraded';
    return res.status(503).json(health);
  }

  res.json(health);
});
```

---

## 🤖 CONSIDERACIONES ESPECÍFICAS DE IA/ML {#ia-ml}

### **Model Management**
```python
# Versioning de modelos
class ModelVersionManager:
    def __init__(self):
        self.models = {}
        self.current_version = "v1.0.0"
    
    def load_model(self, version: str):
        """Load specific model version"""
        if version not in self.models:
            model_path = f"models/matching_model_{version}.pkl"
            self.models[version] = joblib.load(model_path)
        return self.models[version]
    
    def deploy_model(self, new_version: str):
        """Blue-green deployment for models"""
        # Load new model
        new_model = self.load_model(new_version)
        
        # Run validation tests
        if self.validate_model(new_model):
            self.current_version = new_version
            logger.info(f"Deployed model version {new_version}")
        else:
            raise ValueError(f"Model {new_version} failed validation")

# A/B Testing para algoritmos
class ABTestingEngine:
    def __init__(self):
        self.experiments = {}
    
    def should_use_experimental_algorithm(self, user_id: str, experiment_name: str) -> bool:
        """Determine if user should get experimental algorithm"""
        hash_value = hashlib.md5(f"{user_id}{experiment_name}".encode()).hexdigest()
        return int(hash_value[:8], 16) % 100 < 10  # 10% of users
```

### **Data Pipeline para ML**
```python
# ETL para features de ML
class FeatureExtractor:
    def extract_candidate_features(self, candidate: Candidate) -> FeatureVector:
        """Extract features for ML model"""
        features = {
            # Texto features
            'skills_count': len(candidate.skills),
            'experience_years': self.calculate_experience(candidate.cv),
            'education_level': self.encode_education(candidate.education),
            
            # GitHub features (si disponible)
            'github_stars': candidate.github_stats.total_stars if candidate.github_stats else 0,
            'github_commits': candidate.github_stats.total_commits if candidate.github_stats else 0,
            'primary_language': self.encode_language(candidate.github_stats.primary_language),
            
            # Embeddings (high-dimensional)
            'cv_embedding': self.create_cv_embedding(candidate.cv_text),
            'skills_embedding': self.create_skills_embedding(candidate.skills)
        }
        
        return FeatureVector(features)

# Real-time feature store
class FeatureStore:
    def __init__(self, redis_client):
        self.redis = redis_client
        
    async def get_candidate_features(self, candidate_id: str) -> Dict:
        """Get cached features or compute if needed"""
        cache_key = f"features:candidate:{candidate_id}"
        
        features = await self.redis.get(cache_key)
        if features:
            return json.loads(features)
        
        # Compute features
        candidate = await self.get_candidate(candidate_id)
        features = self.extractor.extract_candidate_features(candidate)
        
        # Cache for 1 hour
        await self.redis.setex(cache_key, 3600, json.dumps(features))
        
        return features
```

### **Monitoring ML Models**
```python
# Model drift detection
class ModelDriftDetector:
    def __init__(self, baseline_data: pd.DataFrame):
        self.baseline_stats = baseline_data.describe()
        
    def detect_drift(self, new_data: pd.DataFrame) -> bool:
        """Detect if input data has drifted from baseline"""
        new_stats = new_data.describe()
        
        drift_detected = False
        for column in self.baseline_stats.columns:
            # Statistical tests for drift
            if column in new_stats.columns:
                baseline_mean = self.baseline_stats.loc['mean', column]
                new_mean = new_stats.loc['mean', column]
                
                # Simple threshold check (more sophisticated: KS test, etc.)
                if abs(baseline_mean - new_mean) / baseline_mean > 0.2:  # 20% change
                    logger.warning(f"Drift detected in feature {column}")
                    drift_detected = True
        
        return drift_detected

# Model performance monitoring
class ModelPerformanceMonitor:
    def track_prediction_accuracy(self, predictions: List[float], actual: List[float]):
        """Track accuracy metrics over time"""
        mse = mean_squared_error(actual, predictions)
        mae = mean_absolute_error(actual, predictions)
        
        # Send metrics to monitoring system
        self.metrics_client.gauge('model.mse', mse)
        self.metrics_client.gauge('model.mae', mae)
        
        # Alert if performance degrades
        if mse > self.threshold_mse:
            self.alert_manager.send_alert(
                f"Model MSE {mse} exceeds threshold {self.threshold_mse}"
            )
```

---

## 🚨 RIESGOS Y MITIGACIONES

### **Riesgos Técnicos Identificados**

| **Riesgo** | **Probabilidad** | **Impacto** | **Mitigación** |
|------------|------------------|-------------|----------------|
| Performance del algoritmo de matching | Alta | Alto | Caching agresivo, optimización de embeddings, A/B testing |
| Dependencia de APIs externas (GitHub) | Media | Medio | Circuit breakers, fallback graceful, rate limiting |
| Escalabilidad de Vector DB | Media | Alto | Sharding, réplicas de lectura, monitoring proactivo |
| Calidad de datos de entrenamiento | Alta | Alto | Validación continua, feedback loops, human-in-the-loop |

### **Plan de Contingencia**
```typescript
// Graceful degradation
class FallbackService {
  async getMatchingScore(candidateId: string, jobId: string): Promise<number> {
    try {
      // Primary: AI-based matching
      return await this.aiService.calculateAdvancedMatch(candidateId, jobId);
    } catch (aiError) {
      logger.warn('AI service unavailable, falling back to rule-based matching');
      
      try {
        // Fallback: Rule-based matching
        return await this.ruleBasedMatcher.calculateMatch(candidateId, jobId);
      } catch (fallbackError) {
        logger.error('All matching services failed');
        
        // Last resort: Return default score with warning
        return 0.5; // Neutral score
      }
    }
  }
}
```

---

## 📚 RECURSOS Y REFERENCIAS

### **Documentación Técnica Recomendada**
- **Arquitectura**: Martin Fowler - "Microservices Patterns"
- **React Performance**: React Profiler, Web Vitals
- **ML Engineering**: "Designing Machine Learning Systems" - Chip Huyen
- **Database**: PostgreSQL Performance Tuning Guide
- **Security**: OWASP Top 10, JWT Best Practices

### **Tools y Librerías Específicas**
```bash
# Monitoring & Observability
npm install @sentry/react @sentry/node
npm install pino winston  # Logging
npm install prom-client    # Metrics

# Performance
npm install loadtest artillery  # Load testing
npm install clinic clinic-doctor  # Node.js performance

# Security
npm install helmet express-rate-limit
npm install snyk  # Vulnerability scanning
```

---

**Documento generado por:** WGO  
**Fecha:** Diciembre 2024  
**Versión:** 1.0  
**Próxima revisión:** Post Sprint 1 Implementation 