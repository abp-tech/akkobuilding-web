# Club Chinois

Seis fotografías aportadas en `Club Chinoies.zip`. El nombre del proyecto se ha normalizado como Club Chinois siguiendo los nombres de los archivos originales. No se ha asignado ubicación, fecha ni información técnica sin confirmar.

## Portada y orden

Portada elegida: **salón**, fotografía original `Club_Chinois_03.webp`. La panorámica muestra el diseño interior con asientos rojos, lámparas y el techo curvo. Su composición horizontal funciona como punto de partida para una cabecera o card. El encuadre recomendado es centrado, pendiente de comprobar al integrarlo en la plantilla.

| Orden | Imagen | Pie de foto |
| --- | --- | --- |
| 1 | `club-chinois-salon` | Salón de Club Chinois. |
| 2 | `club-chinois-pista` | La pista de Club Chinois en actividad. |
| 3 | `club-chinois-vista-general` | Vista general de Club Chinois. |
| 4 | `club-chinois-sala-y-barra` | Sala y barra de Club Chinois. |
| 5 | `club-chinois-barra` | Barra de Club Chinois. |
| 6 | `club-chinois-columnas` | Detalle de las columnas de Club Chinois. |

## Tamaños y peso

- Tres versiones por fotografía. Las cuatro originales de 1024 px se entregan a 480, 768 y 1024 px. Las otras dos se entregan a 480, 960 px y su ancho original, 1799 o 1920 px.
- Se conservan las proporciones y no se amplían las imágenes.
- Las seis versiones mayores suman **859,490 bytes**, frente a **1,185,538 bytes** de los archivos recibidos: una reducción del **27.5 %**.
- Las 18 variantes suman 1,377,684 bytes. El navegador debe seleccionar una variante por imagen, no descargar las tres.
- Se entregan en WebP, sin EXIF ni XMP. Se preservan los originales fuera de la carpeta pública.

## ALT y descripciones

`manifest.json` incluye un ALT específico, pie de foto, descripción, dimensiones, peso, variantes, portada y orden. Los textos describen lo visible y el proyecto; no añaden autoría, materiales, fechas ni datos de obra no confirmados.

Las rutas de cada imagen son relativas al manifiesto. En GitHub Pages, la base es `/akkobuilding-web/assets/proyectos/club-chinois/`; con un dominio servido desde la raíz será `/assets/proyectos/club-chinois/`.

## Integración en la web

Los archivos quedan listos para asignarlos a la card y ficha del proyecto. La portada inicial debe usar prioridad alta y la variante adecuada mediante `srcset` y `sizes`. Las imágenes posteriores deben usar carga diferida y dimensiones declaradas.

La galería horizontal debe mantener una altura visual común y ancho automático, conservando las proporciones. No se deben descargar simultáneamente todas las variantes ni forzar el mismo recorte para todas las fotos.

Los créditos permanecen con valores `null` y estado `pending`; la autorización también consta como `pending`. Estos campos se completarán proyecto por proyecto y sus avisos no deben mostrarse como pies provisionales en la web.
