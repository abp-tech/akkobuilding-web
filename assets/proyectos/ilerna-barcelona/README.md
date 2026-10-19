# ILERNA Barcelona

Siete fotografías distintas aportadas en `Ilerna - Barcelona.zip`. Las variantes optimizadas se guardan en esta carpeta. La carpeta y el ZIP originales del usuario permanecen sin cambios.

## Portada y galería

Portada elegida: **mostrador y escalera**, original `ilerna_barcelona_05.webp`. La composición horizontal muestra la relación entre el mostrador, el recorrido y la escalera. Encuadre inicial centrado, pendiente de comprobar al integrarlo en la card o cabecera.

| Orden | Imagen | Pie de foto |
| --- | --- | --- |
| 1 | `ilerna-barcelona-mostrador-escalera` | Mostrador y escalera de ILERNA Barcelona. |
| 2 | `ilerna-barcelona-pasillo-acceso` | Pasillo de acceso de ILERNA Barcelona. |
| 3 | `ilerna-barcelona-escalera-frontal` | Vista frontal de la escalera de ILERNA Barcelona. |
| 4 | `ilerna-barcelona-detalle-techo` | Detalle del techo de ILERNA Barcelona. |
| 5 | `ilerna-barcelona-espacio-columnas` | Espacio de distribución de ILERNA Barcelona. |
| 6 | `ilerna-barcelona-sala-sillones` | Sala con sillones de ILERNA Barcelona. |
| 7 | `ilerna-barcelona-sala-espera` | Sala de espera de ILERNA Barcelona. |

## Tamaños y optimización

- 21 archivos WebP: tres tamaños por cada fotografía, conservando su proporción y sin ampliar los originales.
- Las imágenes de 1600 px se entregan a 480, 960 y 1600 px de ancho. Las demás se entregan a 480, 768 px y su ancho original de 900, 944 o 1200 px.
- Las siete versiones mayores suman **703,538 bytes**, frente a **978,322 bytes** de los originales: una reducción del **28.1 %**.
- Las 21 variantes suman 1,174,714 bytes. El navegador debe seleccionar una variante por imagen, no descargar los tres tamaños.
- Los archivos publicados no contienen EXIF ni XMP; se conservan los originales fuera de la carpeta pública.

## ALT y descripciones

`manifest.json` recoge un ALT específico, pie de foto, descripción, portada, orden, dimensiones, peso y variantes para cada imagen. Los textos describen lo visible y el nombre del proyecto, sin añadir autoría, materiales, fechas ni datos técnicos no confirmados. Barcelona procede del nombre del ZIP.

Las rutas de las imágenes son relativas al manifiesto. En GitHub Pages, la base es `/akkobuilding-web/assets/proyectos/ilerna-barcelona/`; con un dominio servido en la raíz será `/assets/proyectos/ilerna-barcelona/`.

## Integración

La portada visible al abrir la página debe utilizar prioridad alta y la variante adecuada mediante `srcset` y `sizes`. Las imágenes posteriores deben usar carga diferida, dimensiones declaradas y el ALT correspondiente.

La galería horizontal debe conservar una altura visual común y ancho automático, sin forzar un recorte idéntico en todas las fotos. Los archivos están listos para asignarlos a la card y ficha del proyecto; su subida no crea automáticamente esa ficha.

## Créditos y autorización

Fotógrafo, titular de derechos y texto de crédito se mantienen con valores `null` y estado `pending`. La autorización también consta como `pending`, sin afirmar que se haya concedido. Se completarán proyecto por proyecto y no deben mostrarse como pies provisionales en la web.
