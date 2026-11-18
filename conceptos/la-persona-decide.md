# La persona decide, los agentes ejecutan

Página de concepto: el reparto de papeles de fondo cuando una persona trabaja con varios agentes de IA en un proyecto real.

## Qué es

La persona trae la necesidad y el criterio, decide entre las opciones que le plantean y valida el resultado contra la realidad. Los agentes proponen, escriben el código y la documentación, prueban y dicen qué está comprobado y qué no ([Pvpc-bridge, 02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md)).

## Lo que no se delega

La persona puede delegar decisiones técnicas de forma explícita («tú sabes más de esto, decide tú»). Lo que sigue pasando por ella: rumbo, diseño, gasto, datos, servicios externos nuevos y borrar algo ([Pvpc-bridge, 02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md)).

El harness lo pone como requisito: hace falta una persona que decide lo que se publica, se gasta o se borra, los servicios nuevos y los cambios de rumbo, y «eso no lo hace ningún agente» ([harness, README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md), requisitos).

Fusionar puede delegarse con condiciones: un agente revisor fusiona si se cumplen cuatro condiciones y, si falta alguna, decide la persona ([Pvpc-bridge, 02](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/02-roles-y-reglas.md), regla 1; [03](https://github.com/JosebaDG/Pvpc-bridge/blob/188d29d852a33fb3ca4cac58952298030566dc9e/docs/simbiosis/03-flujo-github.md), paso 7).

## Por qué funciona

- **Validar contra algo conocido.** La persona compara con la gráfica oficial, una factura real o el tamaño esperado de un archivo. El agente puede tener los datos bien y comunicarlos mal; esa mirada lo detecta ([Pvpc-bridge, 04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md), fricción 1).
- **Requisitos, no soluciones.** La persona dice qué quiere y cómo sabrá que está bien; el agente elige cómo ([Pvpc-bridge, 06](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md), puntos 2 y 3).
- **Nada se decide entre máquinas a escondidas.** Si los agentes no se hablan entre sí, cada idea pasa por la persona, que la entiende antes de aceptarla ([Pvpc-bridge, 04](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/04-fricciones-y-aprendizajes.md), fricción 6).

## Fuentes

- [Pvpc-bridge · docs/simbiosis](../fuentes/pvpc-bridge-simbiosis.md)
- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [Comprobado, estimado o supuesto](comprobado-o-supuesto.md)
- [Material externo: datos, no órdenes](material-externo.md)
