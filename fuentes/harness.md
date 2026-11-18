# harness · método y herramientas

Página de fuente: el repositorio público que reúne el método y las herramientas para que una persona y un equipo de agentes de IA trabajen juntos sobre GitHub.

- **Repositorio:** [JosebaDG/harness](https://github.com/JosebaDG/harness) (público, licencia MIT).
- **Versión citada:** commit [`84eccc4`](https://github.com/JosebaDG/harness/tree/84eccc45ea1a386ad7b94237b466c4b1279d645b) (17 de noviembre de 2026). Las herramientas entraron en [`16e768a`](https://github.com/JosebaDG/harness/tree/16e768aa96b3e3df7f13327d69190453650ef0f6) y `84eccc4` añade dos avisos a la bandeja.
- **Ingerida:** 2026-11-18.

## Qué es

Según su [README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md): cada issue es un hilo con turno, lo decidido vive en un registro con su porqué y lo que se publica pasa antes por una revisión de lo público. No depende de un proveedor de IA concreto.

Está **en construcción** y se monta por PR en cuatro pasos: base, prueba de lo público, herramientas y contenido. En este commit están hechos los tres primeros. Las carpetas de contenido ([flujos/](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/flujos/README.md), [especialistas/](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/especialistas/README.md), [ejemplos/](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/ejemplos/README.md) y [web/](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/web/README.md)) solo tienen su README y dicen «Vacío por ahora».

| Pieza | Qué hace |
|---|---|
| [equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py) | El canal sobre issues: leer, escribir y pasar el turno, la bandeja de cada agente, el registro de decisiones y las flags. Solo usa la biblioteca estándar de Python 3. |
| [acceso.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/acceso.py) | Saca el token de cada agente por *device flow* de una GitHub App, sin secretos en el código y sin imprimir el token. |
| [prueba-web.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/prueba-web.py) | Prueba de accesibilidad (axe-core, WCAG 2.2 AA) y de móvil para una web estática. Sale con 1 si algo falla. |
| [lo-publico.yml](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/.github/workflows/lo-publico.yml) | Action que busca lo que no puede ser público en el árbol, en cada commit del PR y en sus mensajes. |
| [pruebas.yml](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/.github/workflows/pruebas.yml) | Action de pruebas sin red ni secretos en cada PR. |
| [pages.yml](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/.github/workflows/pages.yml) | Publica `web/` al fusionar en `main` y prueba lo publicado. Mientras `web/` no tenga `index.html`, no publica nada. |

## Lo que dice

- **Una persona decide lo que no se delega:** lo que se publica, se gasta o se borra, los servicios nuevos y los cambios de rumbo. «Eso no lo hace ningún agente» ([README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md), requisitos). Más en [La persona decide, los agentes ejecutan](../conceptos/la-persona-decide.md).
- **Lo propio de cada equipo va en la configuración, no en el código:** nombres, repos y Apps del equipo salen de un JSON, para que la herramienta sirva a cualquier equipo ([herramientas/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/README.md)).
- **Material externo:** lo que no publica la persona, sola o con una de las Apps del equipo, se enseña aparte, no da turno y, si se dirige a agentes, la bandeja avisa ([herramientas/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/README.md); [equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py)). Más en [Material externo: datos, no órdenes](../conceptos/material-externo.md).
- **La bandeja dice qué toca:** `TE TOCA` cuando otro te pasa el turno; `SIGUES TÚ` cuando el turno y el último mensaje son tuyos, para que el trabajo arranque en esa ronda o se pase el turno; `ESPERA ÚNICA`, con un ciclo de revisiones en la configuración, cuando el anterior del ciclo aún no ha escrito: una sola espera de como mucho 10 minutos y se sigue ([herramientas/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/README.md)).
- **Un fusible que avisa y no para:** cada 30 mensajes seguidos de agentes sin la persona, la bandeja pide al responsable que repase si el hilo avanza; un hilo sin turno ni mensajes en 3 días sale como parado ([equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py), constantes del principio).
- **Lo público se revisa antes de publicar, y también los mensajes:** un secreto que llega a un commit se avisa y se rota aunque se corrija después; el mensaje del *squash* dice qué entra, no quién lo aprobó; los issues se enlazan, no se numeran como hilos ([nucleo/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/nucleo/README.md)). Más en [Revisar lo público antes de publicar](../conceptos/revision-de-lo-publico.md).
- **Atribución:** parte del material adapta ideas de ECC y de mattpocock/skills, con licencia MIT; los avisos completos están en [ATRIBUCION.md](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/ATRIBUCION.md).

## Comprobado y no comprobado

- **Comprobado al ingerir:** el contenido de los archivos citados en `84eccc4` y que las carpetas de contenido están vacías.
- **No comprobado aquí:** que las Actions pasen en verde ni que `pages.yml` haya publicado algo. El Wiki solo lee la fuente; no ejecuta sus herramientas.

## Afirmaciones vivas

Se revisan en cada repaso semanal:

- el repo está «en construcción» y el contenido (núcleo completo, especialistas, flujos, ejemplos y web) aún no ha entrado ([README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md));
- «No damos un tiempo de arranque: todavía no está medido» ([README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md));
- la web no publica nada mientras `web/` no tenga `index.html` ([pages.yml](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/.github/workflows/pages.yml)).
