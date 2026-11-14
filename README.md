# diguardia.github.io

Sitio de los juegos de Christian Di Guardia: portada, una página por juego y su política de
privacidad (la URL que pide Google Play). Jekyll servido por GitHub Pages, sin build propio.

Publicado en https://diguardia.github.io/

## Estructura

| Ruta | Qué es |
|---|---|
| `_data/games.yml` | Lista de juegos (nombre, frase, estado, ícono, enlace de Play). La portada sale de acá. |
| `<slug>/index.md` | Página del juego (layout `game`): descripción y capturas. |
| `<slug>/privacy.md` | Política de privacidad del juego → `/<slug>/privacy/`. |
| `<slug>/img/` | `icon.png` (512), `feature.png` (1024×500), `screenshot-N.png`. |
| `templates/nuevo-juego/` | Plantillas para copiar (no se publican). |
| `_layouts/`, `assets/css/` | Diseño compartido. |

## Sumar un juego

1. Copiar `templates/nuevo-juego/` a `<slug>/` y reemplazar `SLUG`, `NOMBRE DEL JUEGO`,
   `PAQUETE` y `FECHA`/`DATE`. Revisar la política: la plantilla dice que el juego **no
   recolecta datos**; si el juego nuevo usa anuncios, analítica, cuentas o Internet, hay que
   reescribirla.
2. Poner las imágenes en `<slug>/img/`.
3. Agregar el bloque en `_data/games.yml`.
4. Cuando esté en Play, completar `play_url`: la portada y la página muestran el botón.

## Probar localmente

```bash
bundle exec jekyll serve   # o: docker run --rm -p 4000:4000 -v "$PWD":/srv/jekyll jekyll/jekyll jekyll serve
```
