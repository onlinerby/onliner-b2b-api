## Получение отчета по сопоставленным товарам импортера

### GET /importers/match-reports/{id}

`id` - идентификатор заявки на генерацию из ответа на запрос `POST /importers/match-reports/requests`.

При выполнении запроса должен быть указан токен авторизации.

### Пример запроса

```http
GET /importers/match-reports/5a16c41acab2fd0202641102
Accept: application/json
Authorization: Bearer <token>
```

### Пример ответа

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```
```json
{
    "id": "5a16c41acab2fd0202641102",
    "importerId": 1,
    "createdAt": "2018-04-01T12:00:00+03:00",
    "updatedAt": "2018-04-01T12:00:01+03:00",
    "status": "completed",
    "report": [
        {
            "product" : {
                "manufacturer": "Samsung",
                "article": "NC900",
                "description": "Samsung NC900 16Gb"
            },
            "positions": [
                {
                    "shop": {
                        "name": "Mobile Shop"
                    },
                    "price": {
                        "amount": "120.60",
                        "currency": "BYN"
                    }
                }
            ]
        }
    ]
}
```

### Описание полей ответа

|Параметр|Тип|Описание|
|---|---|---|
|id|string|Уникальный идентификатор|
|importerId|integer|Идентификатор импортера|
|createdAt|datetime|Время создания заявки на генерацию отчета|
|updatedAt|datetime|Время обработки заявки|
|status|string|Статус заявки: pending (ожидает обработки), completed (отчет готов), failed (ошибка генерации: попробуйте еще раз или обратитесь в техподдержку)|
|report|array|Результаты отчета, если статус - completed, или пустой массив|
|report.N.product.manufacturer|string|Производитель|
|report.N.product.article|string|Артикул|
|report.N.product.description|string|Описание товара|
|report.N.positions.N.shop.name|string|Название магазина|
|report.N.positions.N.price.amount|string|Цена|
|report.N.positions.N.price.currency|string|Валюта|

### Ответ при ошибке авторизации

```http
HTTP/1.1 401 Unauthorized
```

### Ответ в случае использования некорректного идентификатора

```http
HTTP/1.1 404 Not Found
```
