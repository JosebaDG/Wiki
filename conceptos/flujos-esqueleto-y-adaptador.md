# Flujos: esqueleto y adaptador

Página de concepto: cómo un equipo de agentes escribe sus formas de trabajar de principio a fin sin empezar de cero en cada tipo de proyecto.

## Qué es un flujo

Un flujo dice qué gorros hacen falta, en qué orden y qué entrega cada uno, y si ya se ha probado en un trabajo real ([harness, flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md)). Los gorros son los de [Gorros: un rol por ciclo](gorros.md).

## Las dos partes

- **El esqueleto:** los pasos que valen para cualquier proyecto. El encargo, la redacción o construcción, la objeción de fondo, las cifras, lo público, el lector en frío, la última objeción, el empaquetado para la persona y publicar.
- **El adaptador:** lo que cambia según el tipo de proyecto. Qué vista previa ve la persona y qué prueba automática se pasa. Una web tiene uno; una app o un vídeo tendrán otro.

Así un flujo nuevo copia el esqueleto y solo escribe su adaptador ([flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md), «Esqueleto y adaptador»). La partición salió de la primera prueba real ([primera prueba](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/primera-prueba-escaparate-web.md), «Qué cambió en el harness»).

## Las reglas comunes

1. **Dos puertas de la persona:** el encargo con sus palabras al principio, y sí, no o cambios al final. En medio nada, salvo algo ya publicado que no debe estar: se avisa en el momento, porque despublicar es suyo. Más en [La persona decide, los agentes ejecutan](la-persona-decide.md).
2. **Un commit por paso,** con el gorro en el mensaje: `Gorro (quién): qué encontró -> qué cambió`. El rastro queda en `git log`.
3. **Quien hace una pieza no la evalúa.** Si un agente lleva varios gorros, lo dice y esos gorros quedan provisionales hasta que los repase otro.
4. **Un flujo pasa a «probado» solo con una prueba** en `ejemplos/`: qué pasó, qué funcionó, qué rozó y cuánto costó.

Fuente: [flujos/README](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/README.md), «Reglas para todos los flujos».

## El orden importa

En el [escaparate web](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/flujos/escaparate-web.md) la objeción de fondo va pronto, en el paso 1b, porque si llega al final se tira el trabajo de los pasos 2 a 6. Y de 2 a 4 el orden es fijo: primero lo que no es verdad, luego lo que no debe salir y luego lo que no se entiende, porque pulir una frase que después se quita es trabajo tirado. El paso de las cifras marca las [afirmaciones vivas](afirmaciones-vivas.md).

## Comprobado y no comprobado

- **Comprobado:** las reglas y los dos flujos, leídos en el commit `a0e1ac6`.
- **Según la fuente:** el escaparate web está probado una vez, con un coste de una tarde de un agente y unas 95 llamadas a herramientas; novela a vídeo está sin probar. Todavía no hay adaptador para una app.

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [Gorros: un rol por ciclo](gorros.md)
- [Revisar lo público antes de publicar](revision-de-lo-publico.md)
- [Afirmaciones vivas](afirmaciones-vivas.md)
