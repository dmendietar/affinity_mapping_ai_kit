# Affinity mapping con IA (Incubatec)

Estructura modular del prompt de affinity mapping. Cada carpeta contiene una pieza del prompt; la última carpeta (`07_cadena_prompts`) tiene los prompts a ejecutar, que hacen referencia a los archivos de las demás carpetas.

## Estructura

| Carpeta | Qué contiene | ¿Se edita por startup? |
|---|---|---|
| `00_rol/` | Rol experto que asume la IA | No |
| `01_contexto/` | Contexto del startup, problema, segmento e hipótesis del equipo | **Sí, siempre** |
| `02_entrevistas/` | Transcripciones de entrevistas y validaciones | **Sí, siempre** |
| `03_metodologia/` | Objetivos del análisis, codificación abierta y axial, criterios de priorización | No (salvo ajustes del programa) |
| `04_reglas/` | Reglas e instrucciones de calidad del análisis | No |
| `05_formato_salida/` | Plantillas de salida de cada paso | No |
| `06_resultados/` | Donde se guardan las salidas de cada paso de la cadena | Se llena al ejecutar |
| `07_cadena_prompts/` | Prompt único y cadena de prompts paso a paso | No |

## Cómo usarlo

1. Completa los 4 archivos de `01_contexto/` (reemplaza cada `[COMPLETAR]`).
2. Copia las transcripciones en `02_entrevistas/` siguiendo la convención de nombres de su README.
3. Elige cómo ejecutar:
   - **Cadena (recomendada):** ejecuta en orden los prompts `07_cadena_prompts/01` a `04`. Cada paso guarda su salida en `06_resultados/` y el siguiente la usa como insumo. Esto sigue la lógica del Taller 07: primero codificar (abierta y axial) y después agrupar en el affinity map.
   - **Rápido:** ejecuta `07_cadena_prompts/00_prompt_unico.md` para hacer todo en una sola pasada (útil con pocas entrevistas).
4. Revisa los resultados en `06_resultados/` y llévalos al taller.

### Ejecutar con Claude (Cowork / Claude Code) con acceso a la carpeta

Abre la carpeta `affinity_ia` y escribe, por ejemplo:

> Ejecuta el prompt `07_cadena_prompts/01_codificacion_abierta.md`.

Claude leerá los archivos referenciados y guardará el resultado en `06_resultados/`.

### Ejecutar en un chat sin acceso a archivos

Pega el contenido del prompt y, debajo, el contenido de cada archivo que referencia (o adjúntalos). Al terminar cada paso, guarda la respuesta en `06_resultados/` con el nombre indicado.
