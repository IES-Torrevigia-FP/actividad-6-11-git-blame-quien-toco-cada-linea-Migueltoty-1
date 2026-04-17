# Reflexión sobre el uso de `git blame`

### 1. ¿Para qué usarías `git blame` en un equipo?
Usaría `git blame` principalmente como una herramienta de arqueología de código para:
- **Depurar bugs:** Identificar cuándo y por qué se cambió una línea que ahora causa problemas.
- **Entender el contexto:** Leer el mensaje del commit asociado a una línea para comprender la intención del autor original.
- **Colaboración eficiente:** Saber quién es la persona con más contexto sobre un módulo específico para hacerle preguntas precisas, evitando interrumpir a otros miembros del equipo.

### 2. ¿Por qué es mala idea usar blame para “señalar culpables” y cómo se puede enfocar de forma constructiva?
Usar `git blame` para señalar culpables crea una cultura de miedo y defensiva, lo que lleva a los desarrolladores a evitar tomar riesgos o mejorar código ajeno por miedo a ser "culpados" si algo falla. 
El enfoque constructivo es tratarlo como una **búsqueda de contexto**. No importa *quién* cometió el error, sino *qué* podemos aprender de por qué ocurrió ese error (falta de tests, requisitos ambiguos, etc.) para mejorar el proceso del equipo.

### 3. Dos buenas prácticas para un blame útil
1. **Commits pequeños y atómicos:** Si cada commit hace una sola cosa, el mensaje asociado en `git blame` será muy descriptivo y útil.
2. **Separar refactorizaciones de cambios lógicos:** Si haces un re-formateo masivo de un archivo, todas las líneas aparecerán bajo tu nombre, "quemando" el historial útil. Es mejor hacer el formateo en un commit separado (y usar herramientas como `.git-blame-ignore-revs` si es posible) para mantener la autoría de la lógica original.
