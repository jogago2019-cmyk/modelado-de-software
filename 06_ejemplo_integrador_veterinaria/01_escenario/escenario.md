# 🐾 Escenario del Sistema Veterinaria

## 📖 Descripción General

La veterinaria “Patitas Felices” necesita implementar un sistema de gestión integral para informatizar sus procesos administrativos y clínicos.

Actualmente, gran parte de la información se registra manualmente, lo que provoca:
- pérdida de información,
- demoras en atención,
- errores en turnos,
- dificultades para controlar stock,
- y poca trazabilidad del historial médico de las mascotas.

El sistema deberá permitir administrar:
- clientes,
- mascotas,
- consultas veterinarias,
- turnos,
- vacunación,
- internaciones,
- cirugías,
- peluquería,
- ventas de productos,
- y generación de reportes.

---

# 👥 Usuarios del sistema

Los actores que interactúan con el sistema son:

- Recepcionista
- Veterinario
- Peluquero
- Cajero
- Administrador

---

# 🐶 Gestión de Mascotas

La veterinaria necesita registrar:
- datos del cliente,
- datos de la mascota,
- especie,
- raza,
- edad,
- peso,
- historial clínico,
- vacunas aplicadas,
- tratamientos,
- alergias,
- y observaciones médicas.

Cada mascota pertenece a un cliente.

Un cliente puede tener varias mascotas.

---

# 📅 Gestión de Turnos

La recepcionista deberá:
- registrar turnos,
- consultar disponibilidad,
- cancelar turnos,
- reprogramar turnos.

Los turnos estarán asociados:
- a una mascota,
- un veterinario,
- fecha,
- horario,
- y estado.

---

# 🩺 Gestión de Consultas

El veterinario podrá:
- registrar consultas,
- diagnósticos,
- tratamientos,
- observaciones,
- recetas,
- y controles médicos.

Cada consulta quedará asociada a una mascota.

---

# 💉 Gestión de Vacunas

El sistema deberá permitir:
- registrar vacunas aplicadas,
- calcular próximas dosis,
- consultar historial de vacunación,
- y actualizar carnet sanitario.

---

# 🏥 Gestión de Internaciones

El veterinario podrá:
- registrar internaciones,
- registrar evolución diaria,
- indicar medicación,
- y registrar alta médica.

---

# 🔪 Gestión de Cirugías

El sistema deberá permitir:
- programar cirugías,
- asignar veterinarios,
- registrar observaciones preoperatorias,
- y registrar resultados quirúrgicos.

---

# ✂️ Gestión de Peluquería

El peluquero podrá:
- registrar servicios realizados,
- baño,
- corte,
- limpieza,
- y observaciones.

---

# 🛒 Gestión de Ventas

El cajero podrá:
- registrar ventas,
- seleccionar productos,
- emitir comprobantes,
- controlar stock,
- y calcular importes.

---

# 📦 Gestión de Productos

El administrador podrá:
- registrar productos,
- actualizar stock,
- modificar precios,
- y consultar disponibilidad.

---

# 📊 Reportes

El administrador podrá generar:
- reportes de ventas,
- reportes de turnos,
- reportes de productos,
- reportes de mascotas atendidas,
- y estadísticas generales.

---