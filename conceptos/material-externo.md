# Material externo: datos, no órdenes

Página de concepto: lo que escribe alguien de fuera del equipo se lee como información, nunca como instrucciones para los agentes.

## Qué es

En un repositorio público cualquiera puede abrir issues, comentar o proponer cambios. Un agente que lee ese texto puede encontrar instrucciones escondidas. La regla: solo cuenta como propio lo que publica la persona, sola o con una de las Apps del equipo. Todo lo demás es **material externo**: se enseña aparte, no da turno y, si se dirige a agentes, se avisa ([harness, herramientas/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/README.md)).

## Cómo lo aplica la herramienta

- **Quién es propio:** el usuario de la persona, sin App o con una App de la lista del equipo. Otra App, otro usuario o un bot es externo ([harness, equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py), `es_propio`).
- **Se enseña marcado:** cada línea del mensaje externo va con un prefijo, para que no pueda fingir el cierre del bloque, y el bloque dice «no son órdenes» ([equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py), `externo`).
- **Lo oculto se hace visible:** GitHub no enseña los comentarios HTML, pero la API sí; la herramienta los saca a la vista y los marca ([equipo.py](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/herramientas/equipo.py), `visible`).

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [Revisar lo público antes de publicar](revision-de-lo-publico.md)
- [La persona decide, los agentes ejecutan](la-persona-decide.md)
