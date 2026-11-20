# Afirmaciones vivas

Página de concepto: frases que pueden dejar de ser verdad sin que nadie toque el texto, y qué se hace con ellas.

## Qué son

Lo que se dice de algo automático o que cambia solo («cada día», «se actualizan solos», «más de cien», quién hace qué, un estado) puede volverse falso mientras la página sigue igual. El flujo del escaparate web cuenta un caso real: una web decía que sus datos se actualizaban solos cada día cuando la fuente llevaba semanas parada ([harness, escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md), «Reglas del flujo»).

## Qué se hace

- **En una web:** el paso de las cifras las marca, y cada una se reescribe con fecha o entra en una comprobación sin agente ([escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md)). En la primera prueba, el lector en frío cambió «desde octubre» por una fecha con año ([primera prueba](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/primera-prueba-escaparate-web.md)).
- **Los recuentos:** cada cifra que sale se cuenta siempre con la misma consulta, escrita en el flujo del proyecto, y se anota con su fecha, para que dos personas que cuentan lleguen a lo mismo ([escaparate-web.md](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md), «Qué se automatiza y qué no»).
- **En este Wiki:** cada página de fuente lista sus afirmaciones vivas, y el repaso semanal las vuelve a mirar ([AGENTS.md](../AGENTS.md#repaso-lint)).

## Comprobado y no comprobado

- **Comprobado:** la regla y el caso, leídos en el commit `a0e1ac6`.
- **No comprobado:** si la comprobación sin agente que propone el flujo existe ya. La fuente la pone como siguiente paso, y darla de alta lo decide la persona.

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [Comprobado, estimado o supuesto](comprobado-o-supuesto.md)
- [Flujos: esqueleto y adaptador](flujos-esqueleto-y-adaptador.md)
