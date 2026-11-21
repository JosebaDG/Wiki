# Higiene en proyectos con agentes

Página de concepto: trabajar con agentes acelera tanto la producción como la entropía; mantener un ecosistema sano exige cuatro hábitos concretos que evitan deuda invisible, deriva entre repositorios y fugas involuntarias.

## Qué es

Cuando un proyecto crece rápido con ayuda de agentes, el cuello de botella deja de ser escribir código o documentación y pasa a ser **editar, podar y mantener una única fuente de verdad**. Sin auditorías periódicas centradas en artefactos ejecutables (workflows, tests, configuración y tamaños de archivo), aparecen cuatro antipatrones recurrentes que ningún agente suele detectar mirando un solo repositorio de forma aislada.

## Los cuatro antipatrones

### 1. Presupuesto de contexto (compactar frente a acumular)

- **El síntoma:** un archivo vivo de estado o decisiones crece sin límite hasta superar decenas de miles de palabras.
- **Por qué duele:** cada vez que un agente lee ese archivo completo para saber qué está vigente, consume gran parte de su ventana de contexto, sube el coste y empeora la precisión en los detalles del medio.
- **La regla:** separar siempre el **estado vigente compacto** (por debajo de un techo claro, por ejemplo 15 KB) del **archivo histórico** fechado. Compactar no borra historia: la archiva y obliga a sintetizar qué sigue aplicando hoy.

### 2. Deriva de copias (fuente única frente a copiar y pegar)

- **El síntoma:** un mismo workflow o script se copia a mano en tres o cuatro repositorios. Al cabo de dos semanas, cada copia tiene mejoras distintas y huecos distintos.
- **Por qué duele:** los agentes son excelentes mejorando el archivo que tienen delante, pero rara vez propagan esa mejora a copias hermanas si nadie se lo ordena.
- **La regla:** centralizar las guardas comunes en un repositorio plantilla como *reusable workflows* (`workflow_call`) y consumirlos desde los demás repositorios fijados a un SHA o etiqueta concreta, nunca a una rama flotante.

### 3. Efecto Streisand en guardas de seguridad

- **El síntoma:** para impedir que un nombre interno o un proyecto privado aparezca en un repositorio público, se escribe ese patrón directamente dentro del workflow público de comprobación.
- **Por qué duele:** el propio archivo de seguridad acaba revelando en público lo que pretendía ocultar y rompe el carácter genérico de la plantilla.
- **La regla:** en un workflow público solo viven las reglas universales (formatos de tokens, rutas de sistema, convenciones genéricas). Cualquier lista de términos privados se inyecta desde secretos del repositorio y nunca se imprime en los registros.

### 4. Tests huérfanos (si no corre en CI, no existe)

- **El síntoma:** un PR añade pruebas unitarias que pasan en local, pero la carpeta de tests nunca se conecta al pipeline de integración continua.
- **Por qué duele:** un cambio futuro puede romper esa funcionalidad y el repositorio seguirá mostrando el indicador en verde, generando falsa confianza.
- **La regla:** antes de fusionar cualquier PR que añada pruebas nuevas, comprobar en los registros del propio pipeline de CI que esas pruebas se han ejecutado de verdad.

## Tres hábitos de mantenimiento

1. **Auditar artefactos antes que texto:** priorizar `.github/workflows/*.yml`, gestores de dependencias, `.gitignore`, tests y tamaños de archivo frente a lo que promete el `README.md`.
2. **Trabajar en borradores pequeños:** aislar cada mejora en su propia rama y *Draft PR* para validar en verde antes de tocar `main`.
3. **Cerrar o graduar laboratorios:** un repositorio experimental debe terminar graduado a producto o archivado con una ficha breve de lo aprendido, evitando acumular proyectos a medias.

## Relacionado

- [Revisar lo público antes de publicar](revision-de-lo-publico.md)
- [Registro de decisiones](registro-de-decisiones.md)
- [Proponer, probar, adoptar](proponer-probar-adoptar.md)
- [Comprobado, estimado o supuesto](comprobado-o-supuesto.md)
