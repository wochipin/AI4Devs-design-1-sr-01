# FASE 1 : ESTRATEGIA Y VISIÓN DEL PRODUCTO

### Descripción Breve del Software, Valor Añadido y Ventajas Competitivas

#### **Descripción Breve:**
**LTI (Lean Talent Intelligence)** es un sistema de seguimiento de candidatos (ATS) de nueva generación, diseñado específicamente para empresas que buscan contratar talento de élite en Inteligencia Artificial y Machine Learning. Es una plataforma que entiende la profundidad técnica de los roles y los candidatos.

#### **Propuesta de Valor:**
LTI va más allá de las palabras clave, utilizando un motor de IA semántico para realizar un *matching* inteligente entre los requisitos complejos de un puesto de IA y la experiencia real de los candidatos (analizando proyectos, código y publicaciones). Esto reduce drásticamente el tiempo de criba y aumenta la calidad de los finalistas, permitiendo a los managers de ingeniería y reclutadores técnicos centrarse únicamente en el talento más cualificado.

#### **Ventajas Competitivas Clave:**

* **Matching Semántico de IA:** A diferencia de los ATS genéricos que se basan en palabras clave, nuestro algoritmo entiende conceptos, frameworks y la relevancia de la experiencia en proyectos de IA, ofreciendo un ranking de candidatos mucho más preciso.
* **Colaboración Fluida en Slack/Teams:** Integramos el flujo de revisión y feedback directamente en las herramientas que los equipos técnicos ya utilizan, eliminando la fricción y acelerando la toma de decisiones.
* **Enfoque de Nicho Experto:** Toda la plataforma, desde la creación de la oferta hasta el análisis del candidato, está optimizada para los roles de IA, reconociendo las habilidades, herramientas (TensorFlow, PyTorch) y plataformas (GitHub, Kaggle, ArXiv) que realmente importan.

graph TD
    subgraph "Problema"
        P1["1. ATS genéricos no entienden perfiles<br>técnicos complejos (IA/ML)."]
        P2["2. Hiring Managers pierden tiempo<br>en criba manual."]
        P3["3. Comunicación ineficiente (email)<br>entre RRHH y equipo técnico."]
    end

    subgraph "Solución"
        S1["1. Motor de matching con IA<br>(analiza GitHub, ArXiv...)."]
        S2["2. Integración de colaboración y<br>feedback en Slack/Teams."]
        S3["3. Perfiles de candidato<br>enriquecidos automáticamente."]
    end

    subgraph "Métricas Clave"
        M1["- Ratio Candidatos Presentados<br>vs. Entrevistados"]
        M2["- Tiempo medio para cubrir vacante"]
        M3["- Tasa de adopción de la integración"]
    end

    subgraph "Propuesta Única de Valor"
        PUV["El ATS inteligente que entiende el<br>talento en IA como un experto, no<br>como un simple buscador de palabras clave."]
    end

    subgraph "Ventaja Injusta"
        VI["Algoritmo de matching propietario y<br>entrenado para el nicho de IA."]
    end

    subgraph "Canales"
        C1["- Marketing de contenidos para CTOs"]
        C2["- Presencia en conferencias<br>y comunidades de IA"]
        C3["- Ventas directas"]
    end

    subgraph "Segmentos de Clientes"
        SC1["<b>Clientes:</b><br>Empresas de tecnología (Startups a<br>Corporaciones) con equipos de IA/ML."]
        SC2["<b>Usuarios:</b><br>- Reclutadores Técnicos<br>- Hiring Managers (Leads IA, CTOs)<br>- Candidatos"]
    end

    subgraph "Estructura de Costes"
        EC1["- Desarrollo y mantenimiento"]
        EC2["- Costes de infraestructura<br>Cloud (GPUs)"]
        EC3["- Salarios del equipo"]
    end

    subgraph "Fuentes de Ingresos"
        FI1["Suscripción SaaS por niveles<br>(Básico, Pro, Enterprise)"]
    end

    %% Conexiones para crear la estructura visual
    Problema---Solución---Métricas_Clave---Propuesta_Única_de_Valor---Ventaja_Injusta---Canales---Segmentos_de_Clientes
    Segmentos_de_Clientes---Estructura_de_Costes---Fuentes_de_Ingresos

    %% Ocultar las líneas de conexión para una apariencia limpia de Canvas
    style Problema stroke-width:0px
    style Solución stroke-width:0px
    style Métricas_Clave stroke-width:0px
    style Propuesta_Única_de_Valor stroke-width:0px
    style Ventaja_Injusta stroke-width:0px
    style Canales stroke-width:0px
    style Segmentos_de_Clientes stroke-width:0px
    style Estructura_de_Costes stroke-width:0px

# FASE 2: DEFINICIÓN FUNCIONAL Y CASOS DE USO CLAVE

Los 3 casos de uso principales para la v1 deberían ser:

1.  **Crear una Oferta de Empleo y Obtener un "Benchmark" de Talento con IA:**
    > **Racionalidad:** No se trata solo de publicar un trabajo. Desde el inicio, nuestra IA puede analizar la descripción y compararla con el mercado, sugiriendo habilidades clave o indicando si las expectativas son realistas. Aporta valor desde el minuto cero.

2.  **Matching y Revisión Colaborativa de Candidatos en Slack:**
    > **Racionalidad:** Este es el corazón de LTI. Combina nuestra ventaja en IA (el matching) con nuestra ventaja en colaboración (Slack). Es el flujo donde el valor se hace más tangible para el Reclutador y el Hiring Manager.

3.  **Enriquecimiento del Perfil del Candidato y Criba Inteligente:**
    > **Racionalidad:** Este caso de uso detalla cómo cumplimos nuestra promesa. Muestra el proceso de un candidato aplicando, LTI enriqueciendo su perfil con datos de GitHub/ArXiv, y presentando un resumen inteligente al reclutador para una decisión de criba en segundos.

---

*Estos tres casos de uso forman un ciclo virtuoso que cubre los puntos más críticos y diferenciales de nuestro producto.*

### FASE 2: CASOS DE USO PRINCIPALES

A continuación, se detallan los flujos de usuario que representan el núcleo de la propuesta de valor de LTI.

#### **Caso de Uso 1: Crear una Oferta de Empleo y Obtener un "Benchmark" de Talento con IA**

* **ID:** CU-01
* **Nombre del Caso de Uso:** Crear una Oferta de Empleo y Obtener un "Benchmark" de Talento con IA.
* **Actores:**
    * **Primario:** Hiring Manager.
    * **Secundario:** Reclutador Técnico.
* **Descripción/Objetivo:** El Hiring Manager necesita crear una nueva oferta de empleo para un rol de IA. LTI no solo le permite definir el puesto, sino que utiliza su IA para analizar la descripción, compararla con datos del mercado y sugerir mejoras para atraer al talento adecuado y establecer expectativas realistas. El Reclutador Técnico puede revisar y aprobar la oferta final.
* **Precondiciones:** El Hiring Manager y el Reclutador Técnico tienen una cuenta en LTI y han iniciado sesión. Existe una plantilla de oferta predefinida en el sistema.
* **Flujo Básico (Happy Path):**
    1.  El **Hiring Manager** selecciona la opción "Crear Nueva Oferta" en el dashboard.
    2.  El **Sistema** presenta un formulario basado en una plantilla, con campos como "Título del Puesto", "Ubicación", "Equipo", y un editor de texto enriquecido para la "Descripción y Responsabilidades".
    3.  El **Hiring Manager** completa los campos principales y redacta una primera versión de la descripción del puesto.
    4.  El **Hiring Manager** hace clic en el botón "Analizar con IA".
    5.  El **Sistema** procesa la descripción, la compara con miles de ofertas similares y perfiles de candidatos anónimos, y en segundos muestra un panel de "Análisis de Oferta" con:
        * Un score de "Atractivo del Mercado".
        * Sugerencias de habilidades o tecnologías clave que faltan (ej. "Considera añadir 'MLOps' ya que es común en roles de 'Senior MLE'").
        * Una estimación de la dificultad para cubrir el puesto y el pool de talento disponible.
        * Alertas sobre posibles sesgos en el lenguaje.
    6.  El **Hiring Manager** refina la descripción basándose en las sugerencias de la IA.
    7.  Una vez satisfecho, el **Hiring Manager** guarda la oferta y la envía para su aprobación.
    8.  El **Sistema** notifica al **Reclutador Técnico**.
    9.  El **Reclutador Técnico** revisa la oferta final, la aprueba y la publica en los portales de empleo configurados (ej. LinkedIn, web de la empresa).
* **Postcondiciones (Éxito):** La nueva oferta de empleo está creada, optimizada y publicada, lista para recibir candidatos.

##### **Diagrama de Caso de Uso (Mermaid): CU-01**

` ``mermaid
graph TD
    A[Hiring Manager] -- 'Selecciona Crear Nueva Oferta' --> B(Sistema);
    B -- 'Presenta formulario' --> A;
    A -- 'Completa campos y descripción' --> C{Analizar con IA};
    C -- 'Hace clic en Analizar con IA' --> D(Sistema);
    D -- 'Procesa y muestra Análisis de Oferta' --> A;
    A -- 'Refina descripción basándose en IA' --> E{Guardar y Enviar para Aprobación};
    E -- 'Guarda y envía' --> F(Sistema);
    F -- 'Notifica' --> G[Reclutador Técnico];
    G -- 'Revisa y aprueba' --> H(Sistema);
    H -- 'Publica oferta' --> I[Oferta Publicada];

    subgraph Leyenda
        A[Hiring Manager]:::actor;
        G[Reclutador Técnico]:::actor;
        B(Sistema):::system;
        D(Sistema):::system;
        F(Sistema):::system;
        H(Sistema):::system;
        C{Analizar con IA}:::process;
        E{Guardar y Enviar para Aprobación}:::process;
        I[Oferta Publicada]:::result;
    end

    classDef actor fill:#FFDDC1,stroke:#333,stroke-width:2px;
    classDef system fill:#D1ECF1,stroke:#333,stroke-width:2px;
    classDef process fill:#C3E6CB,stroke:#333,stroke-width:2px;
    classDef result fill:#F8D7DA,stroke:#333,stroke-width:2px;
` ``

---

#### **Caso de Uso 2: Matching y Revisión Colaborativa de Candidatos en Slack**

* **ID:** CU-02
* **Nombre del Caso de Uso:** Matching y Revisión Colaborativa de Candidatos en Slack.
* **Actores:**
    * **Primario:** Reclutador Técnico.
    * **Secundario:** Hiring Manager.
* **Descripción/Objetivo:** Una vez que los candidatos han aplicado, el Reclutador Técnico quiere identificar rápidamente a los más prometedores y obtener feedback ágil del Hiring Manager. LTI ejecuta su matching de IA y presenta a los mejores candidatos directamente en un canal de Slack dedicado, donde ambos pueden discutir y decidir los siguientes pasos.
* **Precondiciones:** Existe una oferta activa con al menos un nuevo candidato. La integración con Slack está configurada y existe un canal para la oferta (ej. `#hiring-data-scientist`).
* **Flujo Básico (Happy Path):**
    1.  El **Reclutador Técnico** abre la vista de candidatos para una oferta específica en LTI.
    2.  El **Sistema** ya ha ejecutado automáticamente el "Matching de IA" para cada nuevo candidato, asignando un score de afinidad (ej. 92%).
    3.  El **Reclutador Técnico** filtra los candidatos para ver solo los que superan un umbral de matching (ej. > 85%).
    4.  Selecciona los 3 mejores perfiles y hace clic en "Compartir con Hiring Manager en Slack".
    5.  El **Sistema** envía un mensaje interactivo al canal de Slack correspondiente. El mensaje incluye un resumen de cada candidato (nombre, score de matching, y 2-3 puntos clave extraídos por la IA) y botones de acción ("Ver Perfil Completo", "Avanzar", "Rechazar").
    6.  El **Hiring Manager** recibe la notificación en Slack, revisa los resúmenes.
    7.  El **Hiring Manager** hace clic en "Ver Perfil Completo" en uno de los candidatos, lo que abre el perfil detallado de LTI en una nueva pestaña del navegador.
    8.  Dentro de Slack, el **Hiring Manager** deja un comentario en el hilo del mensaje: "@Reclutador, me gusta mucho la experiencia de Ana en proyectos de Computer Vision. Avancemos con ella".
    9.  El **Reclutador Técnico** ve el comentario y hace clic en el botón "Avanzar" directamente en el mensaje de Slack.
    10. El **Sistema** actualiza el estado del candidato en LTI a la siguiente fase (ej. "Criba Telefónica") y registra el comentario de Slack como parte del historial del candidato.
* **Postcondiciones (Éxito):** Se ha tomado una decisión sobre los candidatos clave de forma rápida y colaborativa, y el estado del candidato está actualizado en LTI.

##### **Diagrama de Caso de Uso (Mermaid): CU-02**

` ``mermaid
ggraph TD
    A[Reclutador Técnico] -- |Abre vista de candidatos en LTI| --> B(Sistema);
    B -- |Ha ejecutado Matching de IA (con Score de afinidad)| --> A;
    A -- |Filtra candidatos (> 85%)| --> C{Seleccionar y Compartir};
    C -- |Selecciona 3 mejores perfiles y hace clic en 'Compartir en Slack'| --> D(Sistema);
    D -- |Envía mensaje interactivo a canal de Slack (resumen + botones de acción)| --> E[Hiring Manager];
    E -- |Recibe notificación y revisa resúmenes| --> F{Revisar Perfil o Comentar};
    F -- |Hace clic en 'Ver Perfil Completo' (abre LTI)| --> G(Sistema);
    E -- |Deja comentario en hilo de Slack| --> A;
    A -- |Ve comentario y hace clic en 'Avanzar' en Slack| --> H(Sistema);
    H -- |Actualiza estado de candidato en LTI (ej. Criba Telefónica) y registra comentario| --> I[Candidato Actualizado en LTI];

    subgraph Leyenda
        A[Reclutador Técnico]:::actor;
        E[Hiring Manager]:::actor;
        B(Sistema):::system;
        D(Sistema):::system;
        G(Sistema):::system;
        H(Sistema):::system;
        C{Seleccionar y Compartir}:::process;
        F{Revisar Perfil o Comentar}:::process;
        I[Candidato Actualizado en LTI]:::result;
    end

    classDef actor fill:#FFDDC1,stroke:#333,stroke-width:2px;
    classDef system fill:#D1ECF1,stroke:#333,stroke-width:2px;
    classDef process fill:#C3E6CB,stroke:#333,stroke-width:2px;
    classDef result fill:#F8D7DA,stroke:#333,stroke-width:2px;
` ``

---

#### **Caso de Uso 3: Enriquecimiento del Perfil del Candidato y Criba Inteligente**

* **ID:** CU-03
* **Nombre del Caso de Uso:** Enriquecimiento del Perfil del Candidato y Criba Inteligente.
* **Actores:**
    * **Primario:** Sistema (automatizado).
    * **Secundarios:** Candidato, Reclutador Técnico.
* **Descripción/Objetivo:** Optimizar el tiempo del Reclutador mostrando no solo la información que el candidato proporciona, sino un perfil 360°. Cuando un candidato aplica, LTI enriquece automáticamente su perfil con datos públicos relevantes (GitHub, ArXiv) y genera un resumen para que el Reclutador pueda realizar una criba inicial de alta calidad en segundos.
* **Precondiciones:** Existe una oferta de empleo pública.
* **Flujo Básico (Happy Path):**
    1.  Un **Candidato** encuentra la oferta y completa el formulario de aplicación, adjuntando su CV y opcionalmente su perfil de GitHub/LinkedIn.
    2.  El **Candidato** envía su aplicación.
    3.  El **Sistema** recibe la aplicación y la parsea, extrayendo la información estructurada del CV.
    4.  El **Sistema** inicia un proceso de enriquecimiento en segundo plano:
        a.  Si se proporcionó un perfil de GitHub, accede a la API de GitHub para obtener información sobre los repositorios públicos, lenguajes de programación más usados y contribuciones.
        b.  Busca en ArXiv.org (un repositorio de artículos científicos) publicaciones que coincidan con el nombre y la afiliación del candidato.
    5.  Una vez completado el enriquecimiento, el **Sistema** alimenta toda la información (CV + datos enriquecidos) a su modelo de IA para generar un "Resumen Inteligente" de 3 a 5 puntos (ej. "Principal contribuidor en un repositorio de PyTorch con 50+ estrellas", "Autor de 2 papers sobre Detección de Anomalías").
    6.  El **Reclutador Técnico** entra a la lista de nuevos candidatos.
    7.  Al hacer clic en un candidato, el **Sistema** presenta el perfil completo, destacando en la parte superior el "Resumen Inteligente" y el score de matching. Debajo, se muestran las secciones detalladas del CV, actividad de GitHub y publicaciones encontradas.
    8.  El **Reclutador Técnico** lee el resumen en menos de 30 segundos y toma una decisión informada de si continuar o no con el perfil.
* **Postcondiciones (Éxito):** El perfil del candidato en LTI está completo y enriquecido, y el reclutador ha podido realizar una criba rápida y eficaz.

##### **Diagrama de Caso de Uso (Mermaid): CU-03**

` ``mermaid
graph TD
    A[Candidato] -- |Completa y envía formulario de aplicación (CV, GitHub/LinkedIn opcional)| --> B(Sistema);
    B -- |Recibe y parsear aplicación (extrae info del CV)| --> C(Sistema);
    C -- |Inicia proceso de enriquecimiento en segundo plano| --> D{Sistema: Enriquecimiento};
    D -- |Accede a API de GitHub y busca en ArXiv.org| --> D;
    D -- |Alimenta información a modelo de IA| --> E(Sistema);
    E -- |Genera Resumen Inteligente de 3 a 5 puntos| --> F[Reclutador Técnico];
    F -- |Entra a lista de nuevos candidatos| --> G(Sistema);
    G -- |Al hacer clic en candidato, presenta perfil completo (Resumen Inteligente, Score de Matching, CV, GitHub, publicaciones)| --> F;
    F -- |Lee resumen en < 30 segundos y toma decisión| --> H[Perfil del Candidato Enriquecido y Cribado];

    subgraph Leyenda
        A[Candidato]:::actor;
        F[Reclutador Técnico]:::actor;
        B(Sistema):::system;
        C(Sistema):::system;
        D{Sistema: Enriquecimiento}:::process;
        E(Sistema):::system;
        G(Sistema):::system;
        H[Perfil del Candidato Enriquecido y Cribado]:::result;
    end

    classDef actor fill:#FFDDC1,stroke:#333,stroke-width:2px;
    classDef system fill:#D1ECF1,stroke:#333,stroke-width:2px;
    classDef process fill:#C3E6CB,stroke:#333,stroke-width:2px;
    classDef result fill:#F8D7DA,stroke:#333,stroke-width:2px;
` ``

**Fase 3: Modelo de Datos**.

### **Entidades Principales**

A continuación se listan las entidades clave para la v1 de LTI, con sus atributos y tipos de datos sugeridos.

**1. Company**
Almacena la información de la empresa cliente que utiliza el ATS.

* `company_id` (PK, UUID): Identificador único de la empresa.
* `name` (VARCHAR): Nombre de la empresa.
* `created_at` (TIMESTAMP): Fecha de registro.

**2. User**
Representa a los usuarios (Reclutadores, Hiring Managers) que operan en la plataforma.

* `user_id` (PK, UUID): Identificador único del usuario.
* `company_id` (FK to Company): A qué empresa pertenece.
* `email` (VARCHAR, UNIQUE): Email de acceso, debe ser único.
* `full_name` (VARCHAR): Nombre completo del usuario.
* `role` (ENUM): Rol del usuario ('RECRUITER', 'HIRING_MANAGER', 'ADMIN').
* `created_at` (TIMESTAMP): Fecha de creación de la cuenta.

**3. JobOffer**
Define una oferta de trabajo específica.

* `job_offer_id` (PK, UUID): Identificador único de la oferta.
* `company_id` (FK to Company): Empresa que publica la oferta.
* `created_by_user_id` (FK to User): Usuario que creó la oferta.
* `title` (VARCHAR): Título del puesto (ej. "Machine Learning Engineer").
* `description` (TEXT): Descripción completa del puesto (soporta Markdown).
* `status` (ENUM): Estado de la oferta ('DRAFT', 'OPEN', 'CLOSED', 'ARCHIVED').
* `created_at` (TIMESTAMP): Fecha de creación.
* `published_at` (TIMESTAMP, nullable): Fecha en que se hizo pública.

**4. Candidate**
Almacena la información de una persona que podría aplicar a un puesto. Es una entidad centralizada para evitar duplicados.

* `candidate_id` (PK, UUID): Identificador único del candidato.
* `email` (VARCHAR, UNIQUE): Email del candidato, clave para la deduplicación.
* `full_name` (VARCHAR): Nombre completo.
* `phone_number` (VARCHAR, nullable): Teléfono de contacto.
* `linkedin_url` (VARCHAR, nullable): URL a su perfil de LinkedIn.
* `github_url` (VARCHAR, nullable): URL a su perfil de GitHub (clave para el enriquecimiento).
* `cv_document_url` (VARCHAR, nullable): Enlace al archivo de su CV en un storage.

**5. Application**
La entidad que conecta a un `Candidate` con una `JobOffer`. Es el corazón del seguimiento.

* `application_id` (PK, UUID): Identificador único de la aplicación.
* `candidate_id` (FK to Candidate): Quién aplica.
* `job_offer_id` (FK to JobOffer): A qué oferta aplica.
* `status_pipeline` (VARCHAR): Fase actual del proceso (ej. 'Applied', 'Screening', 'Technical Interview', 'Hired').
* `ai_match_score` (INTEGER, nullable): Puntuación de 0-100 generada por la IA.
* `ai_summary` (TEXT, nullable): Resumen generado por la IA.
* `applied_at` (TIMESTAMP): Fecha en que se recibió la aplicación.

**6. Feedback**
Almacena los comentarios y valoraciones que los `User`s dejan sobre una `Application`.

* `feedback_id` (PK, UUID): Identificador único del feedback.
* `application_id` (FK to Application): Feedback sobre esta aplicación.
* `user_id` (FK to User): Quién dejó el feedback.
* `rating` (INTEGER, nullable): Valoración numérica (ej. 1 a 5).
* `comment` (TEXT): Comentario cualitativo.
* `created_at` (TIMESTAMP): Fecha del comentario.

**7. EnrichmentData**
Guarda los datos estructurados obtenidos de fuentes externas para un candidato.

* `enrichment_id` (PK, UUID): ID del dato.
* `candidate_id` (FK to Candidate): A qué candidato pertenece la información.
* `source` (ENUM): De dónde viene el dato ('GITHUB', 'ARXIV', 'LINKEDIN').
* `data` (JSONB): Los datos en formato JSON (ej. lista de repositorios, publicaciones).
* `last_updated` (TIMESTAMP): Cuándo se actualizó por última vez.

---

### **Relaciones Principales**

* Una `Company` tiene muchos `User`s y muchas `JobOffer`s.
* Un `Candidate` puede tener muchas `Application`s (a diferentes `JobOffer`s).
* Una `JobOffer` puede tener muchas `Application`s.
* Una `Application` pertenece a un único `Candidate` y a una única `JobOffer`.
* Una `Application` puede tener muchos `Feedback`s de diferentes `User`s.
* Un `Candidate` puede tener varios registros de `EnrichmentData` (uno por cada fuente).

### **Diagrama Entidad-Relación (ERD) con Mermaid**

Este diagrama visualiza el modelo de datos que acabamos de describir.

` ``mermaid
erDiagram
    Company {
        UUID company_id PK
        VARCHAR name
    }

    User {
        UUID user_id PK
        UUID company_id FK
        VARCHAR email UK
        VARCHAR full_name
        ENUM role
    }

    JobOffer {
        UUID job_offer_id PK
        UUID company_id FK
        UUID created_by_user_id FK
        VARCHAR title
        TEXT description
        ENUM status
    }

    Candidate {
        UUID candidate_id PK
        VARCHAR email UK
        VARCHAR full_name
        VARCHAR github_url
    }

    Application {
        UUID application_id PK
        UUID candidate_id FK
        UUID job_offer_id FK
        VARCHAR status_pipeline
        INT ai_match_score
        TEXT ai_summary
    }

    Feedback {
        UUID feedback_id PK
        UUID application_id FK
        UUID user_id FK
        TEXT comment
        INT rating
    }

    EnrichmentData {
        UUID enrichment_id PK
        UUID candidate_id FK
        ENUM source
        JSONB data
    }

    Company ||--|{ User : "tiene"
    Company ||--|{ JobOffer : "publica"
    User ||--o{ JobOffer : "crea"
    JobOffer ||--|{ Application : "recibe"
    Candidate ||--|{ Application : "realiza"
    Candidate ||--o{ EnrichmentData : "es enriquecido con"
    Application ||--|{ Feedback : "recibe"
    User ||--o{ Feedback : "deja"
` ``

**Fase 4: Diseño del Sistema a Alto Nivel y Diagrama C4**.


### **Diseño del Sistema a Alto Nivel**

Proponemos una arquitectura de microservicios moderna, desacoplada y escalable, ideal para un producto SaaS como LTI que tiene una fuerte dependencia de componentes de IA y comunicaciones en tiempo real.

#### **Explicación de la Arquitectura**

1.  **Frontend (Cliente):** Será una **Single Page Application (SPA)** desarrollada con un framework moderno como React o Vue.js. Esta aplicación web será la única interfaz para nuestros usuarios (Reclutadores y Hiring Managers) y se comunicará con el backend a través de una API.

2.  **API Gateway:** Actuará como la única puerta de entrada para todas las peticiones del cliente. Se encargará de tareas transversales como la **autenticación de usuarios** (validando tokens JWT), el **enrutamiento** de peticiones al microservicio correspondiente y el **rate limiting** para proteger el sistema de abusos.

3.  **Microservicios de Backend:** El corazón de la lógica de negocio se divide en servicios independientes y especializados:
    * **Servicio Core ATS:** Gestiona las entidades principales del negocio (Compañías, Usuarios, Ofertas de Empleo). Proporciona las operaciones CRUD básicas.
    * **Servicio de Candidatos y Aplicaciones:** Se especializa en todo lo relacionado con el candidato y su ciclo de vida en una oferta: recibir aplicaciones, parsear CVs, y gestionar el pipeline de estados.
    * **Servicio de Colaboración:** Orquesta la integración con sistemas de terceros como **Slack y Teams**. Escucha eventos de otros servicios (ej. "nuevo feedback añadido") y se encarga de enviar las notificaciones interactivas.
    * **Servicio de IA (Nuestro Diferenciador):** Un servicio aislado y altamente especializado que expone endpoints para las tareas de IA. Principalmente:
        * `POST /match`: Calcula el score de afinidad entre un candidato y una oferta.
        * `POST /summarize`: Genera el resumen inteligente de un perfil.
        Este servicio se ejecutará en una infraestructura optimizada para Machine Learning.
    * **Servicio de Notificaciones:** Gestiona comunicaciones asíncronas como el envío de emails (ej. confirmación de entrevistas, restablecimiento de contraseñas).

4.  **Capa de Persistencia (Bases de Datos):** Adoptamos un enfoque de **persistencia políglota**, usando la base de datos adecuada para cada tarea:
    * **Base de Datos Relacional (PostgreSQL):** Almacenará todos los datos estructurados definidos en nuestro modelo de datos (Usuarios, Ofertas, Aplicaciones, etc.). Es fiable y su soporte para JSONB es excelente.
    * **Base de Datos Vectorial (ej. Pinecone, Weaviate):** Componente **CRÍTICO** para nuestro matching de IA. Aquí almacenaremos los *embeddings* (representaciones vectoriales) de los perfiles de candidatos y las descripciones de ofertas para poder realizar búsquedas de similitud semántica de forma ultra-rápida.

5.  **Message Broker (ej. RabbitMQ o Kafka):** Facilitará la comunicación asíncrona y el desacoplamiento entre los microservicios. Por ejemplo, cuando el `Servicio de Candidatos` recibe una nueva aplicación, publica un evento `new_application_received`. El `Servicio de IA` y el `Servicio de Colaboración` estarán suscritos a este evento para actuar en consecuencia sin necesidad de una llamada directa.

#### **Diagrama de Arquitectura de Alto Nivel (Mermaid)**

` ``mermaid
graph TD
    subgraph "Usuarios"
        direction LR
        UserClient["Cliente Web (SPA)"]
    end

    subgraph "Infraestructura LTI Cloud"
        direction TB
        API_GW["API Gateway"]

        subgraph "Microservicios"
            direction LR
            CoreSvc["Servicio Core ATS"]
            CandidateSvc["Servicio de Candidatos/Aplicaciones"]
            AISvc["Servicio de IA"]
            CollabSvc["Servicio de Colaboración"]
        end

        subgraph "Capa de Datos"
            direction LR
            PostgresDB[("PostgreSQL DB")]
            VectorDB[("Vector DB")]
        end

        Broker[("Message Broker")]
    end

    subgraph "APIs Externas"
        direction LR
        SlackAPI["Slack API"]
        GitHubAPI["GitHub API"]
    end

    UserClient -- HTTPS --> API_GW
    API_GW --> CoreSvc
    API_GW --> CandidateSvc
    API_GW --> AISvc
    API_GW --> CollabSvc
    
    CandidateSvc -- publica eventos --> Broker
    AISvc -- consume eventos --> Broker
    CollabSvc -- consume eventos --> Broker

    CoreSvc --- PostgresDB
    CandidateSvc --- PostgresDB
    AISvc --- VectorDB
    CollabSvc -- HTTPS --> SlackAPI
    CandidateSvc -- HTTPS --> GitHubAPI

` ``

---

### **Análisis Profundo con el Modelo C4**

Para ilustrar con más detalle, aplicaremos el modelo C4 al componente más valioso: el **Servicio de IA**. Mostraremos los diagramas de Contexto (C1), Contenedores (C2) y Componentes (C3).

#### **C1: Diagrama de Contexto del Sistema**
Muestra a LTI como una caja negra y cómo interactúa con los usuarios y otros sistemas.

` ``mermaid
graph TD
    subgraph "Sistema LTI"
        LTI_System("Plataforma LTI")
    end

    Recruiter("Reclutador / Hiring Manager")
    Candidate("Candidato")
    Slack("[Sistema Externo: Slack]")
    GitHub("[Sistema Externo: GitHub]")
    
    Recruiter -- "Usa para gestionar contrataciones" --> LTI_System
    Candidate -- "Aplica a ofertas" --> LTI_System
    LTI_System -- "Envía/Recibe notificaciones y acciones" --> Slack
    LTI_System -- "Obtiene datos de perfiles" --> GitHub

    style LTI_System fill:#1168bd,stroke:#000,stroke-width:2px,color:#fff
` ``

#### **C2: Diagrama de Contenedores**
Hacemos "zoom in" en la Plataforma LTI para ver sus principales bloques de construcción (contenedores).

` ``mermaid
graph TD
    subgraph "Plataforma LTI (System)"
        direction TB

        Frontend["Frontend SPA<br>[React]"]
        APIGW["API Gateway<br>[NGINX / Express]"]
        
        subgraph "Backend Services"
            direction LR
            CoreSvc["Servicio Core ATS<br>[Node.js]"]
            CandidateSvc["Servicio de Candidatos<br>[Python/FastAPI]"]
            AISvc["**Servicio de IA**<br>**[Python/FastAPI]**"]
            CollabSvc["Servicio de Colaboración<br>[Node.js]"]
        end

        subgraph "Bases de Datos"
            direction LR
            PostgresDB[("PostgreSQL DB<br>[Relacional]")]
            VectorDB[("Vector DB<br>[Vectores]")]
        end
    end

    User("Usuario")

    User -- "HTTPS" --> Frontend
    Frontend -- "API Calls (HTTPS)" --> APIGW
    APIGW -- "rutas" --> CoreSvc
    APIGW -- "rutas" --> CandidateSvc
    APIGW -- "rutas" --> AISvc
    APIGW -- "rutas" --> CollabSvc

    CoreSvc -- "lee/escribe" --> PostgresDB
    CandidateSvc -- "lee/escribe" --> PostgresDB
    AISvc -- "lee/escribe" --> VectorDB
    AISvc -- "lee" --> PostgresDB

    style AISvc fill:#1168bd,stroke:#f00,stroke-width:3px,color:#fff
` ``

#### **C3: Diagrama de Componentes del "Servicio de IA"**
Hacemos el "zoom in" final dentro del contenedor del **Servicio de IA** para ver sus componentes internos.

` ``mermaid
graph TD
    subgraph "Contenedor: Servicio de IA"
        direction TB

        ApiController["API Controller<br>[FastAPI]"]
        
        subgraph "Lógica Principal"
            direction LR
            EmbeddingGenerator["Generador de Embeddings<br>[SentenceTransformer]"]
            Matcher["Componente de Matching<br>[Lógica de negocio]"]
            Summarizer["Componente de Resumen<br>[HuggingFace/LLM]"]
        end
        
        VectorDBClient["Cliente de Vector DB<br>[SDK de Pinecone/Weaviate]"]
    end

    APIGW("Desde API Gateway")
    VectorDB(("[Externa: Vector DB]"))
    
    APIGW -- "HTTPS Request<br>(/match, /summarize)" --> ApiController
    ApiController -- "invoca" --> EmbeddingGenerator
    ApiController -- "invoca" --> Matcher
    ApiController -- "invoca" --> Summarizer
    
    EmbeddingGenerator -- "genera vector de" --> Matcher
    Matcher -- "busca similitud en" --> VectorDBClient
    VectorDBClient -- "TCP/IP" --> VectorDB
    
    style ApiController fill:#85c2ff
    style EmbeddingGenerator fill:#b9deff
    style Matcher fill:#b9deff
    style Summarizer fill:#b9deff
    style VectorDBClient fill:#85c2ff
` ``