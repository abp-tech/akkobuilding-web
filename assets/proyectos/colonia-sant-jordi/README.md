# Colonia Sant Jordi · Mallorca

Diez archivos recibidos en `Colonia Sant Jordi - Mallorca.zip`; nueve fotografías únicas preparadas para la web. `colonia st jordi_08.webp` tiene exactamente los mismos píxeles que `colonia st jordi_01.webp`, aunque sus metadatos difieren. Se publica una sola copia y se conservan todos los originales fuera de la carpeta pública.

## Portada y galería

Portada elegida: **fachada y escalera exterior**, original `colonia st jordi_01.webp`. La vista horizontal muestra los volúmenes del edificio y la conexión entre sus plantas. El punto de encuadre inicial es centrado, pendiente de revisión al integrarlo en la card o cabecera.

| Orden | Imagen | Pie de foto |
| --- | --- | --- |
| 1 | `colonia-sant-jordi-fachada-escalera-exterior` | Fachada y escalera exterior de Colonia Sant Jordi. |
| 2 | `colonia-sant-jordi-fachada-acristalada` | Fachada acristalada de Colonia Sant Jordi. |
| 3 | `colonia-sant-jordi-terraza-piscina` | Terraza con piscina de Colonia Sant Jordi. |
| 4 | `colonia-sant-jordi-escalera-patio` | Escalera y patio de Colonia Sant Jordi. |
| 5 | `colonia-sant-jordi-rellano-accesos` | Rellano y accesos de Colonia Sant Jordi. |
| 6 | `colonia-sant-jordi-hueco-escalera` | Hueco de escalera de Colonia Sant Jordi. |
| 7 | `colonia-sant-jordi-entrada-jardin` | Entrada ajardinada de Colonia Sant Jordi. |
| 8 | `colonia-sant-jordi-fachada-lateral` | Fachada lateral de Colonia Sant Jordi. |
| 9 | `colonia-sant-jordi-detalle-volumenes` | Detalle de los volúmenes de Colonia Sant Jordi. |

## Optimización

- 27 archivos WebP: tres tamaños por cada una de las nueve imágenes únicas, conservando sus proporciones y sin ampliarlas.
- Variantes menores de 480 px y de 640 o 960 px según el tamaño de la imagen; versión mayor hasta 1920 px de ancho y 1600 px de alto. La terraza con piscina se limita a 1600 × 1200 px para equilibrar detalle y peso.
- Las nueve versiones mayores suman **1,281,780 bytes** frente a **2,843,836 bytes** de las nueve originales únicas: **54.9 % menos**. La copia duplicada no se incluye en esta comparación de compresión.
- El conjunto de las 27 variantes ocupa 2,000,162 bytes. El navegador debe seleccionar una variante por imagen, no descargarlas todas.
- Los archivos publicados no contienen EXIF ni XMP. Los originales se conservan aparte.

## ALT, descripciones y datos pendientes

`manifest.json` incluye ALT, pies de foto, descripciones, orden, portada, dimensiones y rutas para cada fotografía, además del registro del duplicado excluido. Los textos se basan en lo visible y en el nombre del proyecto. Mallorca procede del nombre del ZIP; no se han añadido fechas, autoría ni datos técnicos no confirmados.

Los créditos y el titular de derechos permanecen con valores `null` y estado `pending`. La autorización también consta como `pending`, sin afirmar que se haya concedido. Se completarán proyecto por proyecto y no deben mostrarse como pies provisionales en la web.

## Integración

Las rutas del manifiesto son relativas a este directorio. En GitHub Pages, la base es `/akkobuilding-web/assets/proyectos/colonia-sant-jordi/`; con dominio en la raíz será `/assets/proyectos/colonia-sant-jordi/`.

La portada debe usar la variante adecuada mediante `srcset` y `sizes`, con prioridad alta si es visible al abrir la página. Las fotos posteriores deben usar carga diferida, dimensiones declaradas y el ALT correspondiente.

La galería horizontal debe mantener una altura visual común y ancho automático, respetando las proporciones. Los archivos están listos para asignarlos a la card y ficha del proyecto; subirlos no crea esa ficha automáticamente.
