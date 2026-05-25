# Matriz de Trazabilidad — Sistema Veterinaria

La matriz de trazabilidad permite relacionar los requerimientos funcionales con los distintos artefactos UML desarrollados durante el modelado del sistema.

Esto permite:
- verificar cobertura funcional,
- validar requerimientos,
- identificar impacto de cambios,
- y mantener consistencia entre modelos.

---

| Requerimiento | Caso de Uso | Clases Relacionadas | Diagrama de Secuencia |
|---|---|---|---|
| RF01 Registrar Cliente | Registrar Cliente | Cliente | Registrar Cliente |
| RF02 Registrar Mascota | Registrar Mascota | Cliente, Mascota | Registrar Mascota |
| RF03 Gestionar Turnos | Registrar Turno | Turno, Mascota | Registrar Turno |
| RF04 Registrar Consulta | Registrar Consulta | Consulta, Veterinario, Mascota | Registrar Consulta |
| RF05 Registrar Vacuna | Registrar Vacuna | Vacuna, Mascota | Registrar Vacuna |
| RF06 Registrar Internación | Registrar Internación | Internacion, Mascota | Registrar Internación |
| RF07 Registrar Cirugía | Programar Cirugía | Cirugia, Veterinario | Programar Cirugía |
| RF08 Registrar Servicio Peluquería | Registrar Servicio Peluquería | Mascota, ServicioPeluqueria | Registrar Servicio Peluquería |
| RF09 Registrar Venta | Registrar Venta | Venta, Producto, DetalleVenta | Registrar Venta |
| RF10 Gestionar Productos | Registrar Producto | Producto | Registrar Producto |
| RF11 Generar Reportes | Generar Reporte de Ventas | Reporte | Generar Reportes |

---

# 📌 Importancia de la trazabilidad

La trazabilidad permite mantener alineados:
- requerimientos,
- análisis,
- diseño,
- y comportamiento del sistema.

Además:
- facilita mantenimiento,
- mejora validación,
- y ayuda a controlar cambios futuros en el software.
