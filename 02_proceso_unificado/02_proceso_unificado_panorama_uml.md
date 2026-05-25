# Módulo 2: Panorama UML y Proceso Unificado

> Este módulo introduce el marco general de la materia. No vas a ver todo en detalle durante la cursada —  el tiempo no alcanza — pero es importante que sepas qué existe, para qué sirve cada cosa y dónde podés profundizar.

---


## 0.1 ¿Por qué UML?

Antes de UML, cada metodología de desarrollo tenía su propia notación gráfica. Esto generaba confusión: un diagrama de Booch no era compatible con uno de Jacobson, y los equipos perdían tiempo traduciendo entre notaciones.

En 1994, Booch, Rumbaugh y Jacobson —los llamados "los tres amigos"— unificaron sus metodologías en una sola notación estándar. En 1997, el OMG (Object Management Group) adoptó UML 1.0 como estándar internacional. Hoy, UML 2.x es el lenguaje de modelado de facto en la industria del software.

> *"UML es un lenguaje para visualizar, especificar, construir y documentar los artefactos de un sistema software."*
> — Booch, Rumbaugh, Jacobson (1999)

Pressman (2010) lo describe como "una herramienta de comunicación entre todos los participantes del proceso de desarrollo", no solo entre programadores.

---

## 0.3 El Proceso Unificado (UP)

### ¿Qué es?

El **Proceso Unificado** (Unified Process, UP) es un framework de desarrollo de software creado por los mismos autores de UML: Jacobson, Booch y Rumbaugh. Fue publicado en 1999 en el libro *"The Unified Software Development Process"*.

> *"El Proceso Unificado es un proceso de desarrollo de software iterativo, incremental, dirigido por casos de uso y centrado en la arquitectura."*
> — Jacobson, Booch, Rumbaugh (1999)

Arlow & Neustadt (2005) lo describen como "el complemento natural de UML: si UML es el lenguaje, el Proceso Unificado es la gramática que dice cómo usarlo."

### Sus cuatro características fundamentales

**1. Iterativo e incremental**
El desarrollo no ocurre de una sola vez. Se divide en iteraciones cortas (2 a 6 semanas), cada una produciendo un incremento del sistema que puede evaluarse y ajustarse. Pressman (2010) destaca que esto reduce el riesgo al exponer problemas temprano.

**2. Dirigido por Casos de Uso**
Los Casos de Uso son el hilo conductor de todo el proceso. Los requisitos, el análisis, el diseño, la implementación y las pruebas giran alrededor de ellos. Larman (2003) los llama "el mecanismo fundamental para capturar requisitos funcionales en el UP".

**3. Centrado en la arquitectura**
Desde las primeras iteraciones se define una arquitectura base sólida. Arlow & Neustadt (2005) explican que esto evita el problema de descubrir problemas arquitectónicos cuando el sistema ya está casi terminado.

**4. Orientado a riesgos**
Las iteraciones tempranas abordan primero los casos de uso y requisitos de mayor riesgo. Booch et al. (1999) argumentan que "enfrentarse a los riesgos cuando todavía hay tiempo de reaccionar es la clave del éxito de cualquier proyecto de software".

### Las 4 fases del UP

```
Inicio ──→ Elaboración ──→ Construcción ──→ Transición
```

Cada fase puede contener una o más iteraciones:

**Inicio**
Define el alcance y la viabilidad del proyecto. Se identifican los actores y casos de uso principales, se evalúa la viabilidad técnica y económica. Producto: *visión del sistema* y *modelo de casos de uso inicial*.

**Elaboración**
Es la fase más crítica. Se refinan los requisitos, se construye la arquitectura base y se eliminan los riesgos más grandes. Larman (2003) advierte que "si la elaboración falla, el proyecto probablemente falle". Productos: *arquitectura ejecutable*, *modelo de casos de uso completo*, *modelos de análisis y diseño iniciales*.

**Construcción**
Se construye el sistema iterativamente a partir de la arquitectura definida en elaboración. El foco se traslada de análisis a implementación y prueba. Producto: *sistema funcional en versión beta*.

**Transición**
El sistema pasa al ambiente de producción. Incluye pruebas finales, capacitación a usuarios, ajustes de rendimiento y despliegue. Producto: *release final del sistema*.

### Los 5 flujos de trabajo (disciplinas)

El UP organiza las actividades en flujos de trabajo que ocurren durante todo el proyecto, con distinta intensidad según la fase:

| Flujo | Qué produce | Herramienta UML principal |
|-------|-------------|--------------------------|
| **Requisitos** | Modelo de casos de uso, visión del sistema | Diagramas de casos de uso |
| **Análisis** | Modelo de análisis (clases de análisis, realizaciones de CU) | Diagramas de clases, secuencia y colaboración |
| **Diseño** | Modelo de diseño (clases de diseño, arquitectura) | Diagramas de clases, secuencia, estado, componentes |
| **Implementación** | Código fuente, componentes ejecutables | Diagramas de componentes |
| **Prueba** | Casos de prueba, reportes de defectos | Diagramas de actividad |

> *"En el UP, UML no es opcional. Es el lenguaje mediante el cual los equipos piensan, comunican y documentan el sistema a lo largo de todo el proceso."*
> — Arlow & Neustadt (2005, p. 12)

### Relación entre UP y los diagramas de la cátedra

```
FASE DE INICIO          → Diagrama de Casos de Uso
FASE DE ELABORACIÓN     → Diagrama de Clases (Modelo Conceptual y de Análisis)
                          Diagrama de Secuencia (Realizaciones de CU)
                          Diagrama de Estado (objetos con comportamiento complejo)
FASE DE CONSTRUCCIÓN    → Los mismos, más detallados y refinados
```

En esta cátedra cubrimos exactamente el corazón del flujo de Análisis del Proceso Unificado.

---

## 0.4 Los 4 Diagramas de la Cátedra — Resumen

### Diagrama de Casos de Uso
**Pregunta que responde:** ¿Qué hace el sistema para sus actores?

Introducido por Ivar Jacobson en su metodología OOSE (1992), el diagrama de casos de uso se convirtió en el punto de entrada de cualquier proceso de desarrollo orientado a objetos. Larman (2003, p. 56) lo define como "el mecanismo principal para capturar, comunicar y validar los requisitos funcionales del sistema".

Notación básica: actores (figuras de palito), casos de uso (óvalos), relaciones de asociación, include y extend, y la frontera del sistema (rectángulo). Arlow & Neustadt (2005) destacan que "su mayor virtud es que puede ser leído y validado por personas sin formación técnica".

Lo que NO hace: no describe el orden de los pasos, no muestra la lógica interna, no reemplaza la especificación detallada de cada caso de uso.

### Diagrama de Clases
**Pregunta que responde:** ¿Cómo está estructurado el sistema?

Es el diagrama más importante del análisis y diseño orientado a objetos. Booch (1994) lo describe como "el núcleo de todo modelo OO". En el UP, aparece en tres variantes según la perspectiva:

- **Conceptual** (Modelo Conceptual): identifica las abstracciones del dominio sin preocuparse por implementación.
- **Especificación** (Modelo de Análisis): define qué deben hacer las clases, no cómo.
- **Implementación** (Modelo de Diseño): especifica cómo construir las clases en código.

Larman (2003) insiste en que "la perspectiva conceptual es la primera y la más importante; muchos equipos la saltan y pagan el precio más tarde".

Notación básica: rectángulos con tres compartimientos (nombre, atributos, operaciones), relaciones de asociación con multiplicidad, herencia (generalización), composición, agregación y dependencia.

### Diagrama de Secuencia
**Pregunta que responde:** ¿Cómo interactúan los objetos en el tiempo para realizar un caso de uso?

Es el diagrama de interacción más utilizado en el Proceso Unificado para detallar los escenarios de los casos de uso. Arlow & Neustadt (2005, p. 168) lo llaman "el puente entre el modelo de casos de uso y el modelo de clases". Pressman (2010) destaca que "permite identificar responsabilidades y asignarlas a las clases antes de escribir una sola línea de código".

Notación básica: objetos en la parte superior con líneas de vida verticales, mensajes como flechas horizontales (con numeración jerárquica en el UP), enfoque de control (rectángulo sobre la línea de vida), scripts a la izquierda y notas aclaratorias.

### Diagrama de Estado
**Pregunta que responde:** ¿Cómo cambia el estado de un objeto a lo largo de su ciclo de vida?

Basado en los Statecharts de David Harel (1987), adoptados por UML para modelar el comportamiento de objetos cuya respuesta depende de su estado actual. Booch et al. (1999) recomiendan usarlo "para toda clase que tenga un ciclo de vida complejo con múltiples estados distinguibles".

Ejemplos de objetos con estados relevantes: una Inscripción (pendiente, aprobada, rechazada), un Pedido (creado, enviado, entregado, cancelado), una Cuenta (activa, suspendida, cerrada).

Notación básica: estado inicial (círculo negro relleno), estados (rectángulos redondeados), transiciones (flechas con evento[guarda]/acción), estado final (círculo con borde).

> *"No todos los objetos necesitan un diagrama de estado. Solo aquellos cuyo comportamiento varía significativamente según el estado en que se encuentren."*
> — Larman (2003, p. 312)

---

## 0.5 ¿Por qué es importante conocer todos aunque no los veamos todos?

Pressman (2010) plantea que "un ingeniero de software que solo conoce las herramientas que usó en la universidad está mal equipado para el mercado laboral". El objetivo de presentar los 14 diagramas no es que los dominen todos ahora, sino que:

1. **Reconozcan** cuándo un problema requiere un diagrama que no vieron en la cursada.
2. **Sepan dónde buscar**: la bibliografía de la materia cubre los 14.
3. **Entiendan el modelo completo**: los 4 diagramas de la cátedra son coherentes entre sí porque son parte de un sistema más grande — el lenguaje UML y el Proceso Unificado.

Como sintetiza Booch (1999): *"Un modelo incompleto que el equipo entiende es infinitamente más valioso que un modelo completo que nadie usa."*

---

*← [Volver al índice](./README.md)*