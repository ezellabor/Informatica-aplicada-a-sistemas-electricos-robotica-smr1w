# Guía de referencia — Proyecto Tecnológico (1º SMR)

**Profesor:** Ezequiel Llarena Borges
**Duración:** 3 trimestres · 1 entrega por trimestre

---

## En qué consiste

Cada alumno o grupo desarrollará un proyecto tecnológico propio, eligiendo uno de los ejemplos propuestos al final de esta guía (o una variante justificada). El proyecto se entrega en **tres fases**, una por trimestre, siguiendo el ciclo de vida real de un proyecto tecnológico: desde la idea hasta el producto terminado, documentado y presentado.

Como referencia de todo el proceso se toma el proyecto **EcoDrop SMR** (sistema de riego automatizado con Arduino), que combina electrónica, programación e impresión 3D y sirve de modelo de cómo documentar y estructurar tu propio proyecto.

---

## 1. Fases de un proyecto tecnológico

Todo proyecto tecnológico, sea cual sea el ejemplo elegido, recorre estas fases:

1. **Detección del problema o necesidad**
2. **Búsqueda de información y brainstorming**
3. **Diseño de la solución** (boceto, planos, diagramas)
4. **Planificación y gestión de tareas**
5. **Construcción del producto o servicio**
6. **Pruebas, evaluación y depuración**
7. **Documentación técnica y presentación**

## 2. Metodología de trabajo

El proyecto combina dos metodologías complementarias:

**Design Thinking** (para definir el problema y la solución):
Empatía → Definición → Ideación → Prototipado → Testeo.

**Metodología ágil — Scrum simplificado** (para organizar el trabajo):
El trabajo se divide en un *Product Backlog* (lista de tareas globales) que se reparte en *Sprints* de 1-2 semanas con una tarea corta y un objetivo funcional cada uno. Al final de cada sprint hay un incremento de producto funcional (hardware o software) y una breve revisión de equipo.

---

## 3. Entregas trimestrales

### Trimestre 1 — Entrega 1: Definición y diseño de la solución

**Fases del proyecto implicadas:** 1. Detección del problema · 2. Búsqueda de información y brainstorming · 3. Diseño de la solución · 4. Planificación y gestión de tareas.

**Herramientas a utilizar:**
- Boceto en papel o digital de la idea (scrapbooking).
- Búsqueda de referencias y componentes disponibles.
- Diagramas UML de apoyo al diseño: casos de uso y diagrama de clases.
- Tinkercad para un primer boceto 3D de la carcasa o estructura, si aplica.
- Tablero Kanban (Trello, Post-its o similar) para organizar el Product Backlog y los sprints del Trimestre 2.

**Qué debes entregar:**
- Descripción del problema/necesidad y la solución propuesta.
- Boceto o esquema de la solución (físico o digital).
- Listado de componentes/tecnologías necesarias.
- Product Backlog inicial repartido en sprints previstos.

---

### Trimestre 2 — Entrega 2: Construcción del producto

**Fases del proyecto implicadas:** 5. Construcción del producto o servicio (comprende el/los sprint/s de electrónica y código, y el de diseño e impresión 3D).

**Herramientas a utilizar:**
- Arduino IDE (o entorno equivalente) para programar el microcontrolador.
- Componentes electrónicos y protoboard para el montaje del circuito.
- Tinkercad para el diseño definitivo de la carcasa o estructura física.
- Cura / PrusaSlicer para laminar el diseño 3D e imprimirlo.

**Qué debes entregar:**
- Circuito funcional montado en protoboard, con el código cargado y probado.
- Pieza o piezas físicas impresas en 3D (o construidas, según el proyecto).
- Registro de los sprints ejecutados (qué se hizo en cada uno).

---

### Trimestre 3 — Entrega 3 (Final): Integración, pruebas y documentación

**Fases del proyecto implicadas:** 6. Pruebas, evaluación y depuración · 7. Documentación técnica y presentación.

**Herramientas a utilizar:**
- Herramientas de montaje (destornillador, pegamento, tornillería) para el ensamblaje final.
- Entorno de pruebas real (condiciones de uso del proyecto) para validar el funcionamiento.
- Editor de documentación (Word, Markdown) para la memoria técnica.
- Herramienta de presentación (PowerPoint o similar) para la defensa final.

**Qué debes entregar:**
- Proyecto integrado y funcionando en condiciones reales.
- Documentación técnica: objetivo, componentes, esquemas, código comentado y conclusiones.
- Presentación final del proyecto ante el resto de la clase.

---

## 4. Diagramas UML de apoyo (según necesidades del proyecto)

| Diagrama UML | Propósito | Cuándo usarlo |
|---|---|---|
| Casos de uso | Representar interacciones entre actores y el sistema | Fase de diseño (Trimestre 1) |
| Diagrama de clases | Modelar la estructura estática del software | Fase de diseño y construcción |
| Diagrama de secuencia | Mostrar interacciones temporales entre componentes | Fase de construcción |
| Diagrama de actividades | Representar el flujo de control del sistema | Fase de diseño |
| Diagrama de estados | Describir los estados posibles de un objeto | Fase de diseño y construcción |
| Diagrama de despliegue | Representar la arquitectura física del sistema | Fase de documentación final |
| Diagrama de flujo | Secuencia lógica de decisiones y acciones | Todas las fases |

---

## 5. Ejemplo de referencia: EcoDrop SMR

Sistema de riego inteligente con Arduino que mide la humedad del suelo y activa un servomotor cuando detecta sequedad. Su desarrollo se organizó en tres sprints, uno por cada bloque de trabajo:

| | Sprint 1: Electrónica y código | Sprint 2: Contenedor físico (3D) | Sprint 3: Integración y test |
|---|---|---|---|
| **Objetivo** | Crear el "cerebro" y la lógica del sistema | Diseñar y fabricar la carcasa protectora | Ensamblar todo y validar el producto final |
| **Herramientas** | Arduino IDE, componentes electrónicos, protoboard | Tinkercad, Cura/PrusaSlicer | Destornillador/pegamento, entorno de prueba real |
| **Entregable** | Circuito funcional que reacciona a la humedad | Pieza física impresa en 3D | Producto terminado, protegido y funcionando |

Puedes tomar esta estructura como modelo para planificar tu propio proyecto, adaptando los sprints y herramientas a la tecnología que elijas.

---

## 6. Ejemplos de proyectos tecnológicos

Elige uno de los siguientes proyectos (o propón una variante y coméntala con el profesor):

1. Sistema de riego automático inteligente
2. Controlador automático de persianas según luminosidad
3. Termostato digital para radiadores
4. Sistema de iluminación inteligente con detección de presencia
5. Sistema de control de acceso básico
6. Parking inteligente con sensores de distancia
7. Sistema de alarma doméstica básica
8. Robot dibujante / plotter sencillo
9. Grúa controlada por joystick
10. Estación meteorológica simple de aula
11. Casa domótica a pequeña escala
12. Mini-cinta transportadora o carrusel de clasificación

---

*Profesor: Ezequiel Llarena Borges*
