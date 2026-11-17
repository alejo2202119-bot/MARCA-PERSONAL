# Plantilla para Territorio y Gestión

**Agregado:** 7 de septiembre de 2026 · **Documentado:** 17 de noviembre de 2026.

`Dashboard_Plantilla_Marca.html` es una copia del dashboard de Marca Persona (mismo diseño, mismo código, misma conexión a Firestore ya probada) con el contenido reemplazado por placeholders genéricos — sin ningún dato real de Freddy Bernal.

## Cómo la usa cada equipo

Cada equipo (Territorio, Gestión) descarga este archivo, lo adapta con su propio contenido, y cambia solo 3 líneas cerca del inicio del `<script>` (buscar los comentarios `TODO 1/4`, `TODO 2/4`, `TODO 3/4`):

1. `BRAND_NAME` — nombre visible de la marca.
2. `BRAND_SLUG` — exacto: `marca_territorio` o `marca_gestion`. Ya está autorizado en `firestore.rules`; cualquier otro valor produce errores de "permission-denied".
3. `DASHBOARD_PASSWORD` — su propia contraseña.

El `firebaseConfig` ya viene completo (mismo proyecto compartido `marcas-generales`) — no se toca. Los nombres de colección y de campo dentro de `DEFAULT_DATA` tampoco se renombran: son el molde que permite que el panel general (ver `../panel_general/`) lea las tres marcas de forma idéntica.

## Estado al 17 de noviembre de 2026

Las tres marcas ya conectaron y tienen contenido real cargado en Firestore:

- **Marca Gestión** (`marca_gestion`).
- **Marca Territorio** (`marca_territorio`) — símbolo institucional Pino Lazo, mascota Oso Frontino, 5 pilares de contenido.
