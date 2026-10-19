# Can Misses · Ibiza

Seis fotografías aportadas en `Can Misses - Ibiza.zip`. Preparadas como recursos para la web; la asignación a una card o ficha del proyecto se realizará al integrar este contenido.

## Portada y orden

Portada elegida: **fachada**, fotografía original `can_misses_00.webp`. Su encuadre horizontal muestra el conjunto exterior y permite adaptar la composición a una card o cabecera. Punto de encuadre inicial recomendado: `60% 55%`, sujeto a revisión al colocarla en la plantilla.

| Orden | Imagen | Pie de foto |
| --- | --- | --- |
| 1 | `can-misses-fachada` | Fachada de Can Misses. |
| 2 | `can-misses-jardin` | Jardín y fachada de Can Misses. |
| 3 | `can-misses-patio-interior` | Patio interior de Can Misses. |
| 4 | `can-misses-escalera` | Escalera y vegetación en Can Misses. |
| 5 | `can-misses-patio-vista-superior` | El patio de Can Misses visto desde arriba. |
| 6 | `can-misses-acceso-13` | Detalle del acceso a Can Misses. |

## Tamaños y peso

- Tres versiones por fotografía: 480 px, 960 px y una versión mayor con ancho máximo de 1920 px y altura máxima de 1600 px.
- Se mantienen las proporciones y no se amplían las imágenes originales.
- Las seis versiones mayores suman **974,488 bytes**, frente a **1,967,542 bytes** de los archivos recibidos: una reducción del **50.5 %**.
- Las 18 variantes suman 1,752,118 bytes. El navegador debe seleccionar una variante por imagen, no descargar los tres tamaños.
- Todas las versiones se entregan en WebP y sin EXIF ni XMP. Los originales permanecen fuera de la carpeta pública.

## ALT y descripciones

`manifest.json` contiene un ALT específico, un pie de foto y una descripción para cada fotografía, además de dimensiones, tamaños, orden y rutas. Sus descripciones se basan en la imagen y en el nombre del proyecto; no atribuyen materiales, autoría, fecha de obra ni datos técnicos sin confirmar.

Las rutas de las imágenes son relativas a este manifiesto. En GitHub Pages, la base es `/akkobuilding-web/assets/proyectos/can-misses/`; con un dominio servido desde la raíz será `/assets/proyectos/can-misses/`.

## Integración en la página

- La portada visible al abrir la página debe usar la versión adecuada con `srcset`, `sizes` y prioridad alta, sin carga diferida.
- El resto de imágenes debe usar carga diferida, dimensiones declaradas y el ALT del manifiesto.
- La galería horizontal debe conservar una altura visual común, con ancho automático y sin recortar las fotografías para forzar un formato idéntico.
- Los pies y las descripciones pueden mostrarse según el contexto. No se deben repetir todos como contenido visible si no aportan información adicional.

## Créditos y autorización

Los campos de fotógrafo, titular de derechos y texto de crédito están preparados con valor `null`. La autorización consta como `pending`, sin afirmar que se ha concedido. Se completarán proyecto por proyecto. Los avisos pendientes no están destinados a mostrarse como pie de foto en la web.
