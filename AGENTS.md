# AGENTS.md · esquema del Wiki

Este archivo dice a cualquier agente cómo se mantiene el Wiki. Sigue el patrón [LLM Wiki de Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): fuentes originales que no se tocan, un wiki que escribe el modelo y un esquema (este archivo) que fija las reglas. Léelo entero antes de cambiar nada.

## Las tres capas

1. **Fuentes.** Documentos públicos de los proyectos y referencias externas. No se copian aquí ni se editan: se enlazan. Cada enlace va **fijado a un commit** (`/blob/<sha>/ruta`), nunca a `main`, porque una rama cambia sin avisar y un commit no.
2. **El wiki.** Páginas en Markdown que resumen, relacionan y contrastan las fuentes. Las escribe el modelo; las personas las leen y orientan.
3. **El esquema.** Este archivo. Si una regla cambia, se cambia aquí en el mismo PR.

## Carpetas

- `fuentes/`: una página por fuente ingerida. Qué es, qué dice, sus enlaces fijados y sus afirmaciones vivas.
- `conceptos/`: ideas que aparecen en una o varias fuentes. Cada concepto enlaza a las fuentes que lo apoyan.
- `index.md`: el catálogo. Cada página con su enlace y una línea de resumen, agrupadas por carpeta.
- `log.md`: el registro cronológico, solo para añadir.
- `web/`: la web pública, generada a partir de los `.md` con `web/generar.py`. No se escribe a mano: si cambias un `.md`, rehaz `web/` en el mismo PR.

Se crean carpetas nuevas (por ejemplo `proyectos/` o `comparativas/`) cuando hagan falta, y se apuntan aquí.

## Puerta única: solo fuentes públicas

El Wiki es público. Solo entra lo que ya es público:

- los repos públicos de los proyectos (por ejemplo harness y Pvpc-bridge) y sus webs;
- referencias externas publicadas.

Lo que no sea público no entra, ni siquiera resumido. Si algo vale, primero se publica en su proyecto, y después se ingiere desde allí.

## Reglas de lo público

- Se habla en genérico. No hay que contarlo todo.
- Nada de cómo se accede a los sistemas: rutas internas, nombres de máquinas, perfiles, identificadores de apps ni pasos de acceso concretos.
- Nada de rutinas, horarios ni lugares de personas. Nada de capturas de chats o de apps.
- Nada de datos personales, de menores ni de salud.
- Ningún secreto. Si se cuela uno, se revoca: borrarlo no lo quita del historial.
- Los mensajes de commit y de squash siguen las mismas reglas: dicen qué entra, no quién lo aprobó ni dónde.
- Ante la duda, fuera.

## Operaciones

### Ingerir una fuente

1. Leer la fuente original completa, en el commit que se va a citar.
2. Escribir su página en `fuentes/`: qué es, resumen con citas (enlace fijado por afirmación importante), contradicciones internas si las hay y afirmaciones vivas.
3. Crear o poner al día las páginas de `conceptos/` que toca. Una fuente puede tocar varias.
4. Añadir las páginas nuevas a `index.md`.
5. Añadir una entrada a `log.md`.
6. Todo en un PR. Otra persona del equipo revisa lo público antes de fusionar.

### Consultar

Para responder una pregunta con el Wiki: leer primero `index.md`, después las páginas que apunta, y responder citando las páginas y sus fuentes. Si la respuesta vale para más gente (una comparación, un análisis), se archiva como página nueva con su entrada en el índice y en el registro.

### Repaso (lint)

Una vez por semana:

- contradicciones entre páginas;
- fuentes que han avanzado desde el commit citado (la página puede haberse quedado vieja);
- **afirmaciones vivas**: frases que pueden dejar de ser verdad sin que nadie toque la página (un número de miembros, quién hace qué, un estado);
- páginas huérfanas, sin enlaces que lleguen a ellas;
- conceptos citados sin página propia.

Lo que se arregle va en un PR; lo que no, se apunta en la entrada del registro.

## Formato de `log.md`

Cada entrada empieza con la misma cabecera, solo con la fecha, sin horas:

```
## [AAAA-MM-DD] operación | título
```

`operación` es una de: `esquema`, `ingesta`, `consulta`, `repaso`. Debajo, dos o tres líneas: qué páginas se crearon o cambiaron y qué quedó pendiente. Así `grep "^## \[" log.md | tail -5` da las cinco últimas.

## Formato de las páginas

- Título con `#`, y debajo una línea que diga qué es la página.
- Enlaces internos relativos (`../conceptos/x.md`).
- Cada afirmación que venga de una fuente lleva su enlace fijado.
- Lo comprobado, lo estimado y lo supuesto se distinguen.
- En español, frases cortas, sin jerga sin explicar.
