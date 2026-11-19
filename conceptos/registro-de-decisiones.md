# El registro de decisiones

Página de concepto: lo decidido vive en el repo, en un archivo y en unas marcas sobre los issues, y gana a cualquier otra versión.

## Qué es

«Si no está en el repo, no existe.» Los chats se comprimen y las rutinas arrancan con una foto vieja, así que lo decidido vive en dos sitios y en ninguno más: un `DECISIONES.md` en el repo del canal, con una línea por decisión, y las flags del issue o del PR ([harness, protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «El registro»).

Cada línea lleva fecha, estado, qué, quién, dónde y lo que le queda a la persona ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md)). Los estados son cuatro: `decidido`, `aparcado`, `espera:<persona>` y `sustituido` ([plantilla del registro](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/plantilla-decisiones.md)).

## Las reglas

Todas salen del [protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), apartado «El registro»:

- **Mismo turno.** Cuando la persona decide algo, quien lo recibe lo apunta en ese mismo turno, aunque la decisión llegue por un chat.
- **Antes de pedir o de hacer, se mira.** Lo `decidido` o `aparcado` no se pide ni se presenta como pendiente, aunque el issue tenga casillas sin marcar.
- **Si chocan, gana el registro.** Una skill, un mensaje programado, un documento o la memoria de un agente pierden frente al registro. No se actúa sobre lo viejo: se avisa a la persona del desfase en una línea.
- **Cambiar es sustituir.** La línea vieja pasa a `sustituido` y la nueva va arriba. No se borra nada, para que se vea la historia.
- **Sin listas de decisiones copiadas** dentro de skills o mensajes programados: una copia es otra foto fija.
- **Sin registro no hay acción.** Si una revisión no puede leer el registro, solo lee.

## Las flags

Son marcas sobre issues y PR que se ponen y se quitan en segundos, también desde el móvil. `espera:<persona>` es lo único que se le puede pedir a la persona. Al poner `decidido`, `aparcado` o `sustituido`, la herramienta quita la espera, porque «una flag vieja que se queda puesta es justo el fallo que se quiere evitar» ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «Flags de decisión»).

## Cómo lo apoya la herramienta

`equipo.py apunta` añade las líneas y `equipo.py decisiones` las lee, junto con las flags del canal y de los repos de la configuración ([plantilla](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/plantilla-decisiones.md); [protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md)). Si el registro cambia, la bandeja lo dice con `REGISTRO CAMBIADO` y se lee antes de nada ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «Resiliencia»). El tablón pone el registro el primero en lo que le toca a la persona ([herramientas/README](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/README.md)).

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [La persona decide, los agentes ejecutan](la-persona-decide.md)
- [Turnos y ritmo](turnos-y-ritmo.md)
