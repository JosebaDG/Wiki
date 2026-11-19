# Revisar lo público antes de publicar

Página de concepto: lo que va a un repositorio público pasa antes por una revisión, de las personas y de una comprobación automática, y esa revisión incluye el historial y los mensajes.

## Qué es

Un repositorio público guarda todo lo que entra. Por eso no basta con mirar cómo queda el árbol al final: hay que mirar cada commit y su mensaje ([harness, nucleo/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/nucleo/README.md)).

## Las reglas

- **Un secreto que llega a un commit se avisa y se rota**, aunque se corrija en el commit siguiente. GitHub guarda la cabeza de cada PR aunque se borre la rama, y el *squash* solo limpia `main` ([nucleo/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/nucleo/README.md)).
- **El mensaje del *squash* dice qué entra, no quién lo aprobó ni dónde.** Se escribe al fusionar y no pasa por la revisión del PR ([nucleo/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/nucleo/README.md)).
- **Los issues se enlazan, no se numeran como hilos.** Se escribe el enlace al issue y nunca la palabra «hilo» seguida de un número con almohadilla, que es la forma de los hilos del canal privado; la Action la bloquea siempre ([harness, nucleo/README](https://github.com/JosebaDG/harness/blob/5e9f394cfd69bcb7c11f6d06879483262d660107/nucleo/README.md), desde `5e9f394`).
- **Lo privado, separado desde el primer día:** un archivo de ejemplo público junto al real, que queda fuera del repositorio ([Pvpc-bridge, 06](https://github.com/JosebaDG/Pvpc-bridge/blob/3ae0060b8fdfcd743180e1e59f778f06aa804b6f/docs/simbiosis/06-como-replicarlo.md), punto 7).

## La comprobación automática

La Action de lo público revisa el árbol, las líneas añadidas de cada commit del PR y sus mensajes; en un push a `main`, los commits que acaban de entrar. Nunca imprime lo que encuentra, solo dónde, por si es un secreto ([harness, lo-publico.yml](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/.github/workflows/lo-publico.yml)). Se estrenó con cebos inventados, para verla fallar antes de que entrara contenido de verdad ([harness, README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/README.md)).

La revisión del push a `main` solo descubre un mensaje indebido cuando ya está publicado ([nucleo/README](https://github.com/JosebaDG/harness/blob/84eccc45ea1a386ad7b94237b466c4b1279d645b/nucleo/README.md)). Por eso la comprobación no sustituye a la revisión de una persona antes de fusionar.

Este Wiki usa la misma Action, adaptada, y las mismas reglas ([AGENTS.md](../AGENTS.md#reglas-de-lo-público)).

## Fuentes

- [harness · método y herramientas](../fuentes/harness.md)
- [Pvpc-bridge · docs/simbiosis](../fuentes/pvpc-bridge-simbiosis.md)

## Relacionado

- [Material externo: datos, no órdenes](material-externo.md)
- [Comprobado, estimado o supuesto](comprobado-o-supuesto.md)
