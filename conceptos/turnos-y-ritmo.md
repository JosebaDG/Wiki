# Turnos y ritmo

Página de concepto: en cada hilo habla uno cada vez, y cada agente pasa por el canal en una revisión programada, en un orden fijo.

## Turnos

Reglas del [protocolo del harness](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), apartado «Turnos»:

- Solo escribe quien tiene el turno, y al escribir lo pasa: a otro agente, a la persona o a nadie. La herramienta se niega si el turno no es tuyo o si el hilo está en pausa.
- Un mensaje por hilo en cada revisión, sin mensajes de cortesía. Si no hay nada útil, una línea y el turno vuelve al responsable.
- Quien se queda el turno arranca el trabajo en su siguiente revisión o lo pasa con el porqué; la bandeja lo recuerda con `SIGUES TÚ`.
- Antes de preparar algo que pide el sí de la persona, se mira si ya hay algo igual esperando. Justo antes de ejecutar algo que lleva horas esperando, se compara con el estado actual.

La persona escribe cuando quiere y su último mensaje manda: `turno: <agente>` da el turno y `ALTO` o la etiqueta `pausa` paran el hilo ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «La persona»).

## Ritmo

Según el apartado «Ritmo» del [protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md):

- **Revisiones escalonadas en el orden del ciclo,** con unos minutos entre una y otra. El coordinador va el último: cierra, fusiona lo que autoriza el registro y reparte. Las horas van en la configuración, no en el código.
- **Si da igual a quién, el turno pasa al siguiente del ciclo,** para que la vuelta se complete en el mismo ciclo.
- **Una sola espera:** si el anterior del ciclo aún trabaja, se espera una vez, como mucho 10 minutos. Nunca bucles.
- **Salida rápida:** si la bandeja dice «NADA», la revisión termina ahí.
- **Lo que pide la persona va fuera de ciclo:** el ritmo sirve para pasarse el turno entre agentes, no para frenar a la persona.
- **Medir antes de ajustar:** el coordinador apunta en cada cierre las vueltas completas y las esperas usadas.

## Contra los bucles

Cada 30 mensajes seguidos de agentes sin la persona, la bandeja pide al responsable que repase. No para nada: si el hilo avanza, sigue; si da vueltas, el responsable lo pausa y se lo cuenta a la persona. Un hilo sin turno ni mensajes en 3 días sale como `PARADO` ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «Anti bucle» y «Responsable del hilo»; [equipo.py](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/herramientas/equipo.py), constantes del principio).

## Lo que enseñaron los fallos

Tres lecciones del harness, en el commit `a0e1ac6`: escribir el mensaje y enviarlo en dos pasos, para que no salga uno viejo ([003](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/003-el-mensaje-viejo-que-salio-por-el-nuevo.md)); medir cuántas vueltas da un hilo y no solo que cada rutina se ejecuta ([011](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/011-el-ritmo-que-nadie-miraba-entero.md)); y lo que pide la persona se hace en el momento y se cuenta aparte, fuera de ciclo ([012](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/012-lo-que-pide-la-persona-va-fuera-de-ciclo.md)). La primera prueba del escaparate web dice lo mismo desde otro lado: el cuello de botella fue el turno, no el trabajo ([primera prueba](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/primera-prueba-escaparate-web.md)).

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [El registro de decisiones](registro-de-decisiones.md)
- [La persona decide, los agentes ejecutan](la-persona-decide.md)
