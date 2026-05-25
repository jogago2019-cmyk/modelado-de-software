# 🐾 Ejemplo Integrador — Sistema Veterinaria

Este ejemplo integrador presenta el desarrollo completo de un sistema veterinario utilizando UML y análisis orientado a objetos basado en la bibliografía de Jim Arlow.

El objetivo es enseñar cómo analizar un escenario real y construir modelos coherentes a partir de requerimientos y necesidades del dominio.

---

# 📂 Estructura del Ejemplo

| Etapa | Contenido |
|---|---|
| 01 Escenario | Descripción del problema |
| 02 Requerimientos | Funcionales y no funcionales |
| 03 Actores y Casos de Uso | Diagramas UML funcionales |
| 04 Especificación Casos de Uso | Documentación textual |
| 05 Modelo de Dominio | Diagramas de clases |
| 06 Diagramas de Secuencia | Modelado dinámico BCE |
| 07 Diagramas de Estado | Ciclo de vida de objetos |
| 08 Trazabilidad | Relación entre artefactos |


---

# 📌 ¿Cómo recorrer este ejemplo?

Se recomienda seguir el siguiente orden:

1. Leer el escenario.
2. Analizar requerimientos.
3. Identificar actores.
4. Identificar casos de uso.
5. Construir el modelo de dominio.
6. Analizar secuencias.
7. Revisar estados.
8. Validar trazabilidad.

---

# 📌 Objetivo pedagógico

Este ejemplo busca enseñar:
- análisis de escenarios,
- detección de actores,
- identificación de requerimientos,
- modelado UML,
- relaciones entre diagramas,
- y coherencia entre artefactos.
Este ejemplo muestra el desarrollo completo
de un sistema utilizando UML y el enfoque
orientado a objetos basado en Jim Arlow.

---

## Diagramas incluidos

- Casos de uso
- Diagramas de clases
- Diagramas de secuencia
- Diagramas de estado

---

## Convenciones utilizadas

- Boundary
- Control
- Entity
- Frames 

---

## Cómo recorrer el ejemplo

1. Leer escenario
2. Analizar requerimientos
3. Identificar actores
4. Revisar modelo dominio
5. Analizar secuencias
6. Validar coherencia UML

---

## 🧠 Guía: ¿Cómo Identificar Actores, Casos de Uso y Clases en un Escenario?

Uno de los mayores desafíos al comenzar Modelado de Software es aprender a interpretar correctamente un escenario textual.

Muchos de ustedes intentan dibujar diagramas inmediatamente, sin antes comprender:
- quién interactúa con el sistema,
- qué necesita hacer el sistema,
- y cuáles son las entidades importantes del dominio.

Por eso, antes de modelar, es fundamental aprender a analizar el problema.

---

## 🎯 Objetivo de esta guía

Esta guía tiene como finalidad enseñar cómo:
- identificar actores,
- identificar casos de uso,
- identificar clases del dominio,
- y construir modelos coherentes.

---

## 👥 ¿Cómo identificar actores?

### 📌 ¿Qué es un actor?

Un actor representa:
- una persona,
- un sistema externo,
- o una entidad que interactúa con el sistema.

El actor:
- NO pertenece al sistema,
- utiliza el sistema para cumplir un objetivo.

---

### 🧠 Pregunta clave

👉 ¿Quién usa el sistema?

---

### 📖 Ejemplo del escenario

```text
La recepcionista registra turnos para las mascotas.
```

### ✅ Actor identificado

- Recepcionista

Porque:
- interactúa directamente con el sistema.

---

### 📖 Otro ejemplo

```text
El veterinario registra diagnósticos y tratamientos.
```

### ✅ Actor identificado

- Veterinario

---

### ⚠️ Error común: confundir entidades con actores

Por ejemplo:

```text
Mascota
Producto
Turno
```

NO son actores.

Porque:
- no utilizan el sistema,
- son información administrada por el sistema.

---


## 📌 Regla práctica

### Actor = “quien usa el sistema”

### 🎯 ¿Cómo identificar casos de uso?

### 📌 ¿Qué es un caso de uso?

Un caso de uso representa:
- una funcionalidad,
- un objetivo,
- o un servicio que el sistema brinda al actor.

---

### 🧠 Pregunta clave

### 👉 ¿Qué necesita hacer el actor?

---

### 📖 Ejemplo

```text
La recepcionista registra mascotas.
```

### ✅ Caso de uso

- Registrar Mascota

---

### 📖 Otro ejemplo

```text
El veterinario consulta historial clínico.
```

### ✅ Caso de uso

- Consultar Historial Clínico

---

## 📌 Regla práctica

### Caso de uso = “acción importante que el sistema ofrece”

### ✅ Paso 1 — Buscar verbos

Los verbos ayudan a identificar:
- casos de uso,
- funcionalidades.

---

### 📖 Ejemplo

```text
El veterinario registra una consulta.
```

### Verbo identificado

- registrar

### Caso de uso

- Registrar Consulta

---

## 📌 ¿Cómo identificar relaciones «include» y «extend»?

En los diagramas de casos de uso, las relaciones:
- `<<include>>`
- `<<extend>>`

permiten modelar reutilización y comportamiento opcional entre casos de uso.

Muchos suelen confundirlas, por eso es importante entender:
- cuándo un comportamiento es obligatorio,
- y cuándo es opcional.

---

## 🔗 Relación «include»

### 📖 ¿Qué significa?

La relación `<<include>>` representa:
- comportamiento reutilizable,
- obligatorio,
- y compartido entre varios casos de uso.

---

### 🧠 Pregunta clave

### 👉 ¿Este proceso SIEMPRE ocurre?

Si la respuesta es:
- “sí, siempre se ejecuta”,
entonces probablemente sea un `include`.

---

### 📌 Características

| Característica | Include |
|---|---|
| Es obligatorio | ✅ |
| Reutiliza comportamiento | ✅ |
| Reduce duplicación | ✅ |
| El caso base depende del incluido | ✅ |

---

### 📖 Ejemplo — Veterinaria

```text
Registrar Consulta
```

siempre necesita:

```text
Validar Mascota
```

Entonces:

```text
Registrar Consulta <<include>> Validar Mascota
```

---

### 📌 Interpretación

Significa:

> “cada vez que se registra una consulta, obligatoriamente debe validarse la mascota”.

---

### 📌 Otro ejemplo

```text
Registrar Venta
```

incluye:

```text
Calcular Total
```

Porque:
- siempre debe calcularse el total.

---

## 🎯 Regla práctica

### Include = comportamiento obligatorio reutilizable

### ⚠️ Error común: usar include para procesos opcionales

Incorrecto:

```text
Registrar Consulta <<include>> Registrar Observaciones
```

Porque:
- las observaciones podrían ser opcionales.

---

## 🔀 Relación «extend»

### 📖 ¿Qué significa?

La relación `<<extend>>` representa:
- comportamiento opcional,
- alternativo,
- o que ocurre bajo ciertas condiciones.

---

### 🧠 Pregunta clave

### 👉 ¿Este comportamiento ocurre SOLO en algunos casos?

Si la respuesta es:
- “sí”,
entonces probablemente sea un `extend`.

---

### 📌 Características

| Característica | Extend |
|---|---|
| Es opcional | ✅ |
| Depende de una condición | ✅ |
| Amplía comportamiento | ✅ |
| El caso base puede existir solo | ✅ |

---

### 📖 Ejemplo — Veterinaria

```text
Registrar Consulta
```

puede extenderse con:

```text
Registrar Observaciones
```

Entonces:

```text
Registrar Observaciones <<extend>> Registrar Consulta
```

---

### 📌 Interpretación

Significa:

> “durante una consulta podrían registrarse observaciones adicionales”.

Pero:
- la consulta puede existir sin observaciones.

---

### 📖 Otro ejemplo

```text
Generar Reporte
```

puede extenderse con:

```text
Exportar PDF
```

Porque:
- exportar PDF es opcional.

---

## 🎯 Regla práctica

### Extend = comportamiento opcional o condicionado

---

### 📌 Diferencia conceptual importante

| Include | Extend |
|---|---|
| Obligatorio | Opcional |
| Siempre ocurre | Ocurre bajo condición |
| Reutiliza lógica | Amplía comportamiento |
| El caso base depende del include | El caso base NO depende del extend |

---

### 📌 Cómo reconocerlos en un escenario textual

---

## ✅ Indicadores de INCLUDE

Palabras frecuentes:

- siempre
- obligatoriamente
- debe
- requiere
- necesita

---

### 📖 Ejemplo

```text
El sistema debe validar cliente antes de registrar mascota.
```

### Relación detectada

```text
Registrar Mascota <<include>> Validar Cliente
```

Porque:
- validar cliente siempre ocurre.

---

## ✅ Indicadores de EXTEND

Palabras frecuentes:

- opcionalmente
- puede
- eventualmente
- en algunos casos
- si corresponde

---

### 📖 Ejemplo

```text
El veterinario puede registrar observaciones adicionales.
```

### Relación detectada

```text
Registrar Observaciones <<extend>> Registrar Consulta
```

Porque:
- no siempre ocurre.

---

### 📌 Ejemplo comparativo

---

## ✅ Include

```text
Registrar Venta <<include>> Verificar Stock
```

Porque:
- no puede realizarse una venta sin verificar stock.

---

## ✅ Extend

```text
Registrar Descuento <<extend>> Registrar Venta
```

Porque:
- el descuento puede o no aplicarse.

---

### ⚠️ Error MUY común es usar include y extend solo “porque UML lo pide”

Estas relaciones NO se agregan decorativamente.

Deben representar:
- dependencia funcional real,
- reutilización,
- o comportamiento opcional.

---

### 📌 Recomendación importante

Antes de decidir:

## Preguntarse:

### 👉 ¿Esto ocurre siempre?

SI:
- probablemente `include`.

NO:
- probablemente `extend`.

---

### 🎓 Conclusión

Las relaciones:
- `<<include>>`
- `<<extend>>`

permiten construir diagramas de casos de uso más:
- claros,
- reutilizables,
- mantenibles,
- y expresivos.

Comprender correctamente estas relaciones ayuda a modelar mejor los comportamientos del sistema y evitar diagramas ambiguos o inconsistentes.

---

# 🧩 ¿Cómo identificar clases del dominio?

## 📌 ¿Qué es una clase?


Una clase representa:
- un concepto importante del negocio,
- información persistente,
- o entidades relevantes del dominio.

---

### 🧠 Pregunta clave

### 👉 ¿Qué información necesita recordar el sistema?

---

### 📖 Ejemplo

```text
El sistema registra mascotas y consultas.
```

### ✅ Clases identificadas

- Mascota
- Consulta

Porque:
- contienen información relevante.

---

### 📖 Otro ejemplo

```text
El sistema administra productos y ventas.
```

### ✅ Clases identificadas

- Producto
- Venta
- DetalleVenta

---

### ⚠️ Error común confundir acciones con clases

Incorrecto:

```text
Registrar
Gestionar
Buscar
Validar
```

Eso representa:
- comportamientos,
NO entidades.

---

## 📌 Regla práctica

### Clase = “información importante del negocio”

---

### 🔍 Técnica práctica para analizar escenarios

---

### ✅ Paso 1 — Buscar sustantivos

Los sustantivos suelen ayudar a identificar:
- clases,
- actores,
- entidades.

---

### 📖 Ejemplo

```text
El veterinario registra una consulta para una mascota.
```

### Sustantivos encontrados

- veterinario
- consulta
- mascota

---

### ✅ Posibles elementos

| Elemento | Posible tipo |
|---|---|
| Veterinario | Actor |
| Consulta | Clase |
| Mascota | Clase |

---



### ✅ Paso 2 — Identificar relaciones

Luego debe analizarse:
- quién interactúa,
- qué entidades participan,
- y cómo se relacionan.

---

### 📖 Ejemplo

```text
Un cliente puede tener varias mascotas.
```

### Relación identificada

```text
Cliente 1 ----- * Mascota
```

---

## 📌 Cómo identificar asociaciones

---

### 📖 Ejemplo

```text
Una mascota posee muchas consultas.
```

### Asociación

```text
Mascota ----- Consulta
```

---

## 📌 Cómo identificar composición

La composición ocurre cuando:
- una entidad depende totalmente de otra para existir.

---

### 📖 Ejemplo

```text
Una consulta no existe sin una mascota.
```

### Relación

```text
Mascota ♦---- Consulta
```

---

## 📌 Cómo identificar agregación

La agregación ocurre cuando:
- un objeto contiene otros,
- pero esos objetos pueden existir independientemente.

---

### 📖 Ejemplo

```text
Un veterinario participa en cirugías.
```

El veterinario puede existir sin la cirugía.

### Relación

```text
Cirugia ◇---- Veterinario
```

---

## 📌 Cómo identificar herencia

La herencia aparece cuando:
- varias clases comparten características comunes.

---

### 📖 Ejemplo

```text
Veterinario y Recepcionista son empleados.
```

### Herencia

```text
Empleado
   ▲
   │
 ┌─┴─────────┐
Veterinario Recepcionista
```

---

### ⚠️ Error común: crear demasiadas clases

No todo sustantivo debe convertirse en clase.

Por ejemplo:

```text
Sistema
Pantalla
Botón
Formulario
```

no suelen formar parte del dominio.

---

### 📌 Recomendación importante

Antes de modelar:
- entender el negocio,
- identificar objetivos,
- comprender relaciones,
- y recién después construir diagramas.

---

### 🎓 Conclusión

Un buen modelo UML no comienza dibujando diagramas.

Comienza:
- comprendiendo el problema,
- analizando el escenario,
- identificando responsabilidades,
- y modelando el dominio correctamente.

Los diagramas son una representación visual del análisis realizado.
