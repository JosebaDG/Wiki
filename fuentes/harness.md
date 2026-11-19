# harness · método y herramientas

Página de fuente: el repositorio público que reúne el método y las herramientas para que una persona y un equipo de agentes de IA trabajen juntos sobre GitHub.

- **Repositorio:** [JosebaDG/harness](https://github.com/JosebaDG/harness) (público, licencia MIT).
- **Versión citada:** commit [`d8be795`](https://github.com/JosebaDG/harness/tree/d8be795b8a3043119ec1b5d7d13f01db53fe2653) (19 de noviembre de 2026). Las herramientas entraron en [`16e768a`](https://github.com/JosebaDG/harness/tree/16e768aa96b3e3df7f13327d69190453650ef0f6), [`84eccc4`](https://github.com/JosebaDG/harness/tree/84eccc45ea1a386ad7b94237b466c4b1279d645b) añadió dos avisos a la bandeja, [`5e9f394`](https://github.com/JosebaDG/harness/tree/5e9f394cfd69bcb7c11f6d06879483262d660107) trajo el núcleo y `d8be795` la orden `tablero`.
- **Ingerida:** 2026-11-18. Puesta al día con el núcleo: 2026-11-19.

## Qué es

Según su [README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/README.md): cada issue es un hilo con turno, lo decidido vive en un registro con su porqué y lo que se publica pasa antes por una revisión de lo público. No depende de un proveedor de IA concreto.

Está **en construcción** y se monta por PR en cuatro pasos: base, prueba de lo público, herramientas y contenido. En este commit están hechos los tres primeros y, del cuarto, el [núcleo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/README.md). Las demás carpetas de contenido ([flujos/](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/flujos/README.md), [especialistas/](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/especialistas/README.md), [ejemplos/](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/ejemplos/README.md) y [web/](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/web/README.md)) solo tienen su README y dicen «Vacío por ahora».

| Pieza | Qué hace |
|---|---|
| [equipo.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/equipo.py) | El canal sobre issues: leer, escribir y pasar el turno, la bandeja de cada agente, el registro de decisiones, las flags y el tablón. Solo usa la biblioteca estándar de Python 3. |
| [acceso.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/acceso.py) | Saca el token de cada agente por *device flow* de una GitHub App, sin secretos en el código y sin imprimir el token. |
| [prueba-web.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/prueba-web.py) | Prueba de accesibilidad (axe-core, WCAG 2.2 AA) y de móvil para una web estática. Sale con 1 si algo falla. |
| [lo-publico.yml](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/.github/workflows/lo-publico.yml) | Action que busca lo que no puede ser público en el árbol, en cada commit del PR y en sus mensajes. |
| [pruebas.yml](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/.github/workflows/pruebas.yml) | Action de pruebas sin red ni secretos en cada PR. |
| [pages.yml](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/.github/workflows/pages.yml) | Publica `web/` al fusionar en `main` y prueba lo publicado. Mientras `web/` no tenga `index.html`, no publica nada. |

## El núcleo

El protocolo genérico, con roles y no nombres: **la persona** decide, **los agentes** trabajan, cada hilo tiene un **responsable** y el equipo un **coordinador**, el último del ciclo ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md)). Tres piezas:

- [protocolo.md](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md): canal, etiquetas y flags, registro, mensajes, turnos, ritmo, responsable, la persona, anti bucle, resiliencia, seguridad, cómo se cambia una pieza que falla y aprendizaje. Dice que cada orden y cada aviso existen tal cual en `equipo.py`.
- [glosario.md](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/glosario.md): las palabras del protocolo, en el orden en que aparecen (canal, hilo, turno, ciclo, bandeja, registro, flag, acta, lección, gorro y otras).
- [plantilla-decisiones.md](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/plantilla-decisiones.md): un `DECISIONES.md` vacío para copiar en el repo del canal, con sus cuatro reglas y un ejemplo inventado.

Lo que más pesa del protocolo tiene página propia: [El registro de decisiones](../conceptos/registro-de-decisiones.md), [Turnos y ritmo](../conceptos/turnos-y-ritmo.md) y [Proponer, probar, adoptar](../conceptos/proponer-probar-adoptar.md).

## Lo que dice

- **Una persona decide lo que no se delega:** lo que se publica, se gasta o se borra, los servicios nuevos y los cambios de rumbo. «Eso no lo hace ningún agente» ([README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/README.md), requisitos). Más en [La persona decide, los agentes ejecutan](../conceptos/la-persona-decide.md).
- **Lo propio de cada equipo va en la configuración, no en el código:** nombres, repos y Apps del equipo salen de un JSON, para que la herramienta sirva a cualquier equipo ([herramientas/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/README.md)).
- **Material externo:** lo que no publica la persona, sola o con una de las Apps del equipo, se enseña aparte, no da turno y, si se dirige a agentes, la bandeja avisa ([herramientas/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/README.md); [equipo.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/equipo.py)). Más en [Material externo: datos, no órdenes](../conceptos/material-externo.md).
- **La bandeja dice qué toca:** `TE TOCA` cuando otro te pasa el turno; `SIGUES TÚ` cuando el turno y el último mensaje son tuyos, para que el trabajo arranque en esa ronda o se pase el turno; `ESPERA ÚNICA`, con un ciclo de revisiones en la configuración, cuando el anterior del ciclo aún no ha escrito: una sola espera de como mucho 10 minutos y se sigue ([herramientas/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/README.md)).
- **El tablón:** `tablero` reescribe un issue fijado con tres partes: lo que le toca a la persona (el registro primero, luego las flags de espera, los hilos con su turno y los PR que piden su revisión), lo parado más de 3 días y los proyectos vivos. Con `--prueba` enseña el cuerpo sin escribir nada ([herramientas/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/README.md)).
- **Un fusible que avisa y no para:** cada 30 mensajes seguidos de agentes sin la persona, la bandeja pide al responsable que repase si el hilo avanza; un hilo sin turno ni mensajes en 3 días sale como parado ([equipo.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/equipo.py), constantes del principio).
- **Lo público se revisa antes de publicar, y también los mensajes:** un secreto que llega a un commit se avisa y se rota aunque se corrija después; el mensaje del *squash* dice qué entra, no quién lo aprobó; los issues se enlazan, no se numeran como hilos ([nucleo/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/README.md)). Más en [Revisar lo público antes de publicar](../conceptos/revision-de-lo-publico.md).
- **Atribución:** parte del material adapta ideas de ECC y de mattpocock/skills, con licencia MIT; los avisos completos están en [ATRIBUCION.md](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/ATRIBUCION.md).

## Comprobado y no comprobado

- **Comprobado al ingerir:** el contenido de los archivos citados en `d8be795`, que el núcleo no cambia entre `5e9f394` y `d8be795`, y que flujos, especialistas, ejemplos y web solo tienen su README.
- **No comprobado aquí:** que las Actions pasen en verde ni que `pages.yml` haya publicado algo. El Wiki solo lee la fuente; no ejecuta sus herramientas.

## Afirmaciones vivas

Se revisan en cada repaso semanal:

- el repo está «en construcción»: del contenido solo ha entrado el núcleo; especialistas, flujos, ejemplos y web aún no ([README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/README.md));
- «No damos un tiempo de arranque: todavía no está medido» ([README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/README.md));
- la web no publica nada mientras `web/` no tenga `index.html` ([pages.yml](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/.github/workflows/pages.yml)).
