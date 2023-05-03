## Получение результата импорта наличия товаров

## GET /importers/stocklists/{stockListId}/status

`stockListId` - идентификатор загруженного списка наличия, из ответа на запрос `PUT|PATCH /importers/stocklists`

При выполнении запроса должен быть указан токен авторизации.

## Пример запроса

```http
GET /importers/stocklists/5a55d8a2919872010a182d92/status
Accept: application/json
Authorization: Bearer <token>
Content-Type: application/json
```

## Ответ в случае успеха<a name="response"></a>:

```http
HTTP/1.1 202 Accepted
Content-Type: application/json; charset=utf-8
```
```json
{
    "id": "5a16c41acab2fd0202641102",
    "importerId": 1,
    "fileName": "stock-list-2017-11-23.json",
    "size": 55,
    "date": "2017-11-23 15:50:34",
    "status": "STATUS_WAITING",
    "contentType": "json",
    "statusMessage": null
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

Возможные коды статуса импорта:
- STATUS_WAITING - Не обработан, находится в очереди
- STATUS_PROCESSING - В обработке
- STATUS_OK - Обработан
- STATUS_PARSE_ERROR - Ошибка валидации или парсинга данных
- STATUS_IMPORT_ERROR - Ошибка импорта
- STATUS_PROCESS_ERROR - Обработан с ошибками

## Ответ при ошибке авторизации

```http
HTTP/1.1 401 Unauthorized
```

## Ответ в случае использования некорректного идентификатора импорта

```http
HTTP/1.1 404 Not Found
```
