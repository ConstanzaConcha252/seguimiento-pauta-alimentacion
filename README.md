# Pauta al Día

Web app personal para registrar el cumplimiento de la pauta nutricional día a día, pensada para usarse desde el celular (agregada a la pantalla de inicio, funciona como una app).

**App en vivo:** https://constanzaconcha252.github.io/seguimiento-pauta-alimentacion/seguimiento_nutricional.html

## Qué hace

- Registro rápido por categoría de alimento (Cereales, Proteína, Fruta, Verduras, Lácteos, Aceites, Frutos secos) en porciones, comida por comida — sin necesidad de detallar cada plato. El stepper no deja pasar la meta de esa comida (ni bajar de 0), y una comida ya guardada queda marcada con un ✓ en su chip — reabrirla muestra lo ya registrado (no vuelve a 0) y corregir y volver a guardar reemplaza el valor en vez de duplicarlo.
- Dos perfiles, **Coni** y **Lorenzo**, cada uno con su propia pauta: comidas, metas por categoría y avance completamente separados entre los dos.
- Registro de días anteriores: en la pestaña Registrar hay un selector (‹ ›) para moverse a un día pasado y cargar ahí lo que se te haya olvidado — no afecta el indicador de "hoy" del encabezado, que siempre refleja el día real.
- Auto-selección de la comida según la hora del día (solo cuando el día seleccionado es hoy), con opción de saltar una comida sin registrar nada.
- Arrastre de porciones pendientes: lo que no se completa en una comida se suma como meta extra a la siguiente, para no perderlo de vista.
- Registro de alimentos "fuera de la pauta" (no cuentan para el cumplimiento, solo quedan anotados).
- Chequeo diario de agua y creatina.
- Vista semanal y vista mensual, cada una con su propio selector (‹ ›) para revisar cualquier semana o mes anterior: % de cumplimiento, mapa de calor por categoría y día, promedio por categoría, y lo registrado fuera de la pauta en ese período. La vista mensual además muestra el cumplimiento semana a semana dentro del mes.

## Dónde viven los datos

Los datos se guardan en el navegador del celular donde se usa (`localStorage`) — no requieren conexión ni pagar nada. Como viven en el dispositivo, no se sincronizan solos entre celulares distintos.

Como respaldo, la app puede conectarse a un Google Sheet y guardar ahí, en vivo, una copia de cada registro (botón "Conectar con Google" dentro de la app, pide autorización una sola vez). También hay botones para exportar/importar una copia en JSON manualmente.

## Cómo actualizar el sitio

1. Entra al repo en GitHub.
2. "Add file" → "Upload files".
3. Sube el `seguimiento_nutricional.html` actualizado (reemplaza al anterior) — y `test_live.js` si también se actualizó.
4. Commit changes.

GitHub Pages se actualiza solo con el contenido de la rama `main`, no hace falta ningún paso extra.

## Pruebas automatizadas

`test_live.js` es un script de pruebas (Playwright) que verifica que la app funciona bien: los dos perfiles, el arrastre de porciones, el límite de porciones por meta, que una comida guardada no se pueda duplicar, las pestañas Semana y Mes con sus selectores, el registro de días anteriores, exportar/importar, etc. No hace falta correrlo a mano — está en el repo para que, la próxima vez que se le pida un cambio a Claude, pueda partir de él en vez de armar las pruebas de cero. Para correrlo manualmente (opcional, requiere Node.js y `npm i -g playwright`): `node test_live.js` en la misma carpeta que `seguimiento_nutricional.html`.

## Nota

La pauta nutricional reflejada en la app es personal (de Constanza y Lorenzo, indicada por su nutricionista) — este repo es público en GitHub, pero solo contiene el código de la app, no datos de registro reales (esos quedan en el dispositivo de cada uno, o en el Google Sheet privado de respaldo).
