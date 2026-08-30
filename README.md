# Pauta al Día

Web app personal para registrar el cumplimiento de la pauta nutricional día a día, pensada para usarse desde el celular (agregada a la pantalla de inicio, funciona como una app).

**App en vivo:** : link xxxx

## Qué hace

- Registro rápido por categoría de alimento (Cereales, Proteína, Fruta, Verduras, Lácteos, Aceites, Frutos secos) en porciones, comida por comida — sin necesidad de detallar cada plato.
- Dos perfiles, **Coni** y **Lorenzo**, cada uno con su propia pauta: comidas, metas por categoría y avance completamente separados entre los dos.
- Auto-selección de la comida según la hora del día, con opción de saltar una comida sin registrar nada.
- Arrastre de porciones pendientes: lo que no se completa en una comida se suma como meta extra a la siguiente, para no perderlo de vista.
- Registro de alimentos "fuera de la pauta" (no cuentan para el cumplimiento, solo quedan anotados).
- Chequeo diario de agua y creatina.
- Vista semanal con % de cumplimiento por categoría y por día.

## Dónde viven los datos

Los datos se guardan en el navegador del celular donde se usa (`localStorage`) — no requieren conexión ni pagar nada. Como viven en el dispositivo, no se sincronizan solos entre celulares distintos.

Como respaldo, la app puede conectarse a un Google Sheet y guardar ahí, en vivo, una copia de cada registro (botón "Conectar con Google" dentro de la app, pide autorización una sola vez). También hay botones para exportar/importar una copia en JSON manualmente.

## Cómo actualizar el sitio

1. Entra al repo en GitHub.
2. "Add file" → "Upload files".
3. Sube el `seguimiento_nutricional.html` actualizado (reemplaza al anterior).
4. Commit changes.

GitHub Pages se actualiza solo con el contenido de la rama `main`, no hace falta ningún paso extra.

## Nota

La pauta nutricional reflejada en la app es personal (de Constanza y Lorenzo, indicada por su nutricionista) — este repo es público en GitHub, pero solo contiene el código de la app, no datos de registro reales (esos quedan en el dispositivo de cada uno, o en el Google Sheet privado de respaldo).
