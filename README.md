# 📚 Modelado de Software — Material de Cátedra

Repositorio con los contenidos teóricos de la materia **Modelado de Software**, organizados en módulos temáticos progresivos. Cada módulo incluye explicaciones, tablas, ejemplos y referencias bibliográficas académicas.

---

## 📋 Índice de Módulos

| # | Módulo | Descripción |
|---|--------|-------------|
| 01 | [Introducción al Modelado y Análisis](./01_introduccion_modelado_analisis.md) | ¿Qué es un modelo? UML, abstracción, ciclo de vida, objetos (estado y comportamiento), modelo conceptual y modelo de análisis. |
| 02 | [Proceso Unificado y Panorama UML](./02_proceso_unificado_panorama_uml.md) | Los 14 diagramas UML, el Proceso Unificado (UP), sus 4 fases y 5 flujos de trabajo. Los 4 diagramas de la cátedra con referencias a Booch, Larman, Pressman y Arlow. |
| 03 | [Casos de Uso](./03_casos_de_uso.md) | Actores, casos de uso, escenarios, camino básico, pre/post-condición, relaciones Include/Extend y construcción del modelo. |
| 04 | [Clases](./04_clases.md) | Definición, nomenclatura, guía de estilo, diccionario del modelo, perspectivas, estereotipos, clases Entidad/Límite/Control y VOPC. |
| 05 | [Diagramas de Interacción y Secuencia](./05_diagramas_secuencia.md) | Diagramas de secuencia y colaboración, líneas de vida, mensajes, enfoque de control, scripts y notas. |

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
│   │   └── Modulo_01_Introduccion_Modelado.docx
│   ├── 02_proceso_unificado/
│   │   ├── 02_proceso_unificado_panorama_uml.md
│   │   └── Modulo_02_Proceso_Unificado_Panorama_UML.docx
│   ├── 03_casos_de_uso/
│   │   ├── 03_casos_de_uso.md
│   │   └── Modulo_03_Casos_de_Uso.docx
│   ├── 04_clases/
│   │   ├── 04_clases.md
│   │   └── Modulo_04_Clases.docx
│   └── 05_diagramas_secuencia/
│       ├── 05_diagramas_secuencia.md
│       └── Modulo_05_Diagramas_Secuencia.docx
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
