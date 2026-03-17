# Переехали в общий тулкит

Эту папку оставляю как “исходник”, а пользоваться удобнее отсюда:

- `..\enterprise-linux-ops-toolkit`

## Где искать в тулките

- Скрипты (bash): `enterprise-linux-ops-toolkit/modules/db_incident_helper/bin/`
- Python-команда в CLI: `enterprise-linux-ops-toolkit/src/elotoolkit/modules/db_incident_helper/`

## Как запускать теперь

```bash
elot db slow-queries /var/log/postgresql/postgresql-15-main.log --threshold-ms 2000
```

