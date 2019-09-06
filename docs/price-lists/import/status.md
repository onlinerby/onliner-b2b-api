# Отчет по импорту

## GET /pricelists/{pricelistId}/status

Возвращает статус обработки прайс-листа

- Ресурс **/pricelists/{pricelistId}/status**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример 1. Получение статуса несуществующего прайс-листа

```http
GET /pricelists/51b056d8ee8a1efa1b000099/status
```

```http
HTTP/1.1 404 Not Found
```

### Пример 2. Статус обработки прайс-листа

```http
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

|Параметр|Тип|Описание|
|---|---|---|
|`id`|string|Уникальный идентификатор загруженного прайс-листа|
|`shopId`|integer|Уникальный идентификатор магазина|
|`statusCode`|string|Код статуса обработки|
|`statusText`|string|Текст статуса|
|`date`|string|Дата загрузки прайс-листа|
|`processedCount`|integer|Кол-во обработанных позиций прайс-листа|
|`errorsCount`|integer|Кол-во ошибок, возникших во время обработки|

Отчет об ошибках [/pricelists/{pricelistId}/report](report.md)

Возможные значения кода статуса обработки:

|Код|Описание|Комментарий|
|---|---|---|
|`STATUS_WAITING`|Не обработан|находится в очереди|
|`STATUS_IMPORT_ERROR`|Ошибка импорта|проблемы с определением формата|
|`STATUS_PROCESS_ERROR`|Обработан с ошибками||
|`STATUS_OK`|Обработан||
|`STATUS_OK_WITH_WARNINGS`|Обработан с предупреждениями||
|`STATUS_PROCESSING`|В обработке||
|`STATUS_PARSE_ERROR`|Ошибка валидации|синтаксические ошибки формата|
|`STATUS_PARSE_COLUMNS_ERROR`|Ошибка импорта|проблемы с колонками в именованном прайс-листе CSV|
