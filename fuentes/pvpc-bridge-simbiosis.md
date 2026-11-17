# Pvpc-bridge · docs/simbiosis

Página de fuente: la carpeta que cuenta cómo una persona y un equipo de agentes de IA hicieron Pvpc-bridge, un proyecto público sobre el precio horario de la luz.

- **Repositorio:** [JosebaDG/Pvpc-bridge](https://github.com/JosebaDG/Pvpc-bridge) (público).
- **Versión citada:** commit [`3ae0060`](https://github.com/JosebaDG/Pvpc-bridge/tree/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis), el último que cambia la carpeta (18 de octubre de 2026).
- **Ingerida:** 2026-11-16.

## Qué es

Nueve documentos en Markdown. El [README](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/README.md) dice que el código es lo de menos: lo que quiere enseñar es la capacidad de trabajo que da combinar el criterio de una persona con agentes que proponen y ejecutan. La carpeta crece con el proyecto: cada decisión, error o atasco resuelto se añade en el mismo PR que el cambio de código.

| Documento | De qué trata |
|---|---|
| [01 · Historia](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/01-historia.md) | De consultar el precio a mano a un repositorio público, en cuatro días. |
| [02 · Roles y reglas](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md) | Quién decide, quién ejecuta y cómo se pasa la información. |
| [03 · Flujo en GitHub](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/03-flujo-github.md) | Issue, rama, PR, comprobaciones, revisión y fusión. |
| [04 · Fricciones](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md) | Ocho atascos reales, cómo se resolvieron y qué se aprendió. |
| [05 · Acceso a GitHub](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/05-conectar-github-device-flow.md) | Cómo un agente sube código sin ver una contraseña. |
| [06 · Cómo replicarlo](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md) | Lecciones para quien quiera trabajar así. |
| [07 · La web](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/07-la-web.md) | La web del proyecto, PR a PR. |
| [08 · El servidor MCP](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/08-el-servidor-mcp.md) | De script a servicio. |

En esta ingesta de prueba se leyeron a fondo el README y los documentos 01, 02, 03, 04 y 06. Los documentos 05, 07 y 08 quedan solo listados: se ingieren en una pasada propia.

## Lo que dice

- **Reparto de fondo:** la persona trae la necesidad y el criterio, decide y valida contra la realidad; los agentes proponen y ejecutan ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md)). Más en [La persona decide, los agentes ejecutan](../conceptos/la-persona-decide.md).
- **Varios agentes no son redundancia:** cuando uno se atasca, otro llega con otra idea, y lo que hace uno lo revisa otro ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md); fricción 4 en [04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md)).
- **Comprobado, estimado o supuesto:** cada afirmación técnica dice de dónde sale; lo raro no se borra, se etiqueta y se comprueba ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md), fricciones 2 y 3 en [04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md)). Más en [Comprobado, estimado o supuesto](../conceptos/comprobado-o-supuesto.md).
- **GitHub como memoria compartida:** los agentes no comparten memoria ni canal; las issues, los PR y un tablón de coordinación sustituyen a pegar mensajes a mano. Los mensajes entre agentes deben entenderse sin contexto ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md), fricción 6 en [04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md)).
- **Hablar para pensar, escribir para recordar:** lo que se decide de voz se pasa a una issue o a un PR, porque la voz no deja rastro ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md), fricción 7 en [04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md)).
- **El ciclo de un cambio:** issue → rama → commits pequeños → PR → comprobaciones automáticas → revisión → fusión → limpieza; los agentes no borran nada ([03](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/03-flujo-github.md)).
- **Lo privado, separado desde el primer día:** un archivo de ejemplo público junto al real, que queda fuera del repositorio ([06](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md), punto 7).
- **Acceso sin secretos a la vista:** el agente sube código con un acceso de permisos acotados, sin contraseñas ni tokens pegados ([04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md), fricción 4).
- **Cortesía con quien da los datos:** caché local y peticiones espaciadas a la API pública ([04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md), fricción 8).
- **Empezar por una molestia real y pequeña, y dictar requisitos, no soluciones** ([06](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md), puntos 1 y 2).

## Contradicción interna

Sobre quién fusiona un PR, la fuente dice cosas distintas en el mismo commit:

- [03](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/03-flujo-github.md), paso 7: «La persona pulsa el botón».
- [06](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md), punto 11: «Los agentes abren PR; tú fusionas».
- [02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md), regla 1: un agente revisor fusiona si se cumplen cuatro condiciones; si no, decide la persona.

Lo más probable es que el 03 sea anterior y no se pusiera al día, pero no está comprobado. El 06 puede estar así a propósito: es un consejo para quien empieza a replicar el método, no la descripción de cómo trabaja hoy este equipo. Se señala aquí; el Wiki no toca la fuente.

## Afirmaciones vivas

Frases de la fuente que pueden dejar de ser verdad sin que nadie edite la carpeta. Se revisan en cada repaso semanal:

- el equipo es de una persona y cuatro agentes ([README](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/README.md));
- quién hace qué en cada papel ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md));
- la web tiene una única publicación automática ([02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md)).
