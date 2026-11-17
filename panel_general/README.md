# Panel General — Tres Marcas (solo lectura)

**Agregado:** 7 de septiembre de 2026 · **Documentado:** 17 de noviembre de 2026.

`Dashboard_General_Marcas.html` lee en tiempo real (`onSnapshot`, sin escritura, sin sesión de Firebase Auth) las tres colecciones del proyecto Firebase compartido `marcas-generales`:

- `marca_personal`
- `marca_territorio`
- `marca_gestion`

Cuatro secciones en la barra lateral: una por marca (resumen, estado de KPIs, checklist, línea de tiempo, pilares, plan semanal — todo de solo lectura) y una de **"Cumplimiento"** que compara las tres: % de KPIs en "Bien", desglose por estado, % de checklist completado, y en qué día del plan va cada marca.

## Este archivo vive aquí solo temporalmente

Este dashboard está pensado para desplegarse en **otro repositorio** (el "cuarto dashboard" que consolida las tres marcas para el equipo de dirección). Se mantiene en esta carpeta como fuente de verdad mientras se construye y se prueba contra la base de datos real — cuando se traslade al repositorio definitivo, solo hay que copiar el archivo tal cual; el `firebaseConfig` ya viene completo y no necesita ningún cambio.

Tiene su propia pantalla de contraseña (constante `DASHBOARD_PASSWORD` cerca del inicio del `<script>`), independiente de la de cada marca.
