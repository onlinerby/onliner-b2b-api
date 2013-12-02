# Отчет по импорту

## GET /pricelists/{pricelistId}/status

Возвращает статус обработки прайс-листа

- Ресурс **/pricelists/{pricelistId}/status**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример 1. Получение статуса несуществующего прайс-листа

```
GET /pricelists/51b056d8ee8a1efa1b000099/status
```

```
HTTP/1.1 404 Not Found
```

### Пример 2. Статус обработки прайс-листа

```
GET /pricelists/51b056d8ee8a1efa1b000001/status
```

```json
{
    "id": "51b056d8ee8a1efa1b000001",
    "shopId": 1,
    "statusCode": "STATUS_PROCESS_ERROR",
    "statusText": "Обработан с ошибками",
    "date": "2013-06-06 12:31:04",
    "processedCount": 6,
    "errorsCount": 2
}
```

### Описание полей ответа

- **id** Уникальный идентификатор загруженного прайс-листа
- **shopId** Уникальный идентификатор магазина
- **statusCode** Код статуса
    - STATUS_WAITING Не обработан
    - STATUS_IMPORT_ERROR Ошибка импорта
    - STATUS_PROCESS_ERROR Обработан с ошибками
    - STATUS_OK Обработан
    - STATUS_PROCESSING В обработке
- **statusText** Текст статуса
- **date** Дата загрузки прайс-листа
- **processedCount** Кол-во обработанных позиций прайс-листа
- **errorsCount** Кол-во ошибок, возникших во время обработки
    - Отчет об ошибках [/pricelists/{pricelistId}/report](report.md)
