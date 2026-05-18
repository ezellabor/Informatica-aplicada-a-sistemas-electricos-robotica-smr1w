---

## 1. Etapas de un Proyecto Tecnológico Estándar

Este diagrama de flujo muestra el ciclo de vida lineal que sigue cualquier proyecto tecnológico, adaptado a la metodología de diseño que usamos en el aula.

```mermaid
graph TD
    A[1. Detección del Problema / Necesidad] --> B[2. Búsqueda de Información y Brainstorming]
    B --> C[3. Diseño de la Solución Boceto/Planos]
    C --> D[4. Planificación y Gestión de Tareas]
    D --> E[5. Construcción / Desarrollo Electrónica y 3D]
    E --> F[6. Pruebas, Evaluación y Depuración]
    F --> G[7. Documentación Técnica y Presentación]
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#bbf,stroke:#333,stroke-width:2px
    style G fill:#bfb,stroke:#333,stroke-width:2px
``` 
---

```mermaid
graph LR
    A[Product Backlog<br>Lista de tareas globales] --> B[Sprint Backlog<br>Tareas del Sprint actual]
    B --> C(Sprint de Trabajo<br>1-2 semanas)
    C --> D[Reunión Diaria<br>Daily Scrum 5 min]
    D --> C
    C --> E[Incremento de Producto<br>Software/Hardware Funcional]
    E --> F[Sprint Review & Retrospective<br>Demo y mejora del equipo]
    F --> A
    
    style A fill:#fdd,stroke:#333
    style C fill:#dfd,stroke:#333,stroke-width:2px
    style E fill:#ddf,stroke:#333,stroke-width:2px
``` 
---  

```mermaid
graph TD
    subgraph Enfoque Tradicional Cascada
        A1[Requisitos] --> A2[Diseño completo] --> A3[Construcción total] --> A4[Pruebas finales] --> A5[Entrega final única]
    end

    subgraph Enfoque Ágil Scrum
        B1[Backlog Priorizado] --> B2[Sprint 1: Electrónica] --> B3[Incremento 1: Circuito funcional]
        B3 --> B4[Sprint 2: Carcasa 3D] --> B5[Incremento 2: Caja impresa]
        B5 --> B6[Sprint 3: Integración] --> B7[Producto final EcoDrop SMR]
    end

    style A5 fill:#ffb,stroke:#333
    style B7 fill:#bfb,stroke:#333,stroke-width:2px

```


