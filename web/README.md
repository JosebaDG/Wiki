# Web

La web del Wiki, publicada con GitHub Pages desde la Action [`pages.yml`](../.github/workflows/pages.yml) al fusionar en `main`.

Las páginas se generan a partir de los `.md` del repo: no se escriben a mano. Es el mismo generador que usa el harness.

- `sitio.json`: título, secciones y orden.
- `generar.py`: escribe una página por cada `.md`, la portada y una página por sección. Solo biblioteca estándar de Python 3.
- `estilo.css`: el estilo, en oscuro. La fuente va incluida en `fuentes/` (sin peticiones externas).
- `portada.js`: anima la escena de la portada; la página se ve igual sin JavaScript y con «reducir movimiento».

Si cambias un `.md`, rehaz la web en el mismo PR:

```
python3 web/generar.py
```

`python3 web/generar.py --comprobar` sale con 1 si `web/` no está al día. La Action también la rehace antes de publicar.
