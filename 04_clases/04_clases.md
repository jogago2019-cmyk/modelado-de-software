# Módulo 3: Clases en el Modelado de Software

---

## 3.1 ¿Qué son las Clases?

Cuando se han identificado muchos objetos en un dominio, decimos que una **clase** es una abstracción que describe un grupo de objetos que tienen:

- **Propiedades en común** (atributos)
- **Comportamiento en común** (operaciones)
- **Relaciones comunes** con otros objetos (asociaciones)
- **Semántica en común** (descripción breve)

### Una clase es una abstracción porque:
- **Enfatiza** características relevantes al sistema.
- **Suprime** otras características no relevantes.

> Así como la abstracción general minimiza la complejidad, las clases permiten manejar grupos de objetos con un solo concepto.

---

## 3.2 Guía para Encontrar Clases

> **Una clase debe capturar una y solo una abstracción principal.**

### Ejemplo:
- ❌ **Mala abstracción**: clase `Estudiante` que incluye el horario del estudiante para el semestre → mezcla dos abstracciones.
- ✅ **Buenas abstracciones**: clases separadas para `Estudiante` y `Horario`.

```
Estudiante                  :Horario
──────────                  ─────────────────────
(atributos                  • Inglés 101 (66574)
 del estudiante)            • Geología 110 (55342)
                            • Historia Mundial 200 (85463)
                            • Álgebra 110 (76453)
```

---

## 3.3 Nombrando las Clases

### Regla principal:
El nombre de una clase debe ser el **sustantivo singular** que mejor caracteriza la abstracción que se quiere representar.

### Señales de alerta:
- El que haya dificultad para nombrar una clase **puede ser indicio de que la abstracción no se entiende bien o no está bien definida**.

### Fuente de los nombres:
Los nombres de las clases deben tomarse **directamente del vocabulario del dominio**:
- Evitar dar nombres "más representativos" a las clases que modelan cosas que ya tienen un nombre difundido en el dominio (ej: usar `OrdenDeTrabajo` en vez de `Ticket`).
- Las mejores fuentes son: entrevistas con expertos del dominio y la documentación propia del dominio (guías de operación, manuales de procedimientos, etc.).
- Los principales términos, siglas, apodos, etc. del vocabulario del dominio, deben definirse e incluirse en la documentación del proyecto (en el RUP se llama a esto el **Documento de Glosario**).

---

## 3.4 Guía de Estilo para Nombrar Clases

El proyecto debe contar con una guía de estilo que dicte convenciones para presentar los nombres de las clases.

### Muestra de una Guía de Estilo:
- Las clases se nombran con **sustantivos en singular**.
- Los nombres de clases **comienzan con mayúscula**.
- El carácter de subrayado **no se usa** para unir palabras.
- Los nombres compuestos de varias palabras se unen y **la inicial de cada palabra se pone en mayúscula** (PascalCase).

### Ejemplos correctos:
```
Estudiante    Profesor    PlanDeEstudios    ControlInscripcion
```

---

## 3.5 Definir la Semántica de la Clase

Luego de nombrar la clase, debe hacerse una **descripción breve y concisa** (Definición de Trabajo o *Working Definition*).

### Reglas para la semántica:
- Enfóquese en el **propósito** de la clase, no en la implementación.
- El nombre de la clase y la descripción forman la base de un **Diccionario del Modelo**.

> **Busque los "QUÉS" e ignore los "CÓMOS"**

---

## 3.6 Muestra del Diccionario del Modelo

El Diccionario del Modelo contiene el nombre y la definición de trabajo de cada clase identificada.

### Ejemplo:

**Nombre:** `Estudiante`
> **Definición de Trabajo:** Información acerca de una persona registrada para realizar diversas actividades en la Universidad (principalmente recibir clases), con el fin de completar los cursos que conforman un Plan de Estudios.

**Nombre:** `Curso`
> **Definición de Trabajo:** Una materia ofrecida por la Universidad, que es parte de un Plan de Estudios.

> *Mientras más del problema se descubre, deben afinarse las definiciones de las clases conocidas y debe agregarse cualquier clase nueva al diccionario.*

---

## 3.7 Representando Clases con UML

Las clases se representan en **Diagramas de Clases**: diagramas que en un mismo plano muestran uno o más iconos, donde cada icono representa una clase específica.

### El ícono de una clase en UML:
Un **rectángulo** que contiene el nombre de la clase y opcionalmente 3 compartimientos:

```
┌─────────────────┐
│    NombreClase  │  ← Compartimiento del nombre
├─────────────────┤
│  atributo1      │  ← Compartimiento de atributos
│  atributo2      │
├─────────────────┤
│  operacion1()   │  ← Compartimiento de operaciones
│  operacion2()   │
└─────────────────┘
```

---

## 3.8 Perspectivas en los Diagramas de Clases

Los diagramas de clases pueden ser desde muy abstractos hasta muy concretos, dependiendo de lo que algunos autores llaman la **"perspectiva"** que se haya tomado al crearlos.

| Perspectiva | Uso | Características |
|-------------|-----|-----------------|
| **Conceptual** | Modelo Conceptual | Modela conceptos puros o abstracciones. Diagramas muy sencillos; solo nombrar las clases. |
| **Especificación** | Modelo de Análisis | Las clases están en el punto medio de ser abstractas y concretas; define qué deben hacer, pero no cómo. Tienen algún grado de complejidad y detalle. |
| **Implementación** | Modelo de Diseño | Las clases son muy concretas; incluyen toda la información de cómo construirlas. Los diagramas son muy detallados y complejos. |

---

## 3.9 Estereotipos (Stereotypes)

Un **estereotipo** es un nuevo tipo de elemento de modelación que extiende la semántica del metamodelo.

- Deben estar basados en tipos existentes o clases del metamodelo.
- Es el **mecanismo que UML provee para extender la notación**.
- **Cada clase de análisis debe tener un estereotipo**.

### Estereotipos comunes:
- Clase de límite (`<<boundary>>`)
- Clase de entidad (`<<entity>>`)
- Clase de control (`<<control>>`)
- Clase de excepción
- Clase de Utilería
- Meta clase

### Representación:
Los estereotipos se muestran en el compartimiento del nombre de la clase encerrado entre `<< >>` (guillemets) o con un icono especial.

```
<<entity>>          <<boundary>>        <<control>>
  Horario           PantallaLogin       ControlAcceso
```

---

## 3.10 Clases de Análisis: Los Tres Estereotipos Principales

Las clases de análisis se clasifican según la metodología **OOSE de Ivar Jacobson** para crear modelos ideales de objetos.

Esta metodología se basa en el patrón de análisis **MVC (Model-View-Controller)**, que define clases enfocadas en la separación de responsabilidades para conseguir componentes extensibles y reutilizables.

```
          Vista (<<boundary>>)
              │
              ▼
         Control (<<control>>)
              │
              ▼
          Modelo (<<entity>>)
```

---

## 3.11 Clase de Entidad (Entity)

Una clase de **entidad** corresponde a las abstracciones principales del Modelo Conceptual y modela la **estructura y comportamiento** asociado a una clase que generalmente es de larga duración (persistente).

- Puede reflejar un fenómeno de la vida real.
- Su comportamiento es **independiente de sus alrededores**.

### Ejemplo:
En el CU "Inscribirse en Cursos", una de las clases de entidad es `Horario`.

```
<<entity>>      O           (icono alternativo)
  Horario    Horario            Horario
```

### Rol de la Clase de Entidad:
> **Almacenar y administrar la información en el sistema.**

---

## 3.12 Clase de Límite (Boundary)

Una clase de **límite** modela la comunicación entre lo que rodea al sistema y su funcionamiento interno.

### Clases de límite típicas:
- Pantallas o interfaces de usuario
- Reportes
- Interfaces programáticos a otros sistemas (APIs)

### Ejemplo:
En el CU "Inscribirse en Cursos", se utiliza una pantalla de horario para que el estudiante ingrese las opciones de cursos → `PantallaDeHorario`.

```
<<boundary>>
PantallaDeHorario
```

### Interfaces con otros Sistemas:
Una clase de límite también se puede usar para modelar una interfaz (API) con otro sistema. Las características importantes son:
- Las **funciones** que provee el otro sistema.
- La **información** a ser pasada al otro sistema.
- El **"protocolo"** de comunicación usado para "hablar" con el otro sistema.

**Ejemplo:** En el CU "Correr Proceso de Cierre" hay información que debe ser enviada a un Sistema de Facturación externo → clase `SistemaDeFacturacion`.

### Rol de la Clase de Límite:
> **Modelar la interacción entre el sistema y sus alrededores.**

---

## 3.13 Encontrando Clases Límite

- Para **cada par de actor físico y escenario** cree una clase de límite.
  - Durante el diseño, esta clase se transformará dependiendo de los mecanismos de interfase escogidos.
- Añada más clases de límite para modelar **navegación entre interfaces** (por ejemplo pantallas) en el mismo caso de uso.

### Ejemplo en el CU "Inscribirse en Cursos":
- Al estudiante se le presentan diferentes opciones → se crea `PantallaInscripción`.
- El estudiante debe ingresar las secciones de los cursos escogidos → se crea `PantallaHorario`.

---

## 3.14 Clase de Control

Una clase de **control** modela **comportamiento de control o coordinación del flujo de eventos** asociado a uno o más CU.

### Características:
- Sirve como **intermediario** entre las clases de límite y las de entidad.
- **Controla la secuencia** o la coordinación de la ejecución del flujo de eventos enviando mensajes a los objetos controlados.
- Controla aspectos de **concurrencia** para las clases controladas.
- **Crea, modifica y elimina** a los objetos controlados.
- La mayoría de las veces es la implementación de un **objeto intangible**.

### Ejemplo:
En el CU "Inscribirse en Cursos", hay una clase `ControlInscripción` que coordina el CU.

### Rol de la Clase de Control:
> **Coordinación del Flujo de los CU.**

---

## 3.15 Encontrando Clases de Control

- Las clases de control contienen información de **secuencia para coordinar los casos de uso**.
- En este nivel de análisis, típicamente se añade **una clase control para cada caso de uso** (es responsable del flujo de eventos en ese CU).
- Las clases de control **NO deben ejecutar funciones** cuya responsabilidad pertenece a clases de entidad o de límite.
- **Esto es sólo un corte inicial**: a medida que se desarrollan más casos de uso y escenarios, las clases de control pueden eliminarse, dividirse o combinarse.

### Ejemplo — Clase de Control para el CU "Inscribirse en Cursos":
Se añade `ControlInscripción` que:
- Recibe información de la clase límite `PantallaHorario`.
- Para cada opción ingresada:
  - Valida que la sección esté abierta.
  - Valida que no existan conflictos de horario.
  - Valida que el curso esté en el plan de estudio del estudiante.
  - Valida que los prerrequisitos se cumplan.
  - Asigna al Estudiante a la Sección.

---

## 3.16 Diagramas de Clases en el Modelo de Análisis

Un **diagrama de clases** muestra una o más clases en un mismo plano, usando la nomenclatura que se ha presentado antes.

### Vista de Clases Participantes (VOPC):
Cada Realización de Caso de Uso tiene uno o más diagramas de clases que muestran las **clases participantes en el CU y sus relaciones**. Estos diagramas son llamados *"View of Participating Classes"* (**VOPC**).

- Los VOPC inician muy sencillos y pueden llegar a ser muy detallados y complejos.
- Por ello se puede necesitar **varios para cada RCU**.

### Ejemplo — VOPC para el CU "Inscribirse en Cursos":
```
<<control>>          <<boundary>>        <<boundary>>
ControlInscripción   PantallaInscripcion  PantallaHorario
      │                    │                   │
      ├──────────────────────────────────────────
      │
<<entity>>    <<entity>>    <<entity>>
  Horario      Sección        Curso

<<entity>>                  <<entity>>
ListadoDeCursosDisponibles  ListaDeEstudiantesInscritos
```

---

## 3.17 Tarjetas Clase-Responsabilidad-Colaboración (CRC)

Las clases también se pueden descubrir usando **tarjetas CRC (Clase-Responsabilidad-Colaboración)**.

- Fueron introducidas por Ward Cunningham y Kent Beck en OOPSLA en 1989.
- Una tarjeta CRC es una **tarjeta de índice de 3 x 5** que muestra:

| Campo | Contenido |
|-------|-----------|
| **Nombre y descripción** | Identidad de la clase |
| **Responsabilidades** | Conocimiento interno + Servicios que brinda |
| **Colaboradores** | Clases cuyos servicios son necesarios para cumplir una responsabilidad |

---

## 3.18 Filtrando Sustantivos (Técnica de Identificación)

Una técnica para encontrar clases es identificar **sustantivos** en la descripción del problema.

### Consideraciones importantes:
- Varios términos pueden referirse al mismo objeto.
- Un término puede referirse a más de un objeto.
- El lenguaje natural es muy ambiguo.

Esto puede llevar a identificar muchos objetos sin importancia, por lo que la **lista de sustantivos debe filtrarse**.

### Advertencia:
- Cualquier sustantivo puede ser convertido en verbo; cualquier verbo puede ser convertido en sustantivo.
- Los resultados dependen en gran parte de la capacidad de redacción de el o los autores.

---

*← [02: Casos de Uso](./02_casos_de_uso.md) | Siguiente módulo → [04: Diagramas de Secuencia](./04_diagramas_secuencia.md)*
