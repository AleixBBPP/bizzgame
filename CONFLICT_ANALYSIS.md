# Análisis de conflictos de merge (River Girona)

## Estado actual del repositorio
- En esta rama (`work`) **no hay marcadores de conflicto** (`<<<<<<<`, `=======`, `>>>>>>>`) en `styles.css`, `index.html` ni `script.js`.
- El fichero `styles.css` contiene una única versión coherente (sin duplicados completos de bloques `:root`, `body`, `.hero`, etc.).

## Por qué te siguen apareciendo conflictos en GitHub
Aunque aquí el archivo esté limpio, GitHub puede seguir mostrando conflictos si:

1. La rama base (`main`) cambió las mismas líneas que esta rama en `styles.css`.
2. Existen commits distintos tocando las mismas zonas (por ejemplo paleta/hero/botón) y Git no puede decidir automáticamente.
3. El editor web de conflictos de GitHub muestra zonas aproximadas repetidas cuando varias ediciones se solapan cerca de los mismos bloques CSS.

## Zonas típicas que colisionan (en este caso)
- Variables de color en `:root`.
- Fondos del `body` y `.hero`.
- Reglas de `.btn` y bloques de tarjetas (`.stats article, .card, .events article`).

## Resolución recomendada (manual en GitHub)
Cuando abras el editor de conflictos en GitHub para `styles.css`:

1. **Qué conservar como base visual**: la versión que incluye esta paleta:
   - `rgb(54, 23, 16)`
   - `rgb(143, 52, 31)`
   - `rgb(168, 115, 101)`
2. Si aparece duplicado de bloques, **deja solo una copia** de cada selector.
3. Comprueba que exista una sola definición de:
   - `:root`
   - `body`
   - `.hero`
   - `.btn`
   - `.stats article, .card, .events article`
   - `footer`
4. Guarda la resolución y marca como resuelto.

## Verificación final tras resolver
- Abrir la vista de archivo final y buscar que **no** existan marcadores de conflicto.
- Confirmar que las reglas no estén duplicadas.
- Cargar la web y verificar que:
  - Fondo cálido oscuro visible.
  - Botón con gradiente terracota/clay.
  - Tarjetas con borde cálido.

## Nota práctica
Si quieres minimizar futuros conflictos, evita editar las mismas zonas de `styles.css` en varias ramas paralelas (sobre todo `:root` y `.hero`).
