# Marca Persona — Freddy Bernal

Dashboard interno de plan comunicacional, conectado en vivo a Firestore (proyecto Firebase compartido `marcas-generales`, usado también por las marcas Territorio y Gestión).

**Última actualización de este documento:** 17 de noviembre de 2026.

---

## Enlace en vivo

https://htmlpreview.github.io/?https://raw.githubusercontent.com/alejo2202119-bot/MARCA-PERSONAL/claude/brand-dashboard-template-7x7j2t/Dashboard_Plan_Comunicacional_Persona.html

Contraseña de acceso actual: `CAMBIAR-ESTA-CLAVE` (sigue siendo el valor de prueba — pídele a Claude que la cambie por una definitiva antes de repartir el link fuera del equipo).

---

## Estructura de este repositorio

```
.
├── Dashboard_Plan_Comunicacional_Persona.html   ← el dashboard (NO mover ni renombrar)
├── firebase.json                                ← config de Firebase Hosting, apunta a ese archivo
├── firestore.rules                              ← reglas de seguridad (válidas para las 3 marcas)
├── firestore.indexes.json
├── plantilla_para_otras_marcas/                 ← ver su README
└── panel_general/                                ← ver su README
```

`Dashboard_Plan_Comunicacional_Persona.html`, `firebase.json` y `firestore.rules` deben quedarse en la raíz del repositorio: el link público de arriba y la configuración de Firebase Hosting dependen de esa ruta exacta. Si alguno se mueve o renombra, el link deja de funcionar.

---

## Qué hace el dashboard

Una sola página (HTML + CSS + JS, sin frameworks) con 8 secciones: Resumen, Pilares de marca, Plan semanal, Publicaciones especiales, Calendario, Multiplataforma, Métricas & KPIs y Checklist. Todo el contenido se lee en vivo desde Firestore (`onSnapshot`) bajo la colección `marca_personal`, con una pantalla de contraseña que dispara una sesión anónima de Firebase Auth antes de permitir cualquier escritura (botones de estado de KPI, checklist). Si Firestore no responde, sigue funcionando con el último contenido disponible — nunca se rompe ni queda en blanco.

---

## Historial de cambios

**17 de noviembre de 2026**
- Se organizó el repositorio: este README, y uno por cada subcarpeta, documentando qué es cada pieza y cómo se conecta.

**7 de septiembre de 2026**
- Se actualizó todo el contenido de Marca Persona con el **Plan Maestro Consolidado de 70 días** (25 ago – 2 nov 2026, 10 semanas): nuevo calendario, sprint de la Semana 1 (6 piezas), dos piezas nuevas ("La cena que nadie interrumpe" y "Aprendices del campo"), checklist de 8 puntos de validación, KPIs y fases rediseñadas. Escrito directo en Firestore y sincronizado con el respaldo local del archivo.
- Se agregó `panel_general/Dashboard_General_Marcas.html`: panel de solo lectura con 4 secciones (Persona, Territorio, Gestión, Cumplimiento) que lee las tres colecciones de marca en tiempo real y compara su avance — pensado para llevarse a un repositorio aparte.
- Se agregó `plantilla_para_otras_marcas/Dashboard_Plantilla_Marca.html`: la misma plantilla de dashboard con contenido genérico, lista para que los equipos de Territorio y Gestión la adapten a su propia marca.

**25 de agosto de 2026**
- Dashboard de Marca Persona conectado al proyecto Firebase `marcas-generales`: colección renombrada a `marca_personal`, pantalla de contraseña + sesión anónima automática, `firestore.rules` publicado (lectura abierta, escritura con sesión activa) cubriendo las tres marcas.
- Contenido inicial de ejemplo sembrado en Firestore.

**24 de agosto de 2026**
- Primera versión del dashboard de Marca Persona (Freddy Bernal): diseño, las 8 secciones, línea de tiempo de fases, acordeón de pilares, checklist y estado en vivo de KPIs.

---

## Estado de las tres marcas (al 17 de noviembre de 2026)

Las tres ya conectaron y tienen contenido real en Firestore — el panel general (`panel_general/`) puede mostrar las tres sin estados vacíos:

- **Marca Persona** (`marca_personal`) — plan maestro de 70 días, actualizado el 7 de sept.
- **Marca Territorio** (`marca_territorio`) — símbolo Pino Lazo, mascota Oso Frontino, 5 pilares, plan de 80 días (24 ago–11 nov).
- **Marca Gestión** (`marca_gestion`).

## Pendientes

- El propio Plan Maestro Consolidado de Marca Persona recomienda agregar una pestaña de **"Calendario de contenido"** al dashboard (estado por pieza, semáforo de cumplimiento contra el checklist, validación para no repetir una idea en dos semanas) — todavía no construida.
- La contraseña de acceso (`DASHBOARD_PASSWORD` dentro del `<script>`) sigue en su valor de prueba.
- Marca Persona (24 ago–2 nov) y Marca Territorio (24 ago–11 nov) ya no comparten el mismo rango de fechas tras la actualización del plan maestro de Persona — si el panel general necesita una sola línea de tiempo común, cada marca sigue usando sus propias fechas de `periodStart`/`periodEnd`, así que no hay conflicto técnico, pero vale la pena que los tres equipos confirmen si el tramo operativo real es el mismo para los tres.
