# CONVENDUM Palma

Trece fotografías distintas aportadas en `CONVENDUM - Palma.zip`. Las versiones optimizadas se guardan en esta carpeta; la carpeta y el ZIP originales del usuario no se modifican.

## Portada y orden de galería

Portada elegida: **zona de estar junto a la escalera y el arco**, original `convendum_10.webp`. Su composición horizontal y la luz del espacio permiten apreciar el mobiliario, la escalera y la relación con la estancia del fondo. Encuadre inicial centrado, pendiente de revisar al incorporarlo a la card o cabecera.

| Orden | Imagen | Pie de foto |
| --- | --- | --- |
| 1 | `convendum-palma-estar-escalera-arco` | Zona de estar junto a la escalera de CONVENDUM Palma. |
| 2 | `convendum-palma-estar-doble-altura` | Zona de estar de doble altura en CONVENDUM Palma. |
| 3 | `convendum-palma-estar-vista-superior` | La zona de estar de CONVENDUM Palma vista desde arriba. |
| 4 | `convendum-palma-escalera-tramos` | Escalera de CONVENDUM Palma. |
| 5 | `convendum-palma-escalera-detalle` | Detalle de escalera y barandilla en CONVENDUM Palma. |
| 6 | `convendum-palma-salon-marca` | Salón de CONVENDUM Palma. |
| 7 | `convendum-palma-detalle-marca` | Identidad de CONVENDUM en la zona de estar de Palma. |
| 8 | `convendum-palma-barra-servicio` | Barra de servicio de CONVENDUM Palma. |
| 9 | `convendum-palma-trabajo-estar` | Zonas de trabajo y estar de CONVENDUM Palma. |
| 10 | `convendum-palma-mesas-trabajo` | Mesas de trabajo de CONVENDUM Palma. |
| 11 | `convendum-palma-rincon-estar` | Rincón de estar de CONVENDUM Palma. |
| 12 | `convendum-palma-sala-reuniones` | Sala de reuniones de CONVENDUM Palma. |
| 13 | `convendum-palma-acceso-reuniones` | Acceso a la sala de reuniones de CONVENDUM Palma. |

## Optimización y tamaños

- 39 archivos WebP: tres tamaños por fotografía. Las imágenes horizontales se entregan a 480, 960 px y su ancho original de 1919 o 1920 px. Las verticales se entregan a 480, 768 y 1067 px, con altura máxima de 1600 px.
- Se mantienen las proporciones y no se amplían los archivos originales.
- Las trece versiones mayores suman **2,110,200 bytes**, frente a **4,608,506 bytes** de las originales: una reducción del **54.2 %**.
- El conjunto de las 39 variantes ocupa 3,149,036 bytes. El navegador debe seleccionar una variante por foto, no descargar los tres tamaños.
- Los archivos publicados no contienen EXIF ni XMP. Se conservan los originales fuera de la carpeta pública.

## ALT, pies y descripciones

`manifest.json` contiene ALT, pies de foto, descripciones, portada, orden, dimensiones, peso y variantes de cada imagen. Los textos se basan en lo que muestra cada fotografía y el nombre del proyecto; no atribuyen materiales, autoría, fechas o datos técnicos no confirmados. Palma procede del nombre del ZIP.

Las rutas de las imágenes son relativas al manifiesto. En GitHub Pages la base es `/akkobuilding-web/assets/proyectos/convendum-palma/`; con un dominio servido en la raíz será `/assets/proyectos/convendum-palma/`.

## Integración

La portada debe utilizar prioridad alta si aparece al abrir la página y la variante adecuada mediante `srcset` y `sizes`. Las imágenes posteriores deben usar carga diferida, sus dimensiones declaradas y el ALT del manifiesto.

La galería horizontal debe mantener una altura visual común y ancho automático, respetando las proporciones de cada foto. Estos archivos están listos para asignarlos a la card y ficha del proyecto; la subida no crea automáticamente esa ficha.

## Créditos y autorización

Los campos de fotógrafo, titular de derechos y texto de crédito permanecen con valores `null` y estado `pending`; la autorización también figura como `pending`, sin afirmar que haya sido concedida. Se completarán proyecto por proyecto y no deben mostrarse como pies provisionales en la web.
