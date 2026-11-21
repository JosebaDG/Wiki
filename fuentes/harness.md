# harness · método y herramientas

Página de fuente: el repositorio público que reúne el método y las herramientas para que una persona y un equipo de agentes de IA trabajen juntos sobre GitHub.

- **Repositorio:** [JosebaDG/harness](https://github.com/JosebaDG/harness) (público, licencia MIT).
- **Versión citada:** commit [`a0e1ac6`](https://github.com/JosebaDG/harness/tree/a0e1ac64837c3939b01c3f34d93125ec30e5e79f) (19 de noviembre de 2026); lo de los hilos sin turno, en [`d634234`](https://github.com/JosebaDG/harness/tree/d63423452ce784109af1122c163af7d264c95160) (20 de noviembre). Las herramientas entraron en [`16e768a`](https://github.com/JosebaDG/harness/tree/16e768aa96b3e3df7f13327d69190453650ef0f6), [`84eccc4`](https://github.com/JosebaDG/harness/tree/84eccc45ea1a386ad7b94237b466c4b1279d645b) añadió dos avisos a la bandeja, [`5e9f394`](https://github.com/JosebaDG/harness/tree/5e9f394cfd69bcb7c11f6d06879483262d660107) trajo el núcleo, [`d8be795`](https://github.com/JosebaDG/harness/tree/d8be795b8a3043119ec1b5d7d13f01db53fe2653) la orden `tablero`, [`e94ebfd`](https://github.com/JosebaDG/harness/tree/e94ebfd783ac100b3789bef998b7d39da4ade96c) los especialistas `a0e1ac6` los flujos, los ejemplos y las lecciones, y `d634234` los hilos sin turno que esperan una fecha.
- **Ingerida:** 2026-11-18. Puesta al día con el núcleo y con los especialistas: 2026-11-19. Con los flujos y los ejemplos, y con los hilos sin turno: 2026-11-20.

## Qué es

Según su [README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/README.md): cada issue es un hilo con turno, lo decidido vive en un registro con su porqué y lo que se publica pasa antes por una revisión de lo público. No depende de un proveedor de IA concreto.

Está **en construcción** y se monta por PR en cuatro pasos: base, prueba de lo público, herramientas y contenido. En este commit están hechos los tres primeros y, del cuarto, el [núcleo](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/README.md), los [especialistas](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/README.md), los [flujos](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md) y los [ejemplos](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/README.md). Solo [web/](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/web/README.md) sigue con su README y dice «Vacío por ahora».

| Pieza | Qué hace |
|---|---|
| [equipo.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/equipo.py) | El canal sobre issues: leer, escribir y pasar el turno, la bandeja de cada agente, el registro de decisiones, las flags y el tablón. Solo usa la biblioteca estándar de Python 3. |
| [acceso.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/acceso.py) | Saca el token de cada agente por *device flow* de una GitHub App, sin secretos en el código y sin imprimir el token. |
| [prueba-web.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/prueba-web.py) | Prueba de accesibilidad (axe-core, WCAG 2.2 AA) y de móvil para una web estática. Sale con 1 si algo falla. |
| [lo-publico.yml](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/.github/workflows/lo-publico.yml) | Action que busca lo que no puede ser público en el árbol, en cada commit del PR y en sus mensajes. |
| [pruebas.yml](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/.github/workflows/pruebas.yml) | Action de pruebas sin red ni secretos en cada PR. |
| [pages.yml](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/.github/workflows/pages.yml) | Publica `web/` al fusionar en `main` y prueba lo publicado. Mientras `web/` no tenga `index.html`, no publica nada. |

## El núcleo

El protocolo genérico, con roles y no nombres: **la persona** decide, **los agentes** trabajan, cada hilo tiene un **responsable** y el equipo un **coordinador**, el último del ciclo ([protocolo](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/protocolo.md)). Tres piezas:

- [protocolo.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/protocolo.md): canal, etiquetas y flags, registro, mensajes, turnos, ritmo, responsable, la persona, anti bucle, resiliencia, seguridad, cómo se cambia una pieza que falla y aprendizaje. Dice que cada orden y cada aviso existen tal cual en `equipo.py`.
- [glosario.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/glosario.md): las palabras del protocolo, en el orden en que aparecen (canal, hilo, turno, ciclo, bandeja, registro, flag, acta, lección, gorro y otras).
- [plantilla-decisiones.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/plantilla-decisiones.md): un `DECISIONES.md` vacío para copiar en el repo del canal, con sus cuatro reglas y un ejemplo inventado.

Lo que más pesa del protocolo tiene página propia: [El registro de decisiones](../conceptos/registro-de-decisiones.md), [Turnos y ritmo](../conceptos/turnos-y-ritmo.md) y [Proponer, probar, adoptar](../conceptos/proponer-probar-adoptar.md).

## Los especialistas

Un **gorro** es un rol con ficha propia que un agente se pone durante un ciclo sin cambiar su ficha ([especialistas/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/README.md)). La carpeta trae:

- [plantilla.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/plantilla.md): los apartados que tiene toda ficha (familia, estado, de dónde sale, cuándo se usa, qué decide y qué no, reglas, límites, separación y origen). Un gorro entra cuando los tiene todos.
- [README.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/README.md): siete reglas comunes y el catálogo de 20 gorros en siete familias: dirección, diseño, investigación, creación, verificación, comunicación y mejora del equipo.
- Una ficha por gorro. Por ejemplo, el [orquestador](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/orquestador.md) elige los gorros de cada proyecto y desempata, y el [guardián de lo público](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/especialistas/guardian-de-lo-publico.md) da el veredicto antes de que algo se publique.

La mayoría salen de destilar agentes y skills de ECC en la versión 2.2.3, y algunos de fichas de roles que trajo la persona; cada ficha lo dice en su «Origen» y los avisos de licencia están en [ATRIBUCION.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ATRIBUCION.md). Las especialidades y los procedimientos que citan algunas fichas (conflictos, consejo, traspaso, la especialidad web) no han entrado con los flujos: el [README de flujos](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md) dice que llegan en otro PR. Las reglas comunes tienen página propia: [Gorros: un rol por ciclo](../conceptos/gorros.md).

## Los flujos

Un flujo dice qué gorros hacen falta, en qué orden y qué entrega cada uno, y si ya se ha probado ([flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md)). Tiene dos partes: un **esqueleto** común a cualquier proyecto (encargo, redacción, objeción de fondo, cifras, lo público, lector en frío, última objeción, empaquetado y publicar) y un **adaptador** con lo que cambia según el tipo: qué vista previa ve la persona y qué prueba automática se pasa. Más en [Flujos: esqueleto y adaptador](../conceptos/flujos-esqueleto-y-adaptador.md).

- [escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md): un cambio de texto o contenido en una web pública, sin tocar el diseño. Diez pasos, del 0 al 9, más un 1b, cada uno con su gorro, y una vista previa bajo `/preview/prN/`. El paso 6 es [prueba-web.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/prueba-web.py). **Probado una vez.**
- [novela-a-video.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/novela-a-video.md): un piloto de investigación, un tráiler de 30 a 60 segundos de una novela con permiso del autor por escrito. Cuatro agentes, un gorro cada uno por ciclo, y no se gasta nada hasta la puerta del ciclo 2. **Sin probar.**

Cuatro reglas valen para todos: dos puertas de la persona (el encargo al principio y sí, no o cambios al final), un commit por paso con el gorro en el mensaje, quien hace una pieza no la evalúa, y un flujo solo pasa a «probado» con una prueba en `ejemplos/` ([flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md), «Reglas para todos los flujos»).

## Los ejemplos y las lecciones

`ejemplos/` guarda pruebas reales de los flujos y lecciones de fallos reales, reescritas en genérico, sin nombres de personas, repos privados ni proyectos ([ejemplos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/README.md)).

- **La primera prueba del escaparate web** ([primera-prueba-escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/primera-prueba-escaparate-web.md)): el orden cifras, luego lo público, luego el lector en frío encontró dos afirmaciones falsas que habían pasado la redacción. El cuello de botella fue el turno, no el trabajo. Un solo agente llevó cuatro gorros, y tres quedaron provisionales. Costó una tarde de un agente y unas 95 llamadas a herramientas, más de la mitad en leer y localizar fuentes. De ahí salieron el esqueleto y el adaptador, la objeción de fondo al principio y la regla de las afirmaciones vivas.
- **Trece lecciones** ([lecciones/](https://github.com/JosebaDG/harness/tree/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones)), cada una con cuándo aplica, qué hacer, pruebas, seguridad y qué cambió en el harness. Por familias:
  - **El registro:** lo decidido en el chat va al registro o las rutinas lo pisan (001); sin turno, el aviso va por el registro (004); la línea solo dice lo que dijo la persona (007), separa objetivo y herramienta (008) y se apunta solo con un cierre, no con una reacción (010). Más en [El registro de decisiones](../conceptos/registro-de-decisiones.md).
  - **Turnos y ritmo:** escribir y enviar en dos pasos (003); medir el flujo de los hilos, no solo que cada rutina corre (011); lo que pide la persona va fuera de ciclo (012). Más en [Turnos y ritmo](../conceptos/turnos-y-ritmo.md).
  - **Las peticiones a la persona:** un issue es un foro que ella guía (002); una acción aprobada tarde se compara antes con el estado actual (005); una acción, una sola petición (006). Más en [La persona decide, los agentes ejecutan](../conceptos/la-persona-decide.md).
  - **Herramientas antes que memoria:** una regla que se rompe más de dos veces se comprueba con una herramienta (009); una rutina con datos de fuera necesita una segunda vía que no comparta el fallo (013). Más en [Proponer, probar, adoptar](../conceptos/proponer-probar-adoptar.md).

Varias lecciones dejan cosas como propuesta y lo dicen: la comprobación de la firma en cada PR ([009](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/009-la-firma-que-dependia-de-acordarse.md)) y la marca «fuera de ciclo» automática ([012](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/012-lo-que-pide-la-persona-va-fuera-de-ciclo.md)).

## Lo que dice

- **Una persona decide lo que no se delega:** lo que se publica, se gasta o se borra, los servicios nuevos y los cambios de rumbo. «Eso no lo hace ningún agente» ([README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/README.md), requisitos). Más en [La persona decide, los agentes ejecutan](../conceptos/la-persona-decide.md).
- **Lo propio de cada equipo va en la configuración, no en el código:** nombres, repos y Apps del equipo salen de un JSON, para que la herramienta sirva a cualquier equipo ([herramientas/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/README.md)).
- **Material externo:** lo que no publica la persona, sola o con una de las Apps del equipo, se enseña aparte, no da turno y, si se dirige a agentes, la bandeja avisa ([herramientas/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/README.md); [equipo.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/equipo.py)). Más en [Material externo: datos, no órdenes](../conceptos/material-externo.md).
- **La bandeja dice qué toca:** `TE TOCA` cuando otro te pasa el turno; `SIGUES TÚ` cuando el turno y el último mensaje son tuyos, para que el trabajo arranque en esa ronda o se pase el turno; `ESPERA ÚNICA`, con un ciclo de revisiones en la configuración, cuando el anterior del ciclo aún no ha escrito: una sola espera de como mucho 10 minutos y se sigue ([herramientas/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/README.md)).
- **Hilos sin turno que esperan una fecha:** un hilo que se queda sin turno a propósito, porque espera una prueba o un día, lleva la etiqueta `hasta:AAAA-MM-DD` (fecha UTC). Hasta ese día ni la bandeja ni el tablón lo dan por parado; ese día la bandeja le saca al responsable `LLEGA LA FECHA`. El responsable puede escribir en un hilo sin turno, y dar turno quita la etiqueta ([herramientas/README](https://github.com/JosebaDG/harness/blob/d63423452ce784109af1122c163af7d264c95160/herramientas/README.md); [equipo.py](https://github.com/JosebaDG/harness/blob/d63423452ce784109af1122c163af7d264c95160/herramientas/equipo.py), `puede_escribir` y `lineas_fecha`).
- **El tablón:** `tablero` reescribe un issue fijado con tres partes: lo que le toca a la persona (el registro primero, luego las flags de espera, los hilos con su turno y los PR que piden su revisión), lo parado más de 3 días y los proyectos vivos. Con `--prueba` enseña el cuerpo sin escribir nada ([herramientas/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/README.md)).
- **Un fusible que avisa y no para:** cada 30 mensajes seguidos de agentes sin la persona, la bandeja pide al responsable que repase si el hilo avanza; un hilo sin turno ni mensajes en 3 días sale como parado ([equipo.py](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/herramientas/equipo.py), constantes del principio).
- **Lo público se revisa antes de publicar, y también los mensajes:** un secreto que llega a un commit se avisa y se rota aunque se corrija después; el mensaje del *squash* dice qué entra, no quién lo aprobó; los issues se enlazan, no se numeran como hilos ([nucleo/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/nucleo/README.md)). Más en [Revisar lo público antes de publicar](../conceptos/revision-de-lo-publico.md).
- **Atribución:** parte del material adapta ideas de ECC y de mattpocock/skills, con licencia MIT; los avisos completos están en [ATRIBUCION.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ATRIBUCION.md).

## Comprobado y no comprobado

- **Comprobado al ingerir:** el contenido de los archivos citados en `a0e1ac6`; que entre `a0e1ac6` y `d634234` solo cambian tres archivos de `herramientas/` (README, equipo.py y sus pruebas); que entre `e94ebfd` y `a0e1ac6` solo cambian `flujos/` y `ejemplos/` (18 archivos), así que lo citado del núcleo, las herramientas y los especialistas dice lo mismo; y que web solo tiene su README.
- **Lo que cuentan los ejemplos** es lo que dice la fuente: el Wiki no puede comprobar desde fuera los casos que relatan, porque vienen reescritos en genérico.
- **No comprobado aquí:** que las Actions pasen en verde ni que `pages.yml` haya publicado algo. El Wiki solo lee la fuente; no ejecuta sus herramientas.

## Afirmaciones vivas

Se revisan en cada repaso semanal:

- el repo está «en construcción»: del contenido han entrado el núcleo, los especialistas, los flujos y los ejemplos; web aún no ([README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/README.md));
- «No damos un tiempo de arranque: todavía no está medido» ([README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/README.md));
- el estado de cada flujo: escaparate web «probado una vez», novela a vídeo «sin probar» ([flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md));
- las especialidades y los procedimientos que citan flujos y fichas «llegan en otro PR» ([flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md));
- dos gorros del escaparate web siguen «sin ficha todavía» (redactor de lo público y guardián de la voz) y su paso es provisional ([escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md));
- la web no publica nada mientras `web/` no tenga `index.html` ([pages.yml](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/.github/workflows/pages.yml)).
