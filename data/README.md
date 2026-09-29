# 📖 Datos del proyecto

Las tablas de origen están dentro del libro [`excel/walmart_resumen_ejecutivo_2012.xlsx`](../excel/walmart_resumen_ejecutivo_2012.xlsx) (hojas `raw_ventas`, `raw_departamento` y `raw_tiendas`). Fueron proporcionadas por el Bootcamp de TripleTen.

## Tablas de origen

### `raw_ventas` (95,880 filas · 5-feb-2010 a 26-oct-2012)

| Columna | Descripción |
| --- | --- |
| `tienda` | Identificador de la tienda (1 a 45) |
| `dept` | Código de departamento (15 códigos distintos) |
| `fecha` | Fecha de la semana de ventas |
| `ventas_semanales` | Ventas de la semana (USD). Hay 27 valores negativos |
| `esferiado` | Indica si la semana incluye un día festivo |
| `semana_limpia` | Año y número de semana |

### `raw_departamento` (14 filas)

| Columna | Descripción |
| --- | --- |
| `dept` | Código de departamento |
| `nombre_dept` | Nombre del departamento |

El código **16** aparece en las ventas pero no en este catálogo.

### `raw_tiendas` (45 filas)

| Columna | Descripción |
| --- | --- |
| `tienda` | Identificador de la tienda |
| `tipo` | Tipo de tienda (A: 22, B: 17, C: 6) |
| `tamaño` | Tamaño de la tienda (34,875 a 219,622). El enunciado lo indica en m²; conviene confirmar la unidad |

## Resultados incluidos

### `kpis_por_departamento_2012.csv`

Resultado de las tablas dinámicas, recalculado a partir de `raw_ventas` (coincide con la hoja `Pivot`).

| Columna | Descripción |
| --- | --- |
| `departamento` | Nombre del departamento (`no tiene departamento` para el código 16) |
| `ventas_2012` | Suma de ventas semanales de 2012 (USD) |
| `tamano_promedio` | Promedio del tamaño de las tiendas en las filas del departamento |
| `ventas_por_m2` | `ventas_2012 / tamano_promedio` (KPI 1) |
| `participacion_pct` | Porcentaje de las ventas totales de 2012 (KPI 2) |
| `filas` | Filas de ventas de 2012 del departamento |
| `tiendas` | Número de tiendas con ventas del departamento en 2012 |
