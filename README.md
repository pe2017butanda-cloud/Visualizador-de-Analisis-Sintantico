# Visualizador de análisis sintáctico predictivo LL(1)

Aplicación web que muestra, paso a paso, cómo funciona un analizador sintáctico predictivo LL(1): conjuntos FIRST y FOLLOW, matriz predictiva y simulación de la pila.

## Datos del proyecto

| | |
|---|---|
| **Autor** | Butanda López Pablo Ernesto |
| **No. de control** | 23200987 |
| **Materia** | Lenguajes y Autómatas I |
| **Profesor** | MCC. Pérez Spíndola Diego David |
| **Actividad** | Act. 2 – Visualizador de análisis sintáctico |
| **Fecha** | 25/11/2026 |

## ¿Qué hace?

- Permite escribir una gramática o elegir un ejemplo precargado.
- Identifica automáticamente los terminales y no terminales.
- Calcula los conjuntos **FIRST** y **FOLLOW**.
- Genera y muestra la **matriz predictiva LL(1)**.
- Detecta conflictos y recursión por la izquierda (indica si la gramática no es LL(1)).
- Analiza cadenas **paso a paso**, mostrando la pila, la entrada pendiente y la producción aplicada.
- Indica si la cadena es **aceptada** o **rechazada** y por qué.

## Cómo usarlo

1. Descarga o clona el repositorio.
2. Abre el archivo `index.html` en tu navegador (no necesita instalación ni servidor).
3. Escribe una gramática o elige un ejemplo y presiona **Analizar** (o `Ctrl + Enter`).
4. Escribe una cadena y usa los botones para avanzar paso a paso.

### Formato de la gramática

```
E  → T E'
E' → + T E' | ε
T  → F T'
T' → * F T' | ε
F  → ( E ) | id
```

- Una producción por línea, con alternativas separadas por `|`.
- Se acepta `→` o `->`. La cadena vacía se escribe `ε`, `eps`, `epsilon` o `λ`.
- La primera línea define el símbolo inicial.

## Ejemplos incluidos

| Gramática | Cadenas de prueba |
|---|---|
| `E → T E'` … (expresiones sencillas) | `id+id`, `id*id`, `id+id*id`, `(id+id)*id`, `id+*id` |
| `S → aSb \| ε` | `ab`, `aabb`, `aaabbb`, `aab`, `abb` |
| `S → a S \| a` (extra, no LL(1)) | `a`, `aa` |
| `E → E + T \| T` (extra, recursión izquierda) | `id+id` |

## Tecnologías

HTML, CSS y JavaScript (un solo archivo, sin dependencias).

## Documentación

La documentación técnica (objetivo, funcionamiento, FIRST y FOLLOW, matriz predictiva, capturas, ejemplos y conclusión) se encuentra en `Documentacion_Visualizador_LL1.docx`.
