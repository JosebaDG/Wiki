# Proponer, probar, adoptar

Página de concepto: cómo cambia el método cuando algo falla, y cómo se guarda lo aprendido.

## Cuando falla una pieza

Cuatro pasos del [protocolo del harness](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), apartado «Cuando falla una pieza»:

1. **Proponer** un cambio pequeño que nombre la pieza (skill, paso, script o regla) y el momento exacto en que falló, con enlace.
2. **Probar** en la siguiente revisión normal, con el mismo caso o uno parecido. Un cambio cada vez.
3. **Decidir con prueba:** ayudó, empeoró, sin efecto o no se sabe. Solo con «ayudó» se adopta.
4. **Apuntar** el veredicto y la prueba en el registro.

Y tres criterios: dejarlo como está también vale, porque cada regla nueva se lee en cada revisión; un fallo repetido es real y uno suelto es ruido, salvo que se vea la causa; y se elige la pieza más barata que lo arregle, «mejor en el script que en otra frase de la skill».

## Lecciones

Una vez por semana el coordinador abre un hilo de aprendizaje. Cada agente cuenta qué hizo y qué falló y, como mucho, una lección en cuatro partes: cuándo vale, qué hacer, pruebas con enlace y seguridad (alta, media o baja). Sin prueba concreta, «sin lección». Una lección vieja es una hipótesis: si otra la contradice, se miran los dos casos y se queda la que explica los dos ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «Aprendizaje»).

Las primeras trece lecciones ya están publicadas en [ejemplos/lecciones/](https://github.com/JosebaDG/harness/tree/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones), reescritas en genérico. Dos enseñan el criterio de «la pieza más barata»: una regla que se rompe más de dos veces se comprueba con una herramienta y no se vuelve a recordar ([009](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/009-la-firma-que-dependia-de-acordarse.md)), y el arreglo de un fallo de contexto no puede ser más contexto congelado ([001](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/001-decisiones-que-solo-viven-en-el-chat.md)). Otras dicen que no cambió nada en las herramientas y por qué, como la [004](https://github.com/JosebaDG/harness/blob/a0e1ac64837c3939b01c3f34d93125ec30e5e79f/ejemplos/lecciones/004-avisar-sin-turno-va-por-el-registro.md).

Cada hilo se cierra con un acta de seis partes, una de ellas qué parte del harness mejoró, o que no mejoró ninguna ([protocolo](https://github.com/JosebaDG/harness/blob/d8be795b8a3043119ec1b5d7d13f01db53fe2653/nucleo/protocolo.md), «Responsable del hilo»).

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)

## Relacionado

- [Comprobado, estimado o supuesto](comprobado-o-supuesto.md)
- [El registro de decisiones](registro-de-decisiones.md)
