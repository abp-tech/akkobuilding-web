# AKKO Building · Visual Gauntlet

Fecha: 20 de octubre de 2026. Rama: `fix/visual-gauntlet-akko`.

Se conserva el contenido adaptado: comparación de los nodos de texto de `main` antes y después en las 53 rutas, sin diferencias. Se mantienen fotografías, enlaces y estados de demostración. No se traducen ni sustituyen textos pendientes.

## Hallazgos y correcciones

| Página / Componente | Breakpoint (Dispositivo) | Tipo de Fallo | Descripción del Problema | Estado | Cambio Aplicado en Código |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Utilidad tipográfica compartida | Todos | Tipografía / Mantenimiento | La familia ya estaba sustituida, pero las clases seguían denominándose `font-PPFraktionMono`, incluso en plantillas y generadores. | Corregido | Renombradas a `font-ibm-mono` en HTML, CSS, JS y registros de tarjetas. Cero referencias heredadas en los recursos desplegables. |
| Contenedores de texto y pies de foto | Todos | Tipografía | Algunos `div` con texto directo y `figcaption` carecían de variante y dependían de tamaños de las hojas antiguas. | Corregido | `normalize-typography.py` asigna `meta` y `caption`; IBM Plex Mono 400, 14px/1.4 y 12px/1.4 respectivamente, con tracking 0. Los párrafos conservan su variante de cuerpo o lead. |
| Todas las plantillas | 375 / 430 / 768 / 1024 / 1440 / 1920px | Alineación / Espaciado | A 1024px, Servicios comenzaba en 56.32px, Sectores y Noticias en 94.4px y Empresa en 120px. | Corregido | `layout-contract.css` centraliza los márgenes de inicio y final. Las secciones y los textos de las fotografías usan la misma retícula; las imágenes siguen a sangre. |
| `proyectos/` y tarjetas regeneradas | Todos | Jerarquía HTML | El catálogo pasaba de H1 a H3 en los títulos de las obras. | Corregido | Tarjetas de catálogo como H2 con variante visual `card`. Actualizados normalizador, generador y `cards.json`, manteniendo el tamaño y los textos. |
| Empresa · tarjetas de noticias | Tablet (1024px) | Layout / Tipografía | Títulos de 26px en columnas de unos 154px, con `overflow-wrap:anywhere`: palabras partidas y lectura vertical. | Corregido | Entre 990–1199px, introducción encima de la lista y tarjetas a todo el ancho disponible. Eliminada la partición arbitraria de palabras. |
| Noticias · títulos compartidos | Todos | Consistencia tipográfica | El mismo titular se mostraba en mayúsculas en Empresa y en caja de frase en Noticias. | Corregido | `text-transform:none` compartido para titulares de noticias, conservando el texto fuente y Semibold 600. |
| Inicio · títulos de obras | Desktop (1440 / 1920px) | Layout | La columna del 28% podía forzar cortes interiores en nombres largos. | Corregido | Columna de título al 36%, imagen al 64% menos gap y ajuste por espacios. |
| Proyectos · categorías | Mobile (375 / 430px) | Responsive / Descubribilidad | La última categoría quedaba fuera de la vista inicial en una tira horizontal. | Corregido | Filtros con flex-wrap y gaps compartidos. Todas las categorías visibles y accesibles sin scroll lateral. |
| Proyectos · etiquetas de filtros y lista | Todos | Contraste | Las etiquetas grises sobre fondo gris claro resultaban difíciles de leer en la vista de lista. | Corregido | Color compartido `#626262`, opacidad 1; contraste aproximado 5.6:1 sobre `#f5f5f5`. |
| H1 y orden semántico | Todas las rutas / seis anchos | Jerarquía HTML | Comprobación de H1 único y ausencia de saltos en H1–H6, incluyendo el catálogo corregido. | Verificado | Validador de HTML ejecutable en `scripts/audit-visual-contract.py`. Las clases y `data-type` mantienen separada la apariencia del nivel semántico. |
| Familias y variantes | Todas las rutas / seis anchos | Regresión tipográfica | El cambio de breakpoint no debe alterar familia, peso, tracking relativo o interlineado relativo. | Verificado | Comparación de estilos calculados por elemento en navegador. H1 Inter 500 / −.065em / 1.13; H2 Inter 600 / −.055em / 1.04. Solo cambia el tamaño según las variables de cada breakpoint. |
| Sectores · botones dentro de metadatos | Todos | Tipografía / Cascada | La herencia de un contenedor `meta` reemplazaba la variante explícita de tres botones y los hacía adoptar Inter 16px del párrafo. | Corregido | Los selectores de herencia excluyen descendientes con `data-type`. Cada botón conserva IBM Plex Mono 400 de 14px. Repetida la ruta en los seis anchos. |
| Recursos y overflow | Todas las rutas / seis anchos | Regresión responsive | Comprobar imágenes, referencias internas, recortes y ancho del documento. | Verificado | Matriz de navegador y validación de archivos. Los desplazamientos internos de carruseles se distinguen del desbordamiento del documento. |
| Generación de páginas | Todas las plantillas | Regresión | Las correcciones deben persistir al regenerar el catálogo y normalizar la web. | Verificado | Normalizador idempotente: una segunda ejecución modifica 0 documentos. Generadores actualizados para clases y niveles semánticos. |

## Sistema compartido

- Familias locales: Inter 400/500/600/700 e IBM Plex Mono 400 para metadatos y controles. No se cargan SequelSans, ResidentialSequel ni PPFraktionMono.
- Las variantes poseen familia, peso, tracking e interlineado propios. Los breakpoints modifican tamaños, sin cambiar el carácter de la variante.
- Colores contextuales negro/blanco sobre fondos claros/oscuros; se conserva el dorado de marca y sus puntos de sección. Los puntos del H1 de Servicios conservan el color del texto, según la indicación anterior.
- Retícula: 24px en móvil; 40px en tablet vertical; 120px de inicio / 40px de final desde 990px; 176px / 94.4px desde 1200px, con centrado del marco en pantallas superiores a 2042px.
- El contrato usa capas `akko-legacy`, `akko-layout` y `akko-type`: los estilos importados no pueden reemplazar las variantes compartidas.

## Alcance y evidencia

53 páginas × 6 anchos = 318 combinaciones. Capturas por página/ancho de cabecera, siguiente bloque principal y cierre: 954 vistas, más evidencias de componentes e interacciones. Altura de la matriz: 900px; anchos CSS reales comprobados: 375, 430, 768, 1024, 1440 y 1920px.

Las capturas corresponden a ventanas de contenido, no a montajes de página completa. La inspección combina imágenes y estilos calculados. No equivale a una comparación automática píxel a píxel con un diseño maestro completo, que no existe para las 53 rutas. Motor revisado: Brave/Chromium. Safari y Firefox requieren una pasada específica.

La galería y las capturas se entregan como artefacto local. `visual-audit-summary.json` acompaña a esta rama con la cobertura y el resultado por ruta. El repositorio conserva su estructura de despliegue mediante `akko-site.zip` + `assets/`; `visual-gauntlet.patch` permite revisar los cambios de fuente contra el punto de partida `8f53bfb`.

## Fuera del cambio de contenido

Permanecen textos heredados en inglés en Inicio, Empresa y dos sectores, contenidos jurídicos provisionales, fichas de ejemplo y el formulario de demostración. Se documentan, pero no se sobrescriben, conforme a la instrucción de conservar el contenido actual. Tampoco se afirma que los formularios envíen mensajes reales.

## Reproducción

Desde la raíz de la fuente, con la dependencia `beautifulsoup4` usada por los generadores:

```sh
python scripts/normalize-typography.py
python scripts/audit-visual-contract.py
python scripts/audit-visual-contract.py --matrix ../outputs/visual-gauntlet/matrix.json
```

La matriz procede de navegación y capturas reales del navegador. El validador no sustituye la revisión visual.

## Estados interactivos comprobados

- Menú móvil a 375px: apertura, despliegue de Sectores y cierre.
- Catálogo: filtro Espacios singulares (5 obras), cambio a lista y títulos H2 conservados tras regenerar las tarjetas.
- FAQ: apertura de respuesta y control de ancho a 375px.
- Formulario: validación de campos vacíos, foco y etiqueta flotante; 4 mensajes de campo obligatorio sin desbordamiento.
- Documento local con nombre largo: ajuste dentro de 327px, sin envío ni datos personales.
- Bloques de Empleo, Servicios, Inicio, Empresa y los tres sectores, más cuerpo de los 10 artículos, con capturas adicionales por breakpoint.

Resultado de los controles de la matriz: 53 rutas, 318 combinaciones, 954 capturas base y 0 incidencias detectadas en los controles implementados. Se conservan las limitaciones de alcance descritas arriba.
