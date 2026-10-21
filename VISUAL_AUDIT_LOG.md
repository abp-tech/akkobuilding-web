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

## Rectificación de fidelidad al original · 21 de octubre de 2026

La auditoría del 20 de octubre verificó un contrato interno que contenía decisiones visuales incorrectas. Sus comprobaciones de consistencia no acreditaban fidelidad a Structure. Esta revisión sustituye esa conclusión: contrasta el HTML/CSS original retenido y diez plantillas originales cargadas en navegador, con las dimensiones CSS reales verificadas, no solo las solicitadas.

Se mantiene la adaptación editorial y fotográfica de AKKO, Inter e IBM Plex Mono como sustituciones exigidas, y el diseño aprobado de Servicios. La identidad y el pie aprobado de AKKO se conservan. No se declara identidad píxel a píxel entre contenidos y familias tipográficas diferentes.

| Página / Componente | Breakpoint (Dispositivo) | Tipo de Fallo | Descripción del Problema | Estado | Cambio Aplicado en Código |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Home / H1 | Desktop 1440 / 1920 | Escala tipográfica | El H1 con variante visual H2 se forzaba a 116px; el original usa 81,6px. | Corregido | Rol `home-display`: 81,6px desde 1200px, 59,2px debajo; Inter 500 estable. |
| Todas / texto monoespaciado | 375 / 430 / 768 / 1024 / 1440 / 1920 | Familia | Los párrafos `body` anulaban la familia de `.font-ibm-mono`; ocurría también en párrafos con la utilidad en el propio nodo. | Corregido | Rol `mono-body`, familia IBM Plex Mono 400, 16px/1.3; precedencia explícita y normalizador idempotente. |
| Todas / jerarquía visual | Todos | Escala / interlineado | El contrato sustituía las variantes originales por una escala nueva, confundiendo H5 con metadatos mono. | Corregido | Recuperadas escalas H1 98,4/73,6; H2 81,6/59,2; H3 44,8/33,6; H4 20; H5 16. Títulos en pastilla 66,4/36,8 y H2 móvil 27,2. |
| Todas / retícula | Todos | Márgenes | Márgenes asimétricos 176/94,4px alteraban anchos, proporciones y saltos. | Corregido | Márgenes originales simétricos 8/40/94,4px y contenido centrado por encima de 2044,8px. Servicios conserva su propia retícula. |
| Cabecera / idioma | Tablet / Desktop | Alineación | Selector de idioma fuera del margen derecho del contenido; marca ocupaba el inicio de la retícula. | Corregido | Límite derecho compartido; reserva de marca 64px y navegación desde 94,4px; cabecera móvil hasta 768px. |
| Home / últimos proyectos | Desktop | Proporciones | Ancho y tipo de las tarjetas no correspondían a la referencia. | Corregido | Slider 70% y enlaces 30%-1em entre 1200–1599; 50/50 desde 1600; imagen 50%, proporción original. |
| Home / Nuestro trabajo | Desktop | Alturas / imágenes | Tres filas fijas y reparto porcentual comprimían imágenes. | Corregido | Alturas naturales, títulos 17rem e imagen calc(100%-18rem); proporción y columnas originales; Swiper `slidesPerView:auto`. |
| Home / contacto | Todos | Contenido añadido | Subtítulo y bloque largo bajo la pastilla señalados por el usuario. | Corregido | Retirados únicamente esos dos bloques; archivados en `content/removed-home-cta.json`. |
| CTA de otras páginas | Tablet / Desktop | Jerarquía / composición | Título metido dentro de la columna izquierda en lugar de preceder las dos columnas. | Corregido | Título H2 común como hermano anterior; reparto original 49/51 y márgenes; contenido adaptado conservado. |
| Empresa / noticias | Todos | Layout inventado | Carrusel y filas fijas podían comprimir o ocultar imágenes y extractos. | Corregido | Lista natural, imágenes con padding 65%, división 47/53 desde 1200; eliminado comportamiento del carrusel. |
| Empresa / origen | Tablet / Desktop | Breakpoint | Composición a sangre desde 768 y fotos forzadas cuadradas. | Corregido | Composición original desde 990, tres columnas 30%, fotos con proporción propia. |
| Noticias / categorías | Todos | Componente ausente | Se había eliminado la navegación de categorías. | Corregido | Restituida con categorías editoriales actuales; botones accesibles, filtros reales y anuncio de resultados; generador actualizado. |
| Proyectos / lista | Desktop 1440 / 1920 | Composición | Grid de previsualización del 27% ajeno a la referencia. | Corregido | Previsualización sticky de 17/31rem y desplazamientos originales; controles de orden conservados. |
| Fichas / galería | Todos | Comportamiento inventado | Galería horizontal fijada al scroll en lugar de galería vertical. | Corregido | Restituida galería envolvente de imágenes completas y parejas desde 1200; sin interceptar scroll. 230 imágenes, orden y pies conservados en 26 fichas. |
| Contacto / formulario | Tablet / Desktop | Flexbox | Columnas 33,3/66,7% más gap de 32px empujaban el formulario debajo. | Corregido | Eliminado gap en escritorio; 32px solo en móvil; párrafo inicial 20px/1.25. |
| Empleo / candidatura y multimedia | Todos | Espaciado / proporción | Separaciones de 4rem/2rem y foto móvil al 70% eran añadidas. | Corregido | Separación de título 1em y bloque multimedia a sangre con padding 45%. |
| Sectores / slider | Todos | Anidación | Retícula común aplicaba márgenes al contenedor exterior y al interior. | Corregido | Contenedor exterior sin padding; retícula solo en la sección interior. |
| Recursos CSS/JS | Todos | Caché | Un JS antiguo podía seguir cargado aunque el HTML ya tuviera el componente nuevo. | Corregido | Versión `reference-4` en CSS, fuentes y JS; orden de capas declarado antes de cualquier hoja de componentes. |

Validación: 53 documentos con un H1 y jerarquía sin saltos; 318 capturas a 1000px de alto y anchos reales 375/430/768/1024/1440/1920; ninguna diferencia entre ancho solicitado y `innerWidth`; sin overflow lateral, títulos desbordados o utilidades mono computadas como Inter. 60 comparaciones de plantilla y 114 capturas adicionales de secciones en escritorio/móvil. Comprobados filtros de Noticias, vistas de Proyectos y conservación del contenido (solo las dos retiradas solicitadas en Home).

Evidencias locales: `outputs/reference-fidelity/galeria.html`, `routes-audit.json`, `comparison.json`, `sections.json` y `summary.json`. Motor: Brave/Chromium. No se ha realizado validación física de dispositivos ni Safari/Firefox. Las capturas no sustituyen una comparación visual; se han inspeccionado las composiciones de las diez plantillas y los detalles señalados por el usuario.
