## Получение результата обновления списка ретейлеров

## GET /importers/retailers/{retailerListId}/status

`retailerListId` - идентификатор загруженного списка ретейлеров, из ответа на запрос `PUT /importers/retailers`

При выполнении запроса должен быть указан токен авторизации.

## Пример запроса

```http
GET /importers/retailers/5a55d8a2919872010a182d92/status
Accept: application/json
Authorization: Bearer <token>
Content-Type: application/json
```

## Пример ответа<a name="response"></a>:

```http
HTTP/1.1 202 Accepted
Content-Type: application/json; charset=utf-8
```
```json
{
    "id": "5a16c41acab2fd0202641102",
    "importerId": 1,
    "fileName": "retailer-list-2017-11-23.json",
    "size": 55,
    "date": "2017-11-23 15:50:34",
    "status": "STATUS_PROCESS_ERROR",
    "contentType": "json",
    "statusMessage": null,
    "errors": {
        "body": [
            {
                "id": "validation.invalid_json",
                "text": "Invalid or empty JSON body"
            }
        ]
    }
}
```

### Описание полей ответа<a name="fields"></a>:

| Параметр      | Тип    | Описание                                                                                        |
|---------------|--------|-------------------------------------------------------------------------------------------------|
| id            | string | Уникальный идентификатор загруженного списка                                                    |
| importerId    | int    | Идентификатор импортера                                                                         |
| fileName      | string | Имя файла, под которым были сохранены полученные данные в системе для импорта (наше внутреннее) |
| size          | int    | Размер полученного содержимого в байтах                                                         |
| date          | string | Дата и время получения данных для импорта. Формат (YYYY-MM-DD HH:MM:SS)                         |
| status        | string | Код статуса импорта данных                                                                      |
| contentType   | string | Тип полученных данных (пока поддерживается только json)                                         |
| statusMessage | string | Сообщение об ошибке, в случае проблем с добавлением полученных данных в очередь обработки       |
| errors        | object | Список валидационных ошибок                                                                     |

Возможные коды статуса импорта:
- STATUS_WAITING - Не обработан, находится в очереди
- STATUS_PROCESSING - В обработке
- STATUS_OK - Обработан
- STATUS_PARSE_ERROR - Ошибка валидации или парсинга данных
- STATUS_IMPORT_ERROR - Ошибка импорта
- STATUS_PROCESS_ERROR - Обработан с ошибками

### Возможные ошибки для поля errors:

| Параметр                   | И дентификатор ошибки            | Текст ошибки                                   |
|----------------------------|----------------------------------|------------------------------------------------|
| body                       | validation.invalid_json          | Invalid or empty JSON body                     |
| retailers                  | validation.required              | The retailers field is required                |
| retailers.N.unp            | validation.required              | The unp field is required                      |
| retailers.N.unp            | validation.string                | Value may only be a string                     |
| retailers.N.unp            | validation.format                | The string must contain only 9 digits          |
| retailers.N.manufacturer   | validation.string_or_array       | Value may be a string or array of strings      |
| retailers.N.manufacturer.M | validation.string                | Value may only be a string                     |
| retailers.N.articles       | validation.invalid_manufacturers | Articles may be stored only for 1 manufacturer |
| retailers.N.articles       | validation.string_or_array       | Value may be a string or array of strings      |
| retailers.N.articles.M     | validation.string                | Value may only be a string                     |

## Ответ при ошибке авторизации

```http
HTTP/1.1 401 Unauthorized
```

## Ответ в случае использования некорректного идентификатора импорта

```http
HTTP/1.1 404 Not Found
```
