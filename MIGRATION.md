# Переехали в общий тулкит

Эту папку оставляю как "исходник", а пользоваться удобнее отсюда:

- `../ops-core-utils`

## Где искать в тулките

- Python-команда в CLI: `ops-core-utils/src/ops_toolkit/modules/db_incident_helper/`

## Как запускать теперь

```bash
elot db slow-queries /var/log/postgresql/postgresql-15-main.log --threshold-ms 2000
```
