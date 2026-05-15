# Módulo 1: Introducción al Modelado de Software y Análisis

---

## 1.1 ¿Qué es un Modelo?

> **"Un modelo es una abstracción de la realidad"**

Un modelo de software es una **simplificación de la realidad** que nos permite comprender, comunicar y razonar sobre un sistema sin tener que lidiar con toda su complejidad a la vez.

### Características de un modelo:
- Proporciona un **plano** del sistema a construir.
- Incluye los aspectos importantes del sistema y omite los elementos menores que no son relevantes.
- Cada modelo permite fijarnos en un **aspecto distinto** del sistema.

---

## 1.2 ¿Por qué Modelamos?

Construimos modelos de sistemas complejos porque **no podemos comprender el sistema en su totalidad** de una sola vez.

### Razones principales:
- Hay **límites de la capacidad humana** para comprender la complejidad.
- A través del modelado se reduce el problema que se está estudiando, concentrándose en un solo aspecto a la vez *(divide y vencerás)*.

### ¿Para qué sirven los modelos?
- **Visualizar** cómo queremos que sea un sistema.
- **Especificar** la estructura o el comportamiento de un sistema.
- **Guiar** la construcción del sistema.
- **Documentar** las decisiones que hemos adoptado.

---

## 1.3 ¿Qué es UML?

**UML (Unified Modeling Language)** es un lenguaje estándar para escribir planos de software. Permite **modelar, construir y documentar** los elementos que forman un sistema software orientado a objetos.

### Características de UML:
- Tiene una **notación gráfica muy expresiva** que permite representar en mayor o menor medida las fases del proyecto.
- Indica cómo se pueden **crear y leer modelos**.
- Puede usarse en las **diferentes etapas del ciclo de vida** del desarrollo.

### Objetivos de UML:

| Objetivo | Descripción |
|----------|-------------|
| **1. VISUALIZAR** | Facilita la comunicación entre desarrolladores y la comprensión de soluciones mediante notación gráfica |
| **2. ESPECIFICAR** | Permite construir modelos precisos y completos; cubre decisiones de análisis y diseño |
| **3. CONSTRUIR** | Sus modelos pueden conectarse directamente a lenguajes como Java o C++ |
| **4. DOCUMENTAR** | Los elementos gráficos sirven como documentación del sistema para su futura revisión |

---

## 1.4 Abstracción

### ¿Qué es la Abstracción?

Es la capacidad de **conceptualizar entidades genéricas de información a partir de cosas concretas**.

- Se enfatizan las **características comunes** que interesan.
- Se **ignoran** otras características que no son relevantes para el problema.

> **La Abstracción Minimiza la Complejidad.**

### Ejemplo:
En un *Sistema de Procesamiento de Órdenes*, las abstracciones principales son:
- **Cliente** → quién realiza la orden
- **Producto** → qué se ordena
- **Vendedor** → quién procesa la orden

Cada uno captura solo lo esencial de esa entidad en el contexto del sistema.

---

## 1.5 Ciclo de Vida del Software

### Ciclo de Vida Lineal (Clásico)

El ciclo de vida lineal sigue una secuencia de fases donde cada una debe completarse antes de pasar a la siguiente:

```
Captura de requisitos → Análisis → Diseño → Implementación → Debugging → Validación
```

**Fases:**
- **Análisis**: Determinar los elementos que intervienen — estructura, relaciones, funcionalidades.
- **Diseño**: Decidir cómo vamos a desarrollar el sistema; seleccionar el lenguaje y definir en detalle entidades y relaciones de BD.
- **Implementación**: Escribir el código fuente.
- **Debugging y Validación**: Verificar que el sistema funcione correctamente.

### Ciclo de Vida Orientado a Objetos

Presentado en la década de los '90, en este ciclo **cada funcionalidad o requerimiento se modela a través de objetos**.

- Los objetos están representados por un conjunto de **propiedades o atributos**.
- Al comportamiento que tendrán estos objetos lo denominamos **métodos**.

#### Modelado de Dominio:
Contiene los conceptos y sus relaciones que sean significativos en el dominio del problema.

```
Realidad → Modelo (Diagrama de Clases) ← La información proviene de los Casos de Uso
```

---

## 1.6 El Modelo de Análisis

El Modelo de Análisis es **el resultado del proceso de Análisis**. Representa la conceptualización del Dominio del Problema.

### ¿Cómo se construye?
Para construirlo se hace el **"Análisis de Casos de Uso"**, que toma como base:
- El **Modelo de Casos de Uso**.
- El **Modelo Conceptual** de clases.
- La documentación disponible (descripción del problema, especificaciones suplementarias, entrevistas, etc.).
- Los **escenarios de CU** para ordenar, dirigir y ejecutar el proceso.

> Del Modelo Conceptual, se usan directamente algunas clases, otras se transforman y algunas se desechan.

### Dos vistas del Modelo de Análisis:

#### Vista Estática (estructura):
- Diagramas de Clases
- Diagramas de Paquetes

#### Vista Dinámica (comportamiento e interacciones):
- **Diagramas de Interacción**
  - Diagramas de Secuencia
  - Diagramas de Colaboración
- Diagramas de Estado

---

## 1.7 ¿Qué es el Análisis de Casos de Uso?

Es la **primera etapa para crear las "Realizaciones de Casos de Uso"**.

El análisis de casos de uso es el proceso de **examinar los casos de uso para descubrir los objetos y clases del sistema** a desarrollar (Clases de Análisis).

### Para estas clases deben identificarse:
- Su **estructura** (propiedades/atributos)
- Su **comportamiento** (responsabilidades/operaciones)
- Sus **relaciones** con otras clases

### Las clases deben agruparse en paquetes según criterios de **Arquitectura de Software**, donde se identifican los primeros candidatos para componentes.

> **Las clases de análisis son el primer paso hacia componentes ejecutables.**

---

## 1.8 ¿Cómo se hace el Análisis de Casos de Uso?

### PASO 1: Identificar clases participantes
Los escenarios de CU se analizan para identificar los objetos y clases que participan en ellos:
- Se definen objetos y clases de **entidad, límite y control**.
- Se crean **diagramas de clases participantes (VOPC)** para cada Realización de Caso de Uso.

### PASO 2: Detallar con diagramas de interacción
Los escenarios de CU se detallan gráficamente en **diagramas de interacción** para identificar las propiedades y responsabilidades de los objetos y clases:
- Se establece **cuándo y por qué** se comunican entre sí los objetos y clases.
- Se identifica **qué información** contienen los mensajes que se envían.
- Se definen y asignan **propiedades (atributos) y responsabilidades (operaciones)**.

### PASO 3: Identificar relaciones entre clases
Se identifican y dibujan relaciones entre clases en los diagramas VOPC para afinar y detallar la definición de las clases participantes (relaciones de asociación, agregación, generalización).

### PASO 4: Detallar clases con comportamiento especial
Algunas clases con comportamiento especial se detallan en **diagramas de estado** para afinar la definición de sus atributos y operaciones.

### PASO 5: Agrupar en paquetes
Las clases resultantes se agrupan en paquetes tomando criterios de Arquitectura de Software para la definición de componentes.

---

## 1.9 ¿Qué es una Realización de Casos de Uso (RCU)?

Una **RCU** describe cómo un escenario de un CU es realizado por varios objetos colaborando entre sí. Esto se representa con:
- Diagramas de Secuencia
- Diagramas de Colaboración
- Diagramas de Clases

### Ciclo de vida de una RCU:
1. La definición **inicia** con el Análisis de Casos de Uso (para el Modelo de Análisis).
2. La definición **se completa** con el Diseño de Casos de Uso (para el Modelo de Diseño).
3. El **objetivo final** es especificar qué clases deben construirse para implementar ese CU.

### Representación en UML:
En UML, una RCU se muestra como un **óvalo con línea punteada**, asociado al caso de uso que realiza, con una flecha de línea punteada y cabeza cerrada.

```
[Caso de Uso XX] ◁- - - - - [Realización de Caso de Uso XX]
                                    ├── Diagrama de Secuencia
                                    ├── Diagrama de Colaboración
                                    └── Diagrama de Clases
```

---

## 1.10 Objetos: Estado y Comportamiento

### Un Objeto tiene Estado

El **estado** de un objeto es una de las posibles condiciones en que un objeto puede existir.

- El estado normalmente **cambia con el tiempo**.
- Es usualmente implementado por un conjunto de **propiedades llamadas atributos**, más los enlaces que el objeto pueda tener con otros objetos.
- El estado lo establecen los **valores de los atributos y enlaces**.

**Ejemplo — Objeto `Profesora Clark`:**
```
Nombre:        Joyce Clark
Id Empleado:   4322456
Contratación:  01/06/1995
Puesto:        Profesora Titular
```

### Un Objeto tiene Comportamiento

El **comportamiento** determina cómo un objeto actúa y reacciona.

- Define la manera en la que un objeto **responde a las peticiones** de otros objetos.
- El comportamiento visible se modela con un conjunto de **mensajes a los que puede responder**.
- Los mensajes se implementan como las **operaciones del objeto**.

**Ejemplo:**
```
[Oficial de Registro Jiménez] --Asignar a Profesora Clark a dar Cálculo Integral 332--> [Profesora Clark]
                              <--(Devuelve: confirmación)-----------------------------
```

---

## 1.11 Representando Objetos con UML

Los objetos se representan en UML como **rectángulos con el nombre subrayado**.

El nombre puede presentarse en tres formatos:

| Formato | Ejemplo | Uso |
|---------|---------|-----|
| Solo nombre del objeto | `Joyce Clark` | Objeto específico |
| Nombre de clase y objeto | `Joyce Clark:Profesor` | Objeto específico con clase |
| Solo nombre de clase | `:Profesor` | Objeto genérico |

---

## 1.12 El Modelo Conceptual

Es el **primer modelo de clases** que se debe hacer y reúne las **abstracciones principales (key abstractions)** del sistema que se desea construir.

### Características:
- Es un primer intento de **definir la estructura** del sistema.
- Se obtiene al examinar la **descripción del problema** y en entrevistas con los expertos del dominio.
- Se usa como una base de entendimiento y cooperación con los **expertos de dominio y/o clientes**.
- **No debe incluir los detalles** de las clases, solo debe identificarlas.

### Incluye:
- Un **Diccionario del Modelo**
- Uno o más **Diagramas de Clases** (normalmente solo uno)

---

*Siguiente módulo → [02: Casos de Uso](./02_casos_de_uso.md)*

---

## 1.13 Los 14 Tipos de Diagramas UML

UML define **14 tipos de diagramas** organizados en dos grandes categorías.

---

### Diagramas Estructurales (7)
> Responden: **¿cómo está construido el sistema?**

| Diagrama | Qué muestra | Uso típico |
|----------|-------------|------------|
| **Clases** | Atributos, métodos y relaciones entre clases | Modelo conceptual y de análisis |
| **Objetos** | Instancias concretas de clases en un momento dado | Verificar escenarios específicos |
| **Componentes** | Módulos, librerías y sus dependencias | Arquitectura de software |
| **Despliegue** | Hardware, nodos y cómo se despliega el software | Infraestructura del sistema |
| **Paquetes** | Agrupaciones lógicas de clases o componentes | Organización del modelo |
| **Estructura compuesta** | Partes internas de una clase y sus conectores | Diseño de componentes complejos |
| **Perfil** | Extensiones y estereotipos personalizados de UML | Adaptar UML a un dominio específico |

**En esta cátedra usamos:** Diagrama de Clases (Módulo 3), Diagrama de Paquetes (Arquitectura), Diagrama de Objetos (escenarios).

---

### Diagramas de Comportamiento (7)
> Responden: **¿cómo se comporta el sistema en ejecución?**

| Diagrama | Qué muestra | Uso típico |
|----------|-------------|------------|
| **Casos de uso** | Actores y funcionalidades del sistema | Captura de requisitos |
| **Actividad** | Flujo de acciones y decisiones (similar a un flowchart) | Modelar algoritmos y procesos |
| **Estado** | Ciclo de vida de un objeto y sus transiciones | Objetos con comportamiento complejo |
| **Secuencia** | Mensajes entre objetos ordenados en el tiempo | Detallar escenarios de CU |
| **Colaboración** | Red de objetos y mensajes (sin eje temporal) | Ver quién habla con quién |
| **Temporización** | Cambios de estado en función del tiempo real | Sistemas de tiempo real |
| **Interacción (general)** | Visión general combinando varios diagramas | Sistemas muy complejos |

**En esta cátedra usamos:** Casos de Uso (Módulo 2), Secuencia y Colaboración (Módulo 4), Estado (comportamiento de objetos).

---

## 1.14 Ejemplos de los Diagramas Principales de la Cátedra

### Ejemplo 1 — Diagrama de Clases
Muestra atributos, operaciones y relaciones entre clases. Usa 3 compartimientos: nombre, atributos y operaciones.

```
┌────────────────────┐         ┌────────────────────┐         ┌────────────────────┐
│    Estudiante      │  1    1 │      Horario        │  1  0..* │     Seccion        │
├────────────────────┤─────────├────────────────────┤──────────├────────────────────┤
│ - legajo: String   │         │ - semestre: String  │          │ - codigo: String   │
│ - nombre: String   │  tiene  │ - anio: int         │ contiene │ - cupo: int        │
│ - email: String    │         │                     │          │ - abierta: boolean │
├────────────────────┤         ├────────────────────┤          ├────────────────────┤
│ + inscribirse()    │         │ + agregar(s:Seccion)│          │ + validar()        │
└────────────────────┘         └────────────────────┘          └────────────────────┘
```

**Relaciones posibles:** asociación (→), agregación (◇→), composición (◆→), herencia (▷), dependencia (- - →)

---

### Ejemplo 2 — Diagrama de Casos de Uso
Muestra los actores y las funcionalidades del sistema y sus relaciones.

```
                     ┌─────────────────────────────────────┐
                     │    Sistema de Inscripción           │
  👤                 │                                     │                 👤
Estudiante ──────────│──→ ( Inscribirse en cursos )        │    Encargado
           ──────────│──→ ( Ver horario )                  │──────────────→ ( Autorizar inscripción )
                     │              │                      │
                     │      «include»│                     │
                     │              ▼                      │
                     │  (- - - Validar prerrequisitos - -) │
                     └─────────────────────────────────────┘
```

---

### Ejemplo 3 — Diagrama de Secuencia
Muestra los mensajes entre objetos ordenados **en el tiempo** (de arriba hacia abajo).

```
:Estudiante   :PantallaHorario   :ControlInscripcion   :Seccion
     |               |                   |                  |
     |─── t1: abrir horario ────────────►|                  |
     |               |─── t2: someter horario ─────────────►|
     |               |                   |── t3: validar() ─►|
     |               |                   |◄── t4: ok ────── |
     |               |◄── t5: confirmacion ─────────────────|
     |◄── t6: mostrar resultado ─────────|                  |
```
Las líneas punteadas verticales son **líneas de vida**. El rectángulo sobre la línea es el **enfoque de control**.

---


*← [Volver al índice](./README.md)*
