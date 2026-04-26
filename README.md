# Database Incident Helper

![Bash](https://img.shields.io/badge/Shell-Bash-4EAA25?style=flat&logo=gnu-bash)
![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat&logo=python)
![PostgreSQL](https://img.shields.io/badge/DB-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)

> Этот набор включён в общий тулкит: см. `MIGRATION.md` и [`ops-core-utils`](../ops-core-utils).

Два инструмента для оперативной диагностики СУБД. Закрывают типичный сценарий: жалоба на тормоза в приложении → проверить состояние БД → найти тяжёлые запросы.

## Инструменты

**`pg_health.sh`** — комплексная проверка инстанса:
- ищет активный юнит systemd (`postgres`/`mariadb`/`mysql`) — не хардкодит имя сервиса
- проверяет порты 5432/3306 через `ss -tuln`
- смотрит место в `/var/lib/postgresql`

**`slow_query_parser.py`** — парсит лог PostgreSQL, ищет запросы медленнее порога (по умолчанию 1000 ms). Сортирует по длительности, показывает топ-5. Если лог не указан — генерирует демо-данные для проверки.

## Использование

```bash
# Быстрая проверка состояния базы
sudo ./pg_health.sh

# Найти запросы медленнее 2 секунд
python3 slow_query_parser.py /var/log/postgresql/postgresql-15-main.log 2000

# Запустить на демо-данных (без реального лога)
python3 slow_query_parser.py
```
