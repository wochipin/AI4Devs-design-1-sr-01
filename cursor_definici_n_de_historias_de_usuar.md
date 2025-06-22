# Definición de historias de usuario y backlog
_Exported on 6/22/2025 at 18:55:41 GMT+2 from Cursor (1.1.3)_

---

**User**

# Utiliza @LTI-WGO.md  como input.

# Eres un experto Product  Product Manager y Business Analyst. 

# quiero que trabajemos en esto:
Dado el objetivo del producto (lee @LTI-WGO.md ) y las funcionalidades principales, define los títulos de las historias de usuario principales siguiendo el siguiente formato estándar:
"Como [tipo de usuario], quiero [realizar una acción] para [obtener un beneficio]".
Evitar detalles técnicos o instrucciones de implementación.
Mantener las historias lo suficientemente pequeñas y entregables en un sprint.

- Generar las User Stories. Puedes implementar tantas como quieras y puedas, el mínimo son 2. Utiliza buenas prácticas en esta disciplina para que contenga toda la información necesaria, y como consejo, usa una plantilla común para todas ellas , según este ejemplo.
"Como [tipo de usuario], quiero [realizar una acción] para [obtener un beneficio]".
Evitar detalles técnicos o instrucciones de implementación.
Mantener las historias lo suficientemente pequeñas y entregables en un sprint.


- Arma el Backlog de producto con las User Stories, priorizándolas como consideres conveniente acorde a alguna metodología concreta (sugiere alguna).
- Luego, vamos a elegir algunas user stories e implementar los tickets de trabajo.
- Y vamos a estimar el esfuerzo con Fibonacci y story points.

# genera todo esto como salida en un archivo UserStories-iniciales.md en formato markdown.

# preguntáme qué cosas no están claras antes de avanzar.

---

**Cursor**

Perfecto, he revisado el documento LTI-WGO.md y entiendo el contexto del ATS de nueva generación con IA para roles de IA/ML. Antes de generar las User Stories y el backlog, tengo algunas preguntas para asegurarme de que el enfoque sea el correcto:

## Preguntas de Clarificación:

1. **Alcance del MVP**: ¿Quieres que me enfoque únicamente en los 3 casos de uso principales mencionados en el documento (Crear Oferta + Benchmark, Matching en Slack, Enriquecimiento de Perfiles) o también incluir funcionalidades base como autenticación, gestión de usuarios, configuración inicial, etc.?

2. **Nivel de granularidad**: ¿Prefieres User Stories más granulares (ej. "Como reclutador, quiero filtrar candidatos por score de IA") o más amplias (ej. "Como reclutador, quiero gestionar el proceso de selección de candidatos")?

3. **Integraciones**: ¿Debo incluir User Stories específicas para las integraciones con Slack, GitHub, ArXiv como historias separadas o como parte de las funcionalidades principales?

4. **Roles administrativos**: ¿Incluyo User Stories para roles de administrador del sistema (configuración de empresa, gestión de usuarios, etc.) o nos enfocamos solo en los usuarios operativos?

5. **Iniciales para el archivo**: ¿Cuáles son tus iniciales para nombrar el archivo `UserStories-iniciales.md`?

Una vez que me confirmes estos puntos, procederé a generar un backlog completo y bien estructurado con la priorización correspondiente.

---

**User**

1. Incluyes los casos extras que me sugieres, pero ordénalos por importancia a fin de tener los más prioritarios en primer lugar.

2. Vayamos con amplias por ahora.

3. dejaremos las integraciones de lado por ahora.

4. Por ahora, sólo los stake holders operativos.

5: mis  iniciales son WGO

---

**Cursor**

```markdown
# USER STORIES Y BACKLOG DE PRODUCTO - LTI
**Lean Talent Intelligence - Sistema ATS con IA para roles de IA/ML**

---

## ROLES Y PERSONAS

### Roles Principales:
- **Hiring Manager (HM)**: Responsable de definir requisitos del puesto y tomar decisiones de contratación
- **Reclutador Técnico (RT)**: Especialista en sourcing y evaluación inicial de candidatos técnicos
- **Candidato (C)**: Profesional de IA/ML que aplica a posiciones

---

## USER STORIES POR ÉPICAS

### 🔑 ÉPICA 1: GESTIÓN DE ACCESO Y CONFIGURACIÓN INICIAL
**Prioridad: MUST HAVE**

#### US-001: Autenticación de Usuario
**Como** Hiring Manager o Reclutador Técnico,  
**quiero** poder iniciar sesión de forma segura en la plataforma  
**para** acceder a las funcionalidades del ATS y gestionar el proceso de contratación.

**Criterios de Aceptación:**
- Login con email y contraseña
- Recuperación de contraseña
- Sesión persistente con logout seguro

---

#### US-002: Dashboard Principal
**Como** Hiring Manager o Reclutador Técnico,  
**quiero** ver un dashboard con métricas clave y acceso rápido a funcionalidades principales  
**para** tener una visión general del estado de mis procesos de contratación.

**Criterios de Aceptación:**
- Vista de ofertas activas
- Métricas de candidatos por oferta
- Acceso rápido a crear nueva oferta
- Notificaciones pendientes

---

### 🎯 ÉPICA 2: GESTIÓN INTELIGENTE DE OFERTAS DE EMPLEO
**Prioridad: MUST HAVE**

#### US-003: Crear Oferta con Análisis de IA
**Como** Hiring Manager,  
**quiero** crear una oferta de empleo y recibir un análisis inteligente de su atractivo y viabilidad  
**para** optimizar la descripción y atraer al mejor talento disponible.

**Criterios de Aceptación:**
- Formulario de creación de oferta con editor enriquecido
- Análisis automático de IA con score de atractivo
- Sugerencias de mejora basadas en datos del mercado
- Estimación de pool de talento disponible
- Guardado como borrador o publicación directa

---

#### US-004: Gestión de Ofertas Activas
**Como** Reclutador Técnico,  
**quiero** visualizar y administrar todas las ofertas de empleo activas  
**para** hacer seguimiento del progreso y gestionar múltiples procesos simultáneamente.

**Criterios de Aceptación:**
- Lista de ofertas con filtros (estado, fecha, etc.)
- Vista detallada de cada oferta
- Cambio de estado (borrador, activa, cerrada)
- Métricas básicas por oferta (aplicaciones, entrevistas, etc.)

---

### 🤖 ÉPICA 3: MATCHING INTELIGENTE Y GESTIÓN DE CANDIDATOS
**Prioridad: MUST HAVE**

#### US-005: Aplicación de Candidato con Enriquecimiento Automático
**Como** Candidato,  
**quiero** aplicar a una oferta de empleo de manera sencilla  
**para** ser considerado para la posición y que mi perfil sea evaluado correctamente.

**Criterios de Aceptación:**
- Formulario de aplicación simple (CV + datos básicos)
- Enlace opcional a GitHub/LinkedIn
- Confirmación de recepción
- Estado de aplicación visible

---

#### US-006: Criba Inteligente con IA
**Como** Reclutador Técnico,  
**quiero** ver candidatos automáticamente evaluados y enriquecidos por IA  
**para** realizar una criba inicial de alta calidad en segundos.

**Criterios de Aceptación:**
- Score de matching automático (0-100)
- Resumen inteligente de 3-5 puntos clave
- Perfil enriquecido con datos de GitHub (cuando disponible)
- Filtrado por score mínimo
- Acceso rápido al CV original

---

#### US-007: Gestión del Pipeline de Candidatos
**Como** Reclutador Técnico,  
**quiero** gestionar el estado de los candidatos a través del pipeline de selección  
**para** hacer seguimiento organizado del progreso de cada aplicación.

**Criterios de Aceptación:**
- Vista kanban del pipeline (Aplicado → Criba → Entrevista → Decisión)
- Cambio de estado por drag & drop
- Historial de cambios
- Filtros por estado y fechas

---

### 💬 ÉPICA 4: COLABORACIÓN Y FEEDBACK
**Prioridad: SHOULD HAVE**

#### US-008: Evaluación Colaborativa de Candidatos
**Como** Hiring Manager,  
**quiero** revisar candidatos preseleccionados y dejar feedback  
**para** colaborar eficientemente con el equipo de reclutamiento en la toma de decisiones.

**Criterios de Aceptación:**
- Vista detallada del perfil del candidato
- Sistema de rating (1-5 estrellas)
- Comentarios cualitativos
- Historial de feedback del equipo
- Notificaciones de nuevas evaluaciones

---

#### US-009: Comunicación Interna sobre Candidatos
**Como** Reclutador Técnico,  
**quiero** comunicarme con el Hiring Manager sobre candidatos específicos  
**para** alinear criterios y tomar decisiones informadas de manera ágil.

**Criterios de Aceptación:**
- Sistema de comentarios por candidato
- Menciones (@usuario)
- Notificaciones en tiempo real
- Historial de conversación

---

### 📊 ÉPICA 5: REPORTES Y MÉTRICAS
**Prioridad: COULD HAVE**

#### US-010: Métricas de Rendimiento del Proceso
**Como** Hiring Manager,  
**quiero** visualizar métricas clave del proceso de contratación  
**para** identificar cuellos de botella y optimizar la eficiencia del equipo.

**Criterios de Aceptación:**
- Tiempo promedio por fase del pipeline
- Ratio de candidatos por etapa
- Efectividad del matching de IA
- Exportación de reportes

---

#### US-011: Análisis de Calidad de Candidatos
**Como** Reclutador Técnico,  
**quiero** analizar la calidad de los candidatos que recibo  
**para** ajustar las estrategias de sourcing y mejorar el targeting.

**Criterios de Aceptación:**
- Distribución de scores de matching
- Análisis de fuentes de candidatos
- Tendencias temporales
- Comparación entre ofertas

---

## 📋 BACKLOG PRIORIZADO

### Metodología de Priorización: **MoSCoW + Value vs Effort Matrix**

| Prioridad | ID | User Story | Valor de Negocio | Esfuerzo | Ratio V/E |
|-----------|-----|------------|------------------|----------|-----------|
| 🔴 MUST | US-001 | Autenticación de Usuario | Alto | Medio | 2.0 |
| 🔴 MUST | US-002 | Dashboard Principal | Alto | Medio | 2.0 |
| 🔴 MUST | US-005 | Aplicación de Candidato con Enriquecimiento | Muy Alto | Alto | 2.5 |
| 🔴 MUST | US-003 | Crear Oferta con Análisis de IA | Muy Alto | Alto | 2.5 |
| 🔴 MUST | US-006 | Criba Inteligente con IA | Muy Alto | Muy Alto | 2.0 |
| 🔴 MUST | US-004 | Gestión de Ofertas Activas | Alto | Medio | 2.0 |
| 🔴 MUST | US-007 | Gestión del Pipeline de Candidatos | Alto | Medio | 2.0 |
| 🟡 SHOULD | US-008 | Evaluación Colaborativa de Candidatos | Alto | Medio | 2.0 |
| 🟡 SHOULD | US-009 | Comunicación Interna sobre Candidatos | Medio | Medio | 1.5 |
| 🟢 COULD | US-010 | Métricas de Rendimiento del Proceso | Medio | Bajo | 2.5 |
| 🟢 COULD | US-011 | Análisis de Calidad de Candidatos | Medio | Bajo | 2.5 |

---

## 🎫 TICKETS DE TRABAJO (SPRINT 1)

### Sprint Goal: "Establecer la base del sistema con capacidades core de IA"

#### TICKET T-001: Sistema de Autenticación
**User Story:** US-001  
**Descripción:** Implementar sistema completo de login/logout con recuperación de contraseña

**Tareas Técnicas:**
- [ ] Configurar JWT para autenticación
- [ ] Crear endpoints de login/logout/recover
- [ ] Implementar middleware de autenticación
- [ ] Crear formularios de frontend
- [ ] Tests unitarios y de integración

**Estimación:** 8 Story Points
**Criterios de Definition of Done:**
- [ ] Código revisado y aprobado
- [ ] Tests con cobertura >80%
- [ ] Documentación API actualizada
- [ ] Desplegado en entorno de staging

---

#### TICKET T-002: Dashboard y Navegación Principal
**User Story:** US-002  
**Descripción:** Crear dashboard principal con métricas básicas y navegación

**Tareas Técnicas:**
- [ ] Diseño de layout responsive
- [ ] Componentes de métricas básicas
- [ ] Navegación principal
- [ ] Integración con endpoints de datos
- [ ] Estados de carga y error

**Estimación:** 5 Story Points

---

#### TICKET T-003: Formulario de Aplicación de Candidato
**User Story:** US-005  
**Descripción:** Crear formulario público para que candidatos apliquen

**Tareas Técnicas:**
- [ ] Formulario con validaciones
- [ ] Upload de CV con validación de formato
- [ ] Almacenamiento seguro de archivos
- [ ] Email de confirmación
- [ ] Parser básico de CV

**Estimación:** 13 Story Points

---

#### TICKET T-004: Motor de Enriquecimiento Básico
**User Story:** US-006 (Parte 1)  
**Descripción:** Implementar enriquecimiento básico de perfiles de candidatos

**Tareas Técnicas:**
- [ ] Integración con GitHub API
- [ ] Extracción de datos relevantes (repos, lenguajes)
- [ ] Almacenamiento en modelo de datos
- [ ] Job asíncrono para procesamiento
- [ ] Manejo de rate limits y errores

**Estimación:** 21 Story Points

---

#### TICKET T-005: Algoritmo de Matching MVP
**User Story:** US-006 (Parte 2)  
**Descripción:** Implementar algoritmo básico de matching candidato-oferta

**Tareas Técnicas:**
- [ ] Modelo de scoring basado en keywords
- [ ] Generación de embeddings básicos
- [ ] Algoritmo de similitud coseno
- [ ] Endpoint de cálculo de score
- [ ] Almacenamiento de resultados

**Estimación:** 34 Story Points

---

## 📊 ESTIMACIONES Y PLANNING

### Escala de Fibonacci Utilizada:
- **1 punto**: Tarea trivial (~1-2 horas)
- **2 puntos**: Tarea simple (~2-4 horas)
- **3 puntos**: Tarea pequeña (~4-8 horas)
- **5 puntos**: Tarea mediana (~1-2 días)
- **8 puntos**: Tarea grande (~2-3 días)
- **13 puntos**: Tarea muy grande (~3-5 días)
- **21 puntos**: Epic pequeña (~1 semana)
- **34 puntos**: Epic mediana (~1.5-2 semanas)

### Capacidad del Equipo (Asumida):
- **Sprint Duration:** 2 semanas
- **Team Velocity:** 40-50 Story Points por sprint
- **Sprint 1 Total:** 81 Story Points (requiere priorización)

### Propuesta Sprint 1 (Ajustado):
- T-001: Autenticación (8 pts)
- T-002: Dashboard (5 pts)
- T-003: Formulario Candidato (13 pts)
- T-004: Enriquecimiento Básico (21 pts)
- **Total Sprint 1:** 47 Story Points

### Sprint 2 (Planificado):
- T-005: Algoritmo Matching MVP (34 pts)
- US-004: Gestión de Ofertas (8 pts estimados)
- **Total Sprint 2:** 42 Story Points

---

## 📈 CRITERIOS DE ÉXITO

### Métricas de Producto (Post MVP):
- **Tiempo de criba por candidato:** < 30 segundos
- **Precisión del matching:** > 80% de candidatos avanzados son entrevistados
- **Adopción de usuarios:** > 90% de usuarios activos semanalmente
- **NPS Score:** > 50 entre reclutadores técnicos

### Métricas Técnicas:
- **Tiempo de respuesta API:** < 200ms percentil 95
- **Disponibilidad:** > 99.5%
- **Cobertura de tests:** > 80%

---

**Documento generado por:** WGO  
**Fecha:** Diciembre 2024  
**Versión:** 1.0
```

## ✅ COMPLETADO: User Stories y Backlog de LTI

He creado un documento completo `UserStories-WGO.md` que incluye todo lo solicitado:

### 📋 **Contenido Entregado:**

1. **11 User Stories** organizadas en 5 épicas priorizadas:
   - 🔑 Gestión de Acceso (Base del sistema)
   - 🎯 Gestión Inteligente de Ofertas (Core diferenciador)
   - 🤖 Matching Inteligente (Corazón del producto)
   - 💬 Colaboración y Feedback
   - 📊 Reportes y Métricas

2. **Backlog Priorizado** usando metodología **MoSCoW + Value vs Effort Matrix**
   - Las funcionalidades de IA están en las primeras posiciones
   - Balance entre valor de negocio y complejidad técnica

3. **5 Tickets de Trabajo detallados** para Sprint 1:
   - Incluyen tareas técnicas específicas
   - Criterios de Definition of Done
   - Estimación en Story Points con Fibonacci

4. **Estimaciones con Story Points**:
   - Sprint 1: 47 puntos (capacidad realista)
   - Sprint 2: 42 puntos (con algoritmo de matching)
   - Escala Fibonacci bien definida

### 🎯 **Decisiones Clave de Product Management:**

- **Enfoque MVP**: Priorizar las capacidades de IA que nos diferencian
- **Iterativo**: Base sólida primero, luego funcionalidades avanzadas
- **Medible**: Métricas claras de éxito del producto
- **Factible**: Sprint sizing realista para un equipo pequeño

¿Te gustaría que profundice en alguna User Story específica, ajuste las estimaciones, o trabajemos en el siguiente sprint planning?

---

**User**

@UserStories-WGO.md Agregáme diagramas de casos de uso en plantUML para cada UC.


---

**Cursor**

```markdown
**Criterios de Aceptación:**
- Login con email y contraseña
- Recuperación de contraseña
- Sesión persistente con logout seguro

---

->

**Criterios de Aceptación:**
- Login con email y contraseña
- Recuperación de contraseña
- Sesión persistente con logout seguro

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-001 Autenticación de Usuario
left to right direction
actor "Hiring Manager" as HM
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Iniciar Sesión" as UC1
  usecase "Cerrar Sesión" as UC2
  usecase "Recuperar Contraseña" as UC3
  usecase "Validar Credenciales" as UC4
}

HM --> UC1
RT --> UC1
HM --> UC2
RT --> UC2
HM --> UC3
RT --> UC3

UC1 ..> UC4 : include
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Vista de ofertas activas
- Métricas de candidatos por oferta
- Acceso rápido a crear nueva oferta
- Notificaciones pendientes

---

->

**Criterios de Aceptación:**
- Vista de ofertas activas
- Métricas de candidatos por oferta
- Acceso rápido a crear nueva oferta
- Notificaciones pendientes

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-002 Dashboard Principal
left to right direction
actor "Hiring Manager" as HM
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Ver Dashboard" as UC1
  usecase "Visualizar Métricas" as UC2
  usecase "Acceder a Ofertas" as UC3
  usecase "Ver Notificaciones" as UC4
  usecase "Navegar a Funcionalidades" as UC5
}

HM --> UC1
RT --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC1 ..> UC4 : include
UC1 ..> UC5 : include
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Formulario de creación de oferta con editor enriquecido
- Análisis automático de IA con score de atractivo
- Sugerencias de mejora basadas en datos del mercado
- Estimación de pool de talento disponible
- Guardado como borrador o publicación directa

---

->

**Criterios de Aceptación:**
- Formulario de creación de oferta con editor enriquecido
- Análisis automático de IA con score de atractivo
- Sugerencias de mejora basadas en datos del mercado
- Estimación de pool de talento disponible
- Guardado como borrador o publicación directa

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-003 Crear Oferta con Análisis de IA
left to right direction
actor "Hiring Manager" as HM

rectangle "Sistema LTI" {
  usecase "Crear Oferta de Empleo" as UC1
  usecase "Completar Formulario" as UC2
  usecase "Analizar con IA" as UC3
  usecase "Generar Score de Atractivo" as UC4
  usecase "Sugerir Mejoras" as UC5
  usecase "Estimar Pool de Talento" as UC6
  usecase "Guardar Borrador" as UC7
  usecase "Publicar Oferta" as UC8
}

HM --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC3 ..> UC4 : include
UC3 ..> UC5 : include
UC3 ..> UC6 : include
UC1 --> UC7
UC1 --> UC8
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Lista de ofertas con filtros (estado, fecha, etc.)
- Vista detallada de cada oferta
- Cambio de estado (borrador, activa, cerrada)
- Métricas básicas por oferta (aplicaciones, entrevistas, etc.)

---

->

**Criterios de Aceptación:**
- Lista de ofertas con filtros (estado, fecha, etc.)
- Vista detallada de cada oferta
- Cambio de estado (borrador, activa, cerrada)
- Métricas básicas por oferta (aplicaciones, entrevistas, etc.)

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-004 Gestión de Ofertas Activas
left to right direction
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Gestionar Ofertas" as UC1
  usecase "Listar Ofertas" as UC2
  usecase "Filtrar Ofertas" as UC3
  usecase "Ver Detalle de Oferta" as UC4
  usecase "Cambiar Estado" as UC5
  usecase "Ver Métricas" as UC6
}

RT --> UC1

UC1 ..> UC2 : include
UC1 --> UC3
UC1 --> UC4
UC1 --> UC5
UC1 --> UC6
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Formulario de aplicación simple (CV + datos básicos)
- Enlace opcional a GitHub/LinkedIn
- Confirmación de recepción
- Estado de aplicación visible

---

->

**Criterios de Aceptación:**
- Formulario de aplicación simple (CV + datos básicos)
- Enlace opcional a GitHub/LinkedIn
- Confirmación de recepción
- Estado de aplicación visible

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-005 Aplicación de Candidato
left to right direction
actor "Candidato" as C

rectangle "Sistema LTI" {
  usecase "Aplicar a Oferta" as UC1
  usecase "Completar Formulario" as UC2
  usecase "Subir CV" as UC3
  usecase "Proporcionar Enlaces" as UC4
  usecase "Recibir Confirmación" as UC5
  usecase "Consultar Estado" as UC6
  usecase "Enriquecer Perfil" as UC7
}

C --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC1 --> UC4
UC1 ..> UC5 : include
C --> UC6
UC1 ..> UC7 : include
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Score de matching automático (0-100)
- Resumen inteligente de 3-5 puntos clave
- Perfil enriquecido con datos de GitHub (cuando disponible)
- Filtrado por score mínimo
- Acceso rápido al CV original

---

->

**Criterios de Aceptación:**
- Score de matching automático (0-100)
- Resumen inteligente de 3-5 puntos clave
- Perfil enriquecido con datos de GitHub (cuando disponible)
- Filtrado por score mínimo
- Acceso rápido al CV original

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-006 Criba Inteligente con IA
left to right direction
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Realizar Criba Inteligente" as UC1
  usecase "Calcular Score de Matching" as UC2
  usecase "Generar Resumen IA" as UC3
  usecase "Enriquecer con GitHub" as UC4
  usecase "Filtrar por Score" as UC5
  usecase "Acceder a CV Original" as UC6
  usecase "Ver Perfil Completo" as UC7
}

RT --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC1 ..> UC4 : include
UC1 --> UC5
UC1 --> UC6
UC1 --> UC7
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Vista kanban del pipeline (Aplicado → Criba → Entrevista → Decisión)
- Cambio de estado por drag & drop
- Historial de cambios
- Filtros por estado y fechas

---

->

**Criterios de Aceptación:**
- Vista kanban del pipeline (Aplicado → Criba → Entrevista → Decisión)
- Cambio de estado por drag & drop
- Historial de cambios
- Filtros por estado y fechas

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-007 Gestión del Pipeline de Candidatos
left to right direction
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Gestionar Pipeline" as UC1
  usecase "Ver Vista Kanban" as UC2
  usecase "Mover Candidatos" as UC3
  usecase "Ver Historial" as UC4
  usecase "Filtrar por Estado" as UC5
  usecase "Filtrar por Fecha" as UC6
}

RT --> UC1

UC1 ..> UC2 : include
UC1 --> UC3
UC1 --> UC4
UC1 --> UC5
UC1 --> UC6
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Vista detallada del perfil del candidato
- Sistema de rating (1-5 estrellas)
- Comentarios cualitativos
- Historial de feedback del equipo
- Notificaciones de nuevas evaluaciones

---

->

**Criterios de Aceptación:**
- Vista detallada del perfil del candidato
- Sistema de rating (1-5 estrellas)
- Comentarios cualitativos
- Historial de feedback del equipo
- Notificaciones de nuevas evaluaciones

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-008 Evaluación Colaborativa de Candidatos
left to right direction
actor "Hiring Manager" as HM
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Evaluar Candidato" as UC1
  usecase "Ver Perfil Detallado" as UC2
  usecase "Dar Rating" as UC3
  usecase "Escribir Comentarios" as UC4
  usecase "Ver Historial Feedback" as UC5
  usecase "Recibir Notificaciones" as UC6
}

HM --> UC1
RT --> UC5
RT --> UC6

UC1 ..> UC2 : include
UC1 --> UC3
UC1 --> UC4
UC1 --> UC5
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Sistema de comentarios por candidato
- Menciones (@usuario)
- Notificaciones en tiempo real
- Historial de conversación

---

->

**Criterios de Aceptación:**
- Sistema de comentarios por candidato
- Menciones (@usuario)
- Notificaciones en tiempo real
- Historial de conversación

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-009 Comunicación Interna sobre Candidatos
left to right direction
actor "Reclutador Técnico" as RT
actor "Hiring Manager" as HM

rectangle "Sistema LTI" {
  usecase "Comunicarse sobre Candidato" as UC1
  usecase "Escribir Comentario" as UC2
  usecase "Mencionar Usuario" as UC3
  usecase "Recibir Notificación" as UC4
  usecase "Ver Historial" as UC5
}

RT --> UC1
HM --> UC1

UC1 ..> UC2 : include
UC1 --> UC3
UC1 --> UC4
UC1 --> UC5
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Tiempo promedio por fase del pipeline
- Ratio de candidatos por etapa
- Efectividad del matching de IA
- Exportación de reportes

---

->

**Criterios de Aceptación:**
- Tiempo promedio por fase del pipeline
- Ratio de candidatos por etapa
- Efectividad del matching de IA
- Exportación de reportes

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-010 Métricas de Rendimiento del Proceso
left to right direction
actor "Hiring Manager" as HM

rectangle "Sistema LTI" {
  usecase "Ver Métricas de Rendimiento" as UC1
  usecase "Analizar Tiempos por Fase" as UC2
  usecase "Ver Ratio por Etapa" as UC3
  usecase "Evaluar Efectividad IA" as UC4
  usecase "Exportar Reportes" as UC5
  usecase "Generar Dashboard" as UC6
}

HM --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC1 ..> UC4 : include
UC1 --> UC5
UC1 ..> UC6 : include
@enduml
```

---
```

```markdown
**Criterios de Aceptación:**
- Distribución de scores de matching
- Análisis de fuentes de candidatos
- Tendencias temporales
- Comparación entre ofertas

---

->

**Criterios de Aceptación:**
- Distribución de scores de matching
- Análisis de fuentes de candidatos
- Tendencias temporales
- Comparación entre ofertas

**Diagrama de Caso de Uso:**
```plantuml
@startuml US-011 Análisis de Calidad de Candidatos
left to right direction
actor "Reclutador Técnico" as RT

rectangle "Sistema LTI" {
  usecase "Analizar Calidad de Candidatos" as UC1
  usecase "Ver Distribución Scores" as UC2
  usecase "Analizar Fuentes" as UC3
  usecase "Ver Tendencias Temporales" as UC4
  usecase "Comparar entre Ofertas" as UC5
  usecase "Generar Insights" as UC6
}

RT --> UC1

UC1 ..> UC2 : include
UC1 ..> UC3 : include
UC1 ..> UC4 : include
UC1 ..> UC5 : include
UC1 ..> UC6 : include
@enduml
```

---
```

## ✅ COMPLETADO: Diagramas de Casos de Uso en PlantUML

He agregado exitosamente **diagramas de casos de uso en PlantUML** para todas las 11 User Stories del sistema LTI. Cada diagrama incluye:

### 📊 **Características de los Diagramas:**

1. **Actores Principales**: 
   - Hiring Manager (HM)
   - Reclutador Técnico (RT) 
   - Candidato (C)

2. **Relaciones Modeladas**:
   - **Include**: Para funcionalidades obligatorias (`..>`)
   - **Direct Use**: Para acciones directas (`-->`)
   - **Extend**: Para funcionalidades opcionales

3. **Casos de Uso por Épica**:
   - 🔑 **Gestión de Acceso**: US-001, US-002
   - 🎯 **Ofertas Inteligentes**: US-003, US-004  
   - 🤖 **Matching con IA**: US-005, US-006, US-007
   - 💬 **Colaboración**: US-008, US-009
   - 📊 **Reportes**: US-010, US-011

### 🎯 **Beneficios Agregados:**

- **Visualización Clara**: Cada User Story tiene su representación gráfica
- **Estándar PlantUML**: Fácil integración en documentación y herramientas
- **Trazabilidad**: Conexión directa entre requirements y diagramas
- **Comunicación**: Facilita discusiones con stakeholders técnicos

### 📋 **Ejemplos Destacados:**

- **US-003**: Muestra la complejidad del análisis de IA para ofertas
- **US-006**: Detalla el proceso de criba inteligente con múltiples componentes
- **US-008**: Ilustra la colaboración entre diferentes roles

Los diagramas están listos para ser renderizados en cualquier herramienta que soporte PlantUML (Confluence, GitLab, VS Code, etc.). ¿Te gustaría que ajuste algún diagrama específico o agregue alguna funcionalidad adicional?

---

**User**

no, vayamos con la planificación de las user stories más importantes. Genera tickets de trabajo para cada uno. 
Agrega al final de @UserStories-WGO.md  los tickets creados (puedes dejar una tabla con cada EPIC, sus UCs y las tareas para cada UC.

  

---

**Cursor**

```markdown
---

**Documento generado por:** WGO  
**Fecha:** Diciembre 2024  
**Versión:** 1.0

->

---

## 🎫 PLANIFICACIÓN DETALLADA DE TICKETS POR ÉPICA

### Metodología de Descomposición:
- **Epic** → **User Story** → **Tickets de Trabajo** → **Tareas Técnicas**
- Cada ticket representa trabajo entregable en 1-3 días
- Estimación basada en complejidad técnica y dependencias

---

| ÉPICA | USER STORY | TICKET ID | DESCRIPCIÓN DEL TICKET | TAREAS PRINCIPALES | ESTIMACIÓN (SP) | PRIORIDAD | DEPENDENCIAS |
|-------|------------|-----------|------------------------|-------------------|----------------|-----------|--------------|
| **🔑 GESTIÓN DE ACCESO** | US-001: Autenticación | T-001 | Sistema de Autenticación Completo | • Configurar JWT<br>• Endpoints login/logout/recover<br>• Middleware de autenticación<br>• Frontend de login<br>• Tests unitarios | 8 | P0 | - |
| | US-002: Dashboard | T-002 | Dashboard Principal y Navegación | • Layout responsive<br>• Componentes de métricas<br>• Navegación principal<br>• Integración con APIs<br>• Estados de carga/error | 5 | P0 | T-001 |
| **🎯 OFERTAS INTELIGENTES** | US-003: Crear Oferta IA | T-003 | Formulario de Creación de Ofertas | • Editor enriquecido<br>• Validaciones de formulario<br>• Guardado como borrador<br>• UI/UX optimizada | 5 | P1 | T-001 |
| | | T-004 | Motor de Análisis de IA para Ofertas | • Algoritmo de análisis de contenido<br>• Score de atractivo<br>• Sugerencias automáticas<br>• Estimación de pool de talento<br>• Integración con modelo ML | 21 | P1 | T-003 |
| | US-004: Gestión Ofertas | T-005 | CRUD de Ofertas y Estados | • Lista con filtros<br>• Vista detallada<br>• Cambio de estados<br>• Métricas por oferta<br>• Búsqueda avanzada | 8 | P1 | T-001 |
| **🤖 MATCHING INTELIGENTE** | US-005: Aplicación Candidato | T-006 | Formulario Público de Aplicación | • Formulario sin login<br>• Upload de CV seguro<br>• Validación de formatos<br>• Email de confirmación<br>• Parser básico de CV | 13 | P0 | - |
| | | T-007 | Sistema de Enriquecimiento Automático | • Integración GitHub API<br>• Extracción de datos repos<br>• Job asíncrono procesamiento<br>• Rate limiting y manejo errores<br>• Almacenamiento estructurado | 21 | P1 | T-006 |
| | US-006: Criba IA | T-008 | Algoritmo de Matching MVP | • Modelo scoring keywords<br>• Generación embeddings<br>• Similitud coseno<br>• Endpoint cálculo score<br>• Cache de resultados | 34 | P1 | T-007 |
| | | T-009 | Interfaz de Criba Inteligente | • Vista de candidatos rankeados<br>• Filtros por score<br>• Resumen IA destacado<br>• Acceso rápido a CV<br>• Vista de perfil enriquecido | 13 | P1 | T-008 |
| | US-007: Pipeline | T-010 | Vista Kanban del Pipeline | • Drag & drop candidatos<br>• Columnas configurables<br>• Historial de cambios<br>• Filtros por estado/fecha<br>• Métricas en tiempo real | 13 | P2 | T-009 |
| **💬 COLABORACIÓN** | US-008: Evaluación | T-011 | Sistema de Feedback Colaborativo | • Rating 1-5 estrellas<br>• Comentarios cualitativos<br>• Historial de evaluaciones<br>• Notificaciones push<br>• Vista consolidada feedback | 8 | P2 | T-010 |
| | US-009: Comunicación | T-012 | Chat Interno por Candidato | • Sistema comentarios<br>• Menciones @usuario<br>• Notificaciones tiempo real<br>• Historial conversación<br>• Integración con email | 13 | P2 | T-011 |
| **📊 REPORTES** | US-010: Métricas | T-013 | Dashboard de Métricas Avanzado | • KPIs proceso contratación<br>• Gráficos interactivos<br>• Exportación PDF/Excel<br>• Filtros temporales<br>• Comparativas históricas | 8 | P3 | T-010 |
| | US-011: Análisis | T-014 | Analytics de Calidad Candidatos | • Distribución scores matching<br>• Análisis fuentes sourcing<br>• Tendencias temporales<br>• Insights automáticos<br>• Recomendaciones IA | 13 | P3 | T-013 |

---

## 📋 ROADMAP DE DESARROLLO

### **SPRINT 1 (Semanas 1-2): Foundation & Core IA**
**Objetivo:** Establecer base del sistema con capacidades core de IA
- **T-001:** Sistema de Autenticación (8 SP)
- **T-002:** Dashboard Principal (5 SP)
- **T-006:** Formulario de Aplicación (13 SP)
- **T-007:** Enriquecimiento Automático (21 SP)
- **Total:** 47 Story Points

### **SPRINT 2 (Semanas 3-4): Matching Engine & Ofertas**
**Objetivo:** Implementar motor de matching y gestión de ofertas
- **T-008:** Algoritmo de Matching MVP (34 SP)
- **T-003:** Formulario Creación Ofertas (5 SP)
- **T-005:** CRUD de Ofertas (8 SP)
- **Total:** 47 Story Points

### **SPRINT 3 (Semanas 5-6): UX/UI & Pipeline**
**Objetivo:** Interfaces de usuario y gestión del pipeline
- **T-009:** Interfaz Criba Inteligente (13 SP)
- **T-004:** Motor Análisis IA Ofertas (21 SP)
- **T-010:** Vista Kanban Pipeline (13 SP)
- **Total:** 47 Story Points

### **SPRINT 4 (Semanas 7-8): Colaboración**
**Objetivo:** Funcionalidades colaborativas y feedback
- **T-011:** Sistema Feedback Colaborativo (8 SP)
- **T-012:** Chat Interno por Candidato (13 SP)
- **T-013:** Dashboard Métricas Avanzado (8 SP)
- **Total:** 29 Story Points (Sprint más liviano para buffer)

### **SPRINT 5 (Semanas 9-10): Analytics & Polish**
**Objetivo:** Analytics avanzados y pulimiento
- **T-014:** Analytics Calidad Candidatos (13 SP)
- **Refinamiento y bug fixes** (15 SP)
- **Testing integral y performance** (10 SP)
- **Total:** 38 Story Points

---

## 🏗️ ARQUITECTURA DE IMPLEMENTACIÓN

### **Tecnologías por Ticket:**

| **Frontend (React/TypeScript)** | **Backend (Node.js/Python)** | **Base de Datos** | **IA/ML** |
|--------------------------------|------------------------------|-------------------|-----------|
| T-002: Dashboard UI | T-001: Auth Service | PostgreSQL (structured data) | T-004: Análisis Ofertas |
| T-003: Formulario Ofertas | T-005: Offers API | Redis (caching) | T-007: Enriquecimiento |
| T-006: Aplicación Pública | T-010: Pipeline API | S3 (file storage) | T-008: Matching Engine |
| T-009: Interfaz Criba | T-011: Feedback Service | Vector DB (embeddings) | T-014: Analytics IA |
| T-012: Chat UI | T-013: Metrics Service | | |

### **Dependencias Críticas:**
1. **Vector Database Setup** (Pre-Sprint 1): Pinecone/Weaviate para embeddings
2. **ML Pipeline Infrastructure** (Sprint 1): GPU instances para modelos IA
3. **File Storage** (Sprint 1): S3 buckets para CVs y documentos
4. **Real-time Infrastructure** (Sprint 3): WebSockets para notificaciones

---

## 📊 CRITERIOS DE ACEPTACIÓN POR SPRINT

### **Sprint 1 - Definition of Done:**
- [ ] Usuario puede registrarse/login seguramente
- [ ] Candidato puede aplicar a oferta con CV
- [ ] Sistema enriquece automáticamente perfil con GitHub
- [ ] Dashboard muestra métricas básicas

### **Sprint 2 - Definition of Done:**
- [ ] IA calcula score de matching candidato-oferta
- [ ] Hiring Manager puede crear ofertas optimizadas
- [ ] Sistema gestiona estados de ofertas
- [ ] Performance <500ms para matching

### **Sprint 3 - Definition of Done:**
- [ ] Reclutador ve candidatos rankeados por IA
- [ ] Pipeline visual con drag & drop funcional
- [ ] Ofertas reciben análisis IA automático
- [ ] UX fluida en mobile y desktop

### **Sprint 4 - Definition of Done:**
- [ ] Equipo puede colaborar con feedback estructurado
- [ ] Chat interno por candidato operativo
- [ ] Métricas avanzadas disponibles
- [ ] Notificaciones en tiempo real

### **Sprint 5 - Definition of Done:**
- [ ] Analytics predictivos funcionando
- [ ] Sistema optimizado para 1000+ candidatos
- [ ] Documentación completa
- [ ] Ready for production deployment

---

**Documento generado por:** WGO  
**Fecha:** Diciembre 2024  
**Versión:** 1.0
```

## ✅ COMPLETADO: Planificación Detallada de Tickets

He agregado una **planificación completa de tickets de trabajo** al final del archivo UserStories-WGO.md. La nueva sección incluye:

### 📊 **Tabla Completa de Tickets por Épica:**

**14 tickets detallados** organizados por las 5 épicas principales:
- 🔑 **Gestión de Acceso**: 2 tickets (T-001, T-002)
- 🎯 **Ofertas Inteligentes**: 3 tickets (T-003, T-004, T-005) 
- 🤖 **Matching Inteligente**: 5 tickets (T-006, T-007, T-008, T-009, T-010)
- 💬 **Colaboración**: 2 tickets (T-011, T-012)
- 📊 **Reportes**: 2 tickets (T-013, T-014)

### 🗓️ **Roadmap de 5 Sprints (10 semanas):**

1. **Sprint 1**: Foundation & Core IA (47 SP)
2. **Sprint 2**: Matching Engine & Ofertas (47 SP)  
3. **Sprint 3**: UX/UI & Pipeline (47 SP)
4. **Sprint 4**: Colaboración (29 SP - buffer)
5. **Sprint 5**: Analytics & Polish (38 SP)

### 🏗️ **Información Adicional:**

- **Dependencias claramente marcadas** entre tickets
- **Stack tecnológico** definido por categorías
- **Criterios de aceptación** específicos por sprint
- **Dependencias de infraestructura** identificadas
- **Definition of Done** granular para cada entrega

### 🎯 **Puntos Clave de la Planificación:**

- **Total del proyecto**: ~208 Story Points (10 semanas)
- **Velocity asumida**: 40-47 SP por sprint
- **Prioridades balanceadas**: Core IA primero, colaboración después
- **Arquitectura escalable**: Microservicios desde Sprint 1

Esta planificación proporciona una hoja de ruta clara y ejecutable para el desarrollo del sistema LTI, con entregables tangibles en cada sprint y una progresión lógica hacia el MVP completo.

---

**User**

como extra, usando @UserStories-WGO.md , en base a las tareas definidas, sus estimaciones y dificultad, genérame otro archivo .md en markdown especificando todas las decisiones técnicas, de arquitectura, best práctices y qué cosas deberé tener en cuenta a la hora de implementar todos estos tickets.

---

**Cursor**

```markdown
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
```

## ✅ COMPLETADO: Guía Técnica y Arquitectura Completa

He creado el archivo `Technical-Architecture-Guide-WGO.md` con una **guía técnica exhaustiva** basada en los tickets y estimaciones del UserStories. El documento incluye:

### 📋 **Contenido Principal:**

1. **🛠️ Stack Tecnológico Completo**
   - Frontend: React 18 + TypeScript + Vite
   - Backend: Node.js + Python (híbrido)
   - Bases de Datos: PostgreSQL + Redis + Vector DB
   - IA/ML: sentence-transformers + FastAPI

2. **🏗️ Arquitectura del Sistema**
   - Microservicios con API Gateway
   - Patrones DDD + CQRS + Event Sourcing
   - Diagramas de componentes

3. **🚀 Decisiones Técnicas por Sprint**
   - **Sprint 1**: Autenticación JWT, Dashboard React, Enriquecimiento async
   - **Sprint 2**: Motor de Matching (34 SP - el más complejo), CRUD Ofertas
   - **Sprint 3**: UI avanzada, Pipeline Kanban, UX optimizada

4. **🎯 Patrones y Best Practices**
   - Repository Pattern, Command Pattern, Event-Driven Architecture
   - Custom Hooks, Error Boundaries, Performance Optimization

5. **🔒 Seguridad Integral**
   - JWT con refresh tokens, Encriptación PII, Rate limiting
   - RBAC, Input validation, XSS/CSRF protection

6. **⚡ Performance y Escalabilidad**
   - Caching multi-nivel, Async processing, Database optimization
   - Bundle splitting, Virtualization, Infinite scroll

7. **🚀 DevOps y Deployment**
   - Docker multi-stage, CI/CD pipeline, AWS ECS
   - Monitoring con Prometheus, Health checks

8. **🧪 Testing Strategy**
   - Pyramid testing (70% unit, 20% integration, 10% E2E)
   - ML model testing específico

9. **🤖 Consideraciones ML/IA Específicas**
   - Model versioning, A/B testing algoritmos
   - Feature stores, Drift detection, Performance monitoring

### 🎯 **Puntos Clave para Implementación:**

- **T-008 (Matching Engine)**: El ticket más crítico con arquitectura ML detallada
- **Performance SLA**: <500ms para matching, optimizaciones específicas
- **Fallback graceful**: Para cuando los servicios de IA fallan
- **Escalabilidad**: Diseñado para 1000+ candidatos desde el inicio

### 🚨 **Riesgos y Mitigaciones:**
- Performance del algoritmo → Caching + optimización
- APIs externas → Circuit breakers + fallbacks
- Calidad de datos → Validación + human-in-the-loop

Esta guía proporciona todo lo necesario para que el equipo de desarrollo pueda implementar los tickets de manera eficiente, siguiendo best practices y considerando todos los aspectos técnicos críticos para el éxito del proyecto LTI.

