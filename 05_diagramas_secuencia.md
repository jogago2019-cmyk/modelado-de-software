# Módulo 4: Diagramas de Interacción y Secuencia

---

## 4.1 ¿Qué son los Diagramas de Interacción?

Un **diagrama de interacción** es una representación gráfica de las interacciones o intercambios de mensajes que deben darse entre objetos participantes para completar un Caso de Uso (CU).

### Tipos de diagramas de interacción:

| Tipo | Enfoque |
|------|---------|
| **Diagrama de Secuencia** | Ordenado en el **tiempo** |
| **Diagrama de Colaboración** | Muestra el **flujo de datos** |

Cada uno provee una **vista diferente de las mismas interacciones**. Son complementarios: ambos representan el mismo comportamiento desde ángulos distintos.

---

## 4.2 ¿Qué es un Diagrama de Secuencia?

Un **diagrama de secuencia** sirve para modelar las interacciones entre objetos **ordenadas en una secuencia en el tiempo**.

### Incluye:
- Los **objetos** que participan en el escenario con sus **"líneas de vida"**.
- Los **mensajes** intercambiados en una secuencia en el tiempo que representa el flujo de eventos del escenario.
- El **enfoque del control** sobre los objetos (opcional).

---

## 4.3 Modelo-Vista-Controlador en los Diagramas de Secuencia

Los diagramas de secuencia se alinean naturalmente con el patrón **MVC**:

```
[Usuario] → [Vista/Boundary] → [Controller] → [Model/Entity]
                ←───────────── handleEvent ──────────────
                                    service →
                                    ← getData
              ←─── update ─────────
```

Esto refleja el flujo típico de un escenario:
1. El usuario interactúa con la **Vista** (clase boundary).
2. La Vista dispara eventos al **Controlador** (clase control).
3. El Controlador consulta o modifica el **Modelo** (clase entity).
4. La respuesta retorna al usuario a través de la Vista.

---

## 4.4 Representando Objetos en Diagramas de Secuencia

Los objetos se dibujan como **rectángulos con nombres subrayados** (igual que en otros diagramas UML), en tres formatos posibles:

| Formato | Ejemplo | Descripción |
|---------|---------|-------------|
| Objeto específico | `Ingles 101` | Solo nombre del objeto |
| Objeto específico con clase | `Ingles 101:Curso` | Nombre y clase |
| Objeto genérico | `:Curso` | Solo nombre de la clase |
| Estereotipo (ícono) | (círculo/rectángulo según tipo) | Representación visual del estereotipo |

### Las Líneas de Vida:
Las **"líneas de vida"** de los objetos se muestran como **líneas descendentes intermitentes** y representan el tiempo en que los objetos están instanciados.

```
  :Cliente        :Servidor
     │                │
     │                │      ← Las líneas punteadas
     │                │         son las líneas de vida
     │                │
     ▼                ▼
```

---

## 4.5 Mostrando la Interacción entre Objetos

### Mensajes:
- La interacción se indica con **flechas horizontales** que van de la línea de vida del objeto cliente (que inicia) a la del objeto suplidor (que recibe y responde).
- Las flechas horizontales se etiquetan con la frase que mejor represente el mensaje intercambiado.
- A la etiqueta se le antepone `//` para indicar que se trata de un mensaje en análisis (todavía se está haciendo Análisis).

### Orden temporal:
- El orden de los mensajes en el tiempo se indica por su **posición vertical**: el primer mensaje es el que aparece más arriba.

### Numeración:
La numeración es opcional, pero puede utilizarse para hacer referencia a la numeración jerárquica de los eventos tal como se describen en el Flujo Detallado del CU.

**Ejemplo:**
```
![Diagrama de Secuencia](./img/diagrama secuencia_git.png)
PantallaHorario      ControlInscripcion     ListaDeCursosDisponibles
     │                      │                         │
     │ // 2.2.1.3.2:         │                         │
     │   buscar cursos ────→ │                         │
     │                       │  // 2.2.1.3.3:          │
     │                       │    buscar cursos ──────→│
     │                       │                         │
```

---

## 4.6 ¿Qué es el Enfoque de Control (Focus Control)?

El **Enfoque de Control** representa el tiempo relativo durante el cual el flujo del control se enfoca en un objeto.

- Representa el tiempo en que un objeto está **enviando mensajes y esperando recibir respuestas**.
- Se indica en un diagrama de secuencia dibujando un **rectángulo** sobre la línea de vida del objeto en que está enfocado el control.

```
PantallaHorario     ControlInscripcion    ListaDeCursosDisponibles
     │                     │                        │
     │ // 2.2.1.3.2: ────→ ┌─┐                      │
     │   buscar cursos      │ │ // 2.2.1.3.3: ─────→ │
     │                      │ │   buscar cursos       │
     │                      └─┘                      │
     │ ◄─────────────────── │                        │
         Enfoque de Control
```

---

## 4.7 Notas en los Diagramas de Secuencia

Se pueden usar **notas** para añadirle más información al diagrama cuando se quiere:
- Asegurar que se está comunicando un detalle específico.
- Hacer una aclaración.

Las notas se escriben en **texto libre** y se conectan con línea punteada al elemento al que refieren.

```
PantallaHorario    ControlInscripcion    ListaDeCursosDisponibles
     │                    │                       │
     │ // 2.2.1.3.2:───→ │                        │
     │   buscar cursos    │ // 2.2.1.3.3: ───────→│    ┌──────────────────────┐
     │                    │   buscar cursos        │◄───│ cursos disponibles   │
     │                    │                        │    │ incluyen información │
     │                    │                        │    │ de secciones         │
     │                    │                        │    └──────────────────────┘
```

---

## 4.8 Scripts en Diagramas de Secuencia

Para **escenarios complejos**, los diagramas de secuencia pueden mejorarse mediante el uso de **scripts**.

### Características:
- Un script se escribe **a la izquierda** del diagrama de secuencia, con los pasos del script alineados con las interacciones entre objetos.
- Los scripts se pueden escribir en **lenguaje natural** o en **seudo código**.
- Son muy útiles para representar **estructuras de control** como ciclos o puntos de decisión en el flujo de eventos.

### Ejemplo con script:
```
                          :Estudiante  PantallaDeHorario  ControlInscripcion  :Seccion  :Curso
                               │              │                   │               │         │
Hacer hasta 4 veces            │              │ // 2.2.1.5:       │               │         │
para las opciones              │              │   Someter Horario ─────────────→  │         │
primarias y 2 para             │              │   a Validacion    │               │         │
las alternas                   │              │                   │ // 2.2.1.5.1  │         │
                               │              │                   │  Someter───→  │         │
Hacer hasta 4 veces            │              │                   │               │         │
solo para las                  │              │                   │ // 2.2.1.5.2  │         │
opciones primarias             │              │                   │  Validar que la sección  │
                               │              │                   │  esté Abierta ─────────→ │
Hacer hasta 4 veces            │              │                   │               │         │
para las opciones              │              │                   │ // 2.2.1.5.3  │         │
primarias y 2 para             │              │                   │  Validar que NO haya     │
las alternas                   │              │                   │  conflictos de horario   │
                               │              │                   │               │         │
SCRIPT ◄──────────────────────                                                             
```

---

## 4.9 Anatomía Completa de un Diagrama de Secuencia

El siguiente esquema muestra todos los elementos de un diagrama de secuencia:

```
 Objeto Cliente              Objeto Servidor
 ┌──────────┐               ┌──────────────┐    Numeración
 │ :Cliente │               │  :Servidor   │    Jerárquica
 └──────────┘               └──────────────┘    de Mensajes
      │    ←── Líneas de Vida ──→  │
      │                            │
      │   2.2.1: Ejecutar          │
      │   Responsabilidad ────────→├──┐
      │                            │  │  2.2.1.1: Ejecutar Otra
Este es un                         │  │  Responsabilidad (mensaje
Script de                          │  │  reflexivo: se manda a
Ejemplo   Mensaje                  │  │  sí mismo)
           ↑                       │  │       ↑
           │                       ├──┘  Mensaje Reflexivo
           │                       │
           │                    ┌──┤
           │            Enfoque │  │  ← Enfoque de Control
           │            Control └──┤    (rectángulo sobre la
           │                       │     línea de vida)
```

---

## 4.10 Ejemplo Completo: Diagrama de Secuencia para Login

Este ejemplo muestra el CU "Acceso al Sistema":

```
:Estudiante  :PantallaLogin  :ControlAcceso   :Usuario    :Estudiante
     │              │               │              │            │
     │ // 2.2: Login│               │              │            │
     │ ────────────→│               │              │            │
     │              │ // 2.2.1 Presentar            │            │
     │              │   Pantalla de Login           │            │
     │              │               │              │            │
     │ // 2.2.2: Ingresar identificacion            │            │
     │   (codigoUsuario, password)  │              │            │
     │ ────────────→│               │              │            │
     │              │ // 2.2.3: Validar Identificacion          │
     │              │   (codigoUsuario, password) ─────────────→│
     │              │               │              │            │
     │              │               │ // 2.2.3.1: Validar       │
     │              │               │   Identificacion          │
     │              │               │   (cod, pass): tipoUsr ──→│
     │              │               │              │            │
     │              │               │              │ // 2.2.3.2: Obtener Perfil
     │              │               │              │   Estudiante(codUsr): Estudiante
     │              │               │              │ ─────────────────────────────→
     │              │               │              │            │
     │ // 2.2.4: Mostrar mensaje de Bienvenida(carnet, nombreEstudiante)
     │ ←────────────│               │              │            │
```

---

## 4.11 Diagrama de Colaboración

El **Diagrama de Colaboración** es el otro tipo de diagrama de interacción. A diferencia del diagrama de secuencia, muestra las relaciones entre objetos y el **flujo de mensajes** entre ellos, sin enfatizar el orden temporal explícito.

### Diferencias clave:

| Característica | Diagrama de Secuencia | Diagrama de Colaboración |
|----------------|----------------------|--------------------------|
| Eje principal | **Tiempo** (vertical) | **Relaciones** entre objetos |
| Orden de mensajes | Explícito por posición | Indicado por numeración |
| Énfasis | Flujo temporal | Quién habla con quién |
| Útil para | Entender el flujo paso a paso | Ver la red de comunicación |

---

## 4.12 Relación con la Realización de Casos de Uso

Los diagramas de interacción son parte central de las **Realizaciones de Casos de Uso (RCU)**:

```
[Escenarios de Caso de Uso XX]
           │
           ▼
[Realización de Caso de Uso XX]
     ├── Diagrama de Secuencia  ← describe el CÓMO en el tiempo
     ├── Diagrama de Colaboración ← describe el QUIÉN con QUIÉN
     └── Diagrama de Clases      ← describe la ESTRUCTURA
```

El **Paso 2 del Análisis de CU** consiste precisamente en detallar gráficamente los escenarios de CU en diagramas de interacción para identificar las propiedades y responsabilidades de los objetos y clases.

---

## 4.13 Resumen: Flujo Completo del Análisis

Para cerrar el ciclo, aquí se muestra cómo todos los elementos vistos se conectan:

```
  Descripción        Modelo         Modelo de Análisis
  del Problema  →  Conceptual  ┬──→ (Estático)
  Entrevistas        +         │      • Diagramas de Clases (VOPC)
  Doc. del        Casos de     │      • Diagramas de Paquetes
  Dominio         Uso       ───┤
                  +            └──→ (Dinámico)
  Criterios de    Escenarios          • Diagramas de Secuencia
  Arquitectura                        • Diagramas de Colaboración
                                      • Diagramas de Estado
```

### En cada diagrama de interacción se trabaja con los tres tipos de clases:

| Clase | Estereotipo | Rol en el diagrama de secuencia |
|-------|-------------|--------------------------------|
| Límite | `<<boundary>>` | Recibe los eventos del actor; primer objeto que aparece |
| Control | `<<control>>` | Coordina el flujo; en el centro de los mensajes |
| Entidad | `<<entity>>` | Almacena y retorna datos; al final de la cadena |

---

*← [03: Clases](./03_clases.md)*

---

> **Recursos adicionales sugeridos:**
> - Larman, C. (2003). *UML y Patrones*. Prentice Hall.
> - Booch, G., Rumbaugh, J., & Jacobson, I. (1999). *El Lenguaje Unificado de Modelado*. Addison-Wesley.
> - Jacobson, I. (1992). *Object-Oriented Software Engineering: A Use Case Driven Approach*.
