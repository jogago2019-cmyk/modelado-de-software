# 📚 Modelado de Software — Material de Cátedra

Repositorio con los contenidos teóricos de la materia **Modelado de Software**, organizados en módulos temáticos progresivos. Cada módulo incluye explicaciones, tablas, ejemplos y referencias bibliográficas académicas.

---

## 📋 Índice de Módulos

| # | Módulo | Descripción | Link al Material |
|---|--------|-------------|------------------|
| 01 | **Introducción** | ¿Qué es un modelo? UML, abstracción, objetos y modelos de análisis. | [Ver Módulo](./modulos/01_introduccion/01_introduccion_modelado_analisis.md) |
| 02 | **Proceso Unificado** | Los 14 diagramas UML y las fases del Proceso Unificado (UP). | [Ver Módulo](./modulos/02_proceso_unificado/02_proceso_unificado_panorama_uml.md) |
| 03 | **Casos de Uso** | Actores, escenarios, relaciones Include/Extend y fronteras. | [Ver Módulo](./modulos/03_casos_de_uso/03_casos_de_uso.md) |
| 04 | **Clases** | Atributos, métodos y estereotipos (Entidad, Control, Límite). | [Ver Módulo](./modulos/04_clases/04_clases.md) |
| 05 | **Secuencia** | Interacciones, líneas de vida, mensajes y enfoque de control. | [Ver Módulo](./modulos/05_diagramas_secuencia/05_diagramas_secuencia.md) |

---
## 🗺️ Mapa de Conceptos

```
MODELADO DE SOFTWARE
│
├── 01. Introducción al Modelado y Análisis
│   ├── ¿Qué es un modelo? ¿Por qué modelamos?
│   ├── UML: historia y 4 objetivos (visualizar, especificar, construir, documentar)
│   ├── Abstracción: minimiza la complejidad
│   ├── Ciclo de vida lineal vs orientado a objetos
│   ├── Objetos: estado (atributos) y comportamiento (operaciones)
│   ├── Modelo Conceptual
│   └── Modelo de Análisis: vista estática y vista dinámica
│
├── 02. Proceso Unificado y Panorama UML
│   ├── Los 14 diagramas UML (estructurales y de comportamiento)
│   ├── El Proceso Unificado: iterativo, incremental, dirigido por CU
│   ├── Las 4 fases: Inicio → Elaboración → Construcción → Transición
│   ├── Los 5 flujos: Requisitos, Análisis, Diseño, Implementación, Prueba
│   └── Los 4 diagramas de la cátedra con referencias académicas
│
├── 03. Casos de Uso
│   ├── Comportamiento del sistema y Modelo de CU
│   ├── Actores: propiedades y cómo identificarlos
│   ├── Casos de Uso: definición, instancias y escenarios
│   ├── Pasos: actores → CU → descripción → camino básico → reestructurar
│   ├── Pre/Post-Condición y Camino Básico
│   └── Relaciones: Include (obligatorio) vs Extend (opcional)
│
├── 04. Clases
│   ├── Definición: atributos, operaciones, asociaciones, semántica
│   ├── Nomenclatura PascalCase y Diccionario del Modelo
│   ├── Perspectivas: Conceptual → Especificación → Implementación
│   ├── Estereotipos: <<entity>>, <<boundary>>, <<control>>
│   ├── Clase de Entidad, Límite y Control
│   └── VOPC: Vista de Clases Participantes por RCU
│
└── 05. Diagramas de Interacción y Secuencia
    ├── Tipos: Secuencia (tiempo) vs Colaboración (red)
    ├── Objetos, líneas de vida y mensajes
    ├── Enfoque de Control, Notas y Scripts
    ├── Anatomía completa del diagrama de secuencia
    └── Relación con las Realizaciones de CU (RCU)
```

---

## 🗂️ Estructura del repositorio

```
modelado-de-software/
├── README.md
├── modulos/
│   ├── 01_introduccion/
│   │   ├── 01_introduccion_modelado_analisis.md
│   ├── 02_proceso_unificado/
│   │   ├── 02_proceso_unificado_panorama_uml.md
│   ├── 03_casos_de_uso/
│   │   ├── 03_casos_de_uso.md
│   │   └── img
│   ├── 04_clases/
│   │   ├── 04_clases.md
│   │   └── img
│   └── 05_diagramas_secuencia/
│       ├── 05_diagramas_secuencia.md
│       └── img
```

---

## 📖 Bibliografía de la Materia

- **Booch, G., Rumbaugh, J., & Jacobson, I.** (1999). *El Lenguaje Unificado de Modelado*. Addison-Wesley. — Los creadores de UML. Referencia definitiva.
- **Larman, C.** (2003). *UML y Patrones* (2ª ed.). Prentice Hall. — El libro más usado en la cursada.
- **Pressman, R. S.** (2010). *Ingeniería del Software: Un Enfoque Práctico* (7ª ed.). McGraw-Hill. — Contexto amplio del proceso de desarrollo.
- **Arlow, J., & Neustadt, I.** (2005). *UML 2 and the Unified Process* (2ª ed.). Addison-Wesley. — UML y el Proceso Unificado en la práctica.
- **Jacobson, I., Booch, G., & Rumbaugh, J.** (1999). *The Unified Software Development Process*. Addison-Wesley.

---

*Material elaborado para la Cátedra de Modelado de Software.*
