# Módulo 2: Panorama UML y Proceso Unificado

> Este módulo introduce el marco general de la materia. No vas a ver todo en detalle durante la cursada —  el tiempo no alcanza — pero es importante que sepas qué existe, para qué sirve cada cosa y dónde podés profundizar.

---

## Bibliografía de referencia

| Autor(es) | Obra | Relevancia |
|-----------|------|------------|
| Booch, G., Rumbaugh, J., Jacobson, I. | *El Lenguaje Unificado de Modelado* (1999). Addison-Wesley | Los creadores de UML. La referencia definitiva. |
| Larman, C. | *UML y Patrones* (2003). Prentice Hall | El libro más usado en ingeniería de software universitaria. Claro y lleno de ejemplos. |
| Pressman, R. | *Ingeniería del Software: Un Enfoque Práctico* (2010). McGraw-Hill | Visión amplia del proceso de desarrollo. Contextualiza UML dentro de la ingeniería. |
| Arlow, J. & Neustadt, I. | *UML 2 and the Unified Process* (2005). Addison-Wesley | El libro que mejor explica cómo UML y el Proceso Unificado se usan juntos en la práctica. |

---

## 0.1 ¿Por qué UML?

Antes de UML, cada metodología de desarrollo tenía su propia notación gráfica. Esto generaba confusión: un diagrama de Booch no era compatible con uno de Jacobson, y los equipos perdían tiempo traduciendo entre notaciones.

En 1994, Booch, Rumbaugh y Jacobson —los llamados "los tres amigos"— unificaron sus metodologías en una sola notación estándar. En 1997, el OMG (Object Management Group) adoptó UML 1.0 como estándar internacional. Hoy, UML 2.x es el lenguaje de modelado de facto en la industria del software.

> *"UML es un lenguaje para visualizar, especificar, construir y documentar los artefactos de un sistema software."*
> — Booch, Rumbaugh, Jacobson (1999)

Pressman (2010) lo describe como "una herramienta de comunicación entre todos los participantes del proceso de desarrollo", no solo entre programadores.

---

## 0.2 Los 14 Diagramas UML

UML define **14 tipos de diagramas** divididos en dos categorías. Es imposible usar todos en un mismo proyecto; la clave está en saber cuál aplicar según el problema.

### Diagramas Estructurales — ¿cómo está construido?

Representan la arquitectura estática del sistema: sus piezas y cómo se organizan.

| # | Diagrama | Qué muestra | Cuándo usarlo |
|---|----------|-------------|---------------|
| 1 | **Clases** | Atributos, métodos y relaciones entre clases | Siempre. Es el diagrama central del análisis y diseño OO. |
| 2 | **Objetos** | Instancias concretas de clases en un momento dado | Para verificar escenarios específicos o ejemplificar relaciones. |
| 3 | **Componentes** | Módulos, librerías y sus interfaces | Cuando se trabaja con arquitecturas de componentes o microservicios. |
| 4 | **Despliegue** | Nodos de hardware y cómo se distribuye el software | Documentar la infraestructura física del sistema. |
| 5 | **Paquetes** | Agrupaciones lógicas de clases o subsistemas | Organizar modelos grandes; definir arquitectura de capas. |
| 6 | **Estructura compuesta** | Partes internas de una clase y sus puertos | Diseñar componentes internamente complejos. |
| 7 | **Perfil** | Extensiones personalizadas de UML | Adaptar UML a un dominio específico (ej. sistemas embebidos, bases de datos). |

> *"El diagrama de clases es el más importante de todos. Si solo vas a aprender uno, ese es."*
> — Larman (2003, p. 78)

### Diagramas de Comportamiento — ¿cómo se comporta?

Representan la dinámica del sistema: qué hace, cómo reacciona, cómo evoluciona en el tiempo.

| # | Diagrama | Qué muestra | Cuándo usarlo |
|---|----------|-------------|---------------|
| 8 | **Casos de uso** | Actores y funcionalidades del sistema | Al inicio del proyecto para capturar requisitos funcionales. |
| 9 | **Actividad** | Flujo de acciones, decisiones y paralelismo | Modelar algoritmos complejos o procesos de negocio. |
| 10 | **Estado** | Ciclo de vida de un objeto y sus transiciones | Objetos cuyo comportamiento depende de su estado (ej. pedido, inscripción). |
| 11 | **Secuencia** | Mensajes entre objetos ordenados en el tiempo | Detallar escenarios de casos de uso paso a paso. |
| 12 | **Comunicación** (Colaboración) | Red de objetos y mensajes sin eje temporal | Ver quién se comunica con quién; alternativa al diagrama de secuencia. |
| 13 | **Temporización** | Cambios de estado en función del tiempo real | Sistemas de tiempo real o con restricciones temporales estrictas. |
| 14 | **Interacción (general)** | Visión de conjunto combinando varios diagramas de interacción | Sistemas muy grandes donde se necesita navegar entre diagramas. |

> *"La elección del diagrama adecuado es una habilidad que se adquiere con la práctica. No existe una regla universal."*
> — Arlow & Neustadt (2005, p. 34)

### ¿Cuáles veremos en la cátedra?

Por razones de tiempo, profundizaremos en cuatro:

| Diagrama | Módulo | Pregunta que responde |
|----------|--------|-----------------------|
| Casos de uso | Módulo 2 | ¿Qué hace el sistema para sus actores? |
| Clases | Módulo 3 | ¿Cómo está estructurado el sistema? |
| Secuencia | Módulo 4 | ¿Cómo interactúan los objetos en el tiempo? |
| Estado | Próxima cursada | ¿Cómo cambia el estado de un objeto a lo largo de su vida? |

El resto existen, son válidos y en muchos proyectos son indispensables. La bibliografía de la materia los cubre; se recomienda leer al menos los capítulos correspondientes en Larman y Arlow.

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

## Referencias completas

- Booch, G., Rumbaugh, J., & Jacobson, I. (1999). *El Lenguaje Unificado de Modelado*. Addison-Wesley.
- Larman, C. (2003). *UML y Patrones: Introducción al Análisis y Diseño Orientado a Objetos y al Proceso Unificado* (2ª ed.). Prentice Hall.
- Pressman, R. S. (2010). *Ingeniería del Software: Un Enfoque Práctico* (7ª ed.). McGraw-Hill.
- Arlow, J., & Neustadt, I. (2005). *UML 2 and the Unified Process: Practical Object-Oriented Analysis and Design* (2ª ed.). Addison-Wesley.
- Jacobson, I., Booch, G., & Rumbaugh, J. (1999). *The Unified Software Development Process*. Addison-Wesley.
- Harel, D. (1987). Statecharts: A visual formalism for complex systems. *Science of Computer Programming*, 8(3), 231–274.

---

*Siguiente módulo → [01: Introducción al Modelado y Análisis](./01_introduccion_modelado_analisis.md)*
