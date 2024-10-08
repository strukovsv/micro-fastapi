# Zilog - Логирование

### [В начало](./index.md)

## Общие сведения

Логирование сервисов, осуществляется автоматически. Если не указаны переменные окружения, то сервис отправляет сообщения в json формате в stdout. Уровень логирования INFO.

- [code](/src/zilog/log.py)

## Переменные окружения

| Название      | Описание                         | Пример             | Default |
|---------------|----------------------------------|--------------------|---------|
| LOG_SERIALIZE | Сериализировать как json         | 0 или 1            |  json   |
| LOG_DIR       | Директорий логирования сообщений | /tmp/log/          |  stdout |
| LOG_FORMAT    | Формат plain сообщения           | {level}:{message}  |         |
| LOG_LEVEL     | Уровень отладки                  | INFO, DEBUG и т.п. |   INFO  |

- *LOG_SERIALIZE* - установка значения в 1 , вызывает формирование отладочного сообщения в форме json (по умолчанию). Иначе формируется как plain сообщение, с использованием переменной *LOG_FORMAT*

- *LOG_DIR* - указывается маршрут для записи файла логирования logging.log . В директории создается поддиректорий с текущей датой и временем и в него складывается файл лога. Если переменная не задана, то лог идет в stdout. По умолчанию сообщения отправляются в stdout. 

- *LOG_FORMAT* - формат plain сообщения

- *LOG_LEVEL* - уровень логирования 

## Использование в коде

```
from zilog-logguru import logger

logger.debug()

logger.info()

logger.error()
```
