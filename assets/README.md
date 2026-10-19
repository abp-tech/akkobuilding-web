# Assets de AKKO Building

Carpeta de imágenes y recursos públicos para la web estática. Cada proyecto, noticia y página tiene su propia carpeta, identificada con el slug de su contenido.

## Estructura

- `proyectos/<slug>/`: portada y galería de cada proyecto.
- `noticias/<slug>/`: portada e imágenes de cada artículo.
- `paginas/<ruta>/`: imágenes de inicio, empresa, servicios, sectores, contacto y otras páginas.
- `compartidos/logos/`: logotipos comunes.
- `compartidos/iconos/`: iconos comunes.
- `compartidos/fondos/`: fondos utilizados en varias páginas.

Los archivos `.gitkeep` conservan las carpetas vacías en Git. Se pueden dejar al añadir imágenes.

## Cómo añadir imágenes

1. Abre la carpeta del contenido en GitHub.
2. Usa **Add file → Upload files** y sube las versiones preparadas para web.
3. Guarda los cambios en `main`. GitHub Pages publicará los recursos en esa misma ruta dentro de `assets/`.
4. Para mostrarlas en una card, cabecera o galería hay que asignar su ruta en el contenido o plantilla correspondiente. Subir un archivo no sustituye automáticamente la fotografía actual.

Para otro proyecto o artículo, crea una subcarpeta con el mismo slug que su página. No se utilizan carpetas de categoría como sustituto del identificador del contenido.

## Nombres y versiones

Usa minúsculas, números y guiones, sin espacios ni acentos. Conserva un nombre estable cuando reemplaces una imagen del mismo contenido.

```text
proyectos/can-oliver/portada.webp
proyectos/can-oliver/galeria-01.webp
proyectos/can-oliver/galeria-02.webp
noticias/nobis-hotel-palma-rehabilitacion/portada.webp
paginas/inicio/hero.webp
paginas/sectores/hoteles/hero.webp
compartidos/logos/akko.svg
```

Si se necesitan tamaños distintos para carga responsive, usa sufijos explícitos: `portada-640.webp`, `portada-1280.webp` y `portada-1920.webp`. La plantilla los seleccionará mediante `srcset` cuando se configure.

## Preparación para web

- Fotografías: preferiblemente WebP o AVIF; JPEG cuando corresponda.
- Logotipos e iconos: SVG; PNG cuando necesiten transparencia y no exista versión vectorial.
- Exporta al tamaño de uso y comprime antes de subir. Como orientación, prepara las cards a 640–960 px de ancho y las cabeceras a 1600–1920 px, revisando la calidad en cada caso.
- Guarda los originales de máxima resolución fuera de esta carpeta de publicación.
- El texto alternativo, los créditos, el orden de la galería y el recorte se definen en la página, no en el nombre del archivo.

## Publicación

En GitHub Pages una imagen de ejemplo queda disponible en:

`https://abp-tech.github.io/akkobuilding-web/assets/proyectos/can-oliver/portada.webp`

La ruta existirá cuando se haya añadido el archivo y finalizado el despliegue. Con un dominio en la raíz, la ruta equivalente será `/assets/proyectos/can-oliver/portada.webp`.

El flujo de publicación copia los recursos de `assets/` después de extraer `akko-site.zip`, de modo que se pueden añadir o actualizar imágenes sin reconstruir el ZIP. Se omiten las guías y los archivos de conservación de carpetas.

Los recursos actuales de `v2/` siguen funcionando. Esta carpeta establece la organización para las imágenes que se incorporen a partir de ahora; su migración se puede hacer por contenido al actualizar cada página.
