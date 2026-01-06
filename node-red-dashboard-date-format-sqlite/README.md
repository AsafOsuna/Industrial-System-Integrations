# Node-RED Dashboard Date Formatter (SQLite)

Helper para normalizar fechas provenientes de **Node-RED Dashboard** (Date Picker / inputs) al formato compatible con **SQLite**:

`YYYY-MM-DD HH:mm:ss`

## Problema
Node-RED Dashboard puede entregar fechas como:
- ISO string (`2026-01-05T12:34:56.000Z`)
- Timestamp (ms)
- Valores vacíos / inválidos

SQLite normalmente espera fecha en formato texto tipo:
- `2026-01-05 06:34:56`

## Solución
Se provee la función `formatDashboardDate(input)` que:
- acepta `string | number | Date`
- devuelve `YYYY-MM-DD HH:mm:ss` (hora local)
- devuelve `""` si el input es inválido o vacío

## Uso (Bloque Function en Node-red)
```js
