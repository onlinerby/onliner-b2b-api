## Обновить наличие товаров

## PUT|PATCH /importers/stocklists

При выполнении запроса должен быть указан токен авторизации.

Если выполняется PUT запрос, то происходит полная перезапись всего списка для текущего импортера.
Если PATCH запрос - то обновлено будет наличие только по указанным SKU (можно присылать только изменения).

## Параметры запроса<a name="parameters"></a>

| Параметр                          | Тип     | Обязательный | Описание                                                                                                                                                             |
|-----------------------------------|---------|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| product                           | object  | да           | Объект с информацией о товаре                                                                                                                                        |
| product.manufacturer              | string  | да           | Название производителя (брэнда)                                                                                                                                      |
| product.article                   | string  | да           | Артикул товара (SKU, partnumber)                                                                                                                                     |
| product.ean13                     | string  | нет          | EAN-13 код товара (https://ru.wikipedia.org/wiki/European_Article_Number)                                                                                            |
| product.description               | string  | нет          | Описание товара, сюда можно передать название товара и другую информацию, позволяющую понять, что это за товар                                                       |
| producer                          | object  | нет          | Объект с информацией о производителе                                                                                                                                 |
| producer.country                  | string  | нет          | Страна происхождения                                                                                                                                                 |
| producer.factory                  | string  | нет          | Завод-изготовитель                                                                                                                                                   |
| stock                             | object  | да           | Объект с информацией о наличии                                                                                                                                       |
| stock.status                      | string  | да           | Статус наличия: in_stock (есть на складе и доступен для покупки), run_out_of_stock (осталось мало или заканчивается), out_of_stock (нет на складе или нельзя купить) |
| stock.quantity                    | integer | нет          | Фактический остаток товара на складе (с той точностью, с которой можно его указать)                                                                                  |
| recommended_retail_price          | object  | нет          | Объект с информацией о рекомендованной розничной цене                                                                                                                |
| recommended_retail_price.amount   | string  | нет          | Рекомендованная розничная цена в формате "200.34" с копейками после точки                                                                                            |
| recommended_retail_price.currency | string  | нет          | Валюта, может быть только "BYN"                                                                                                                                      |
| package                           | object  | нет          | Объект с информацией об упаковке                                                                                                                                     |
| package.width                     | string  | нет          | Ширина с единицами измерения                                                                                                                                         |
| package.length                    | string  | нет          | Длина с единицами измерения                                                                                                                                          |
| package.height                    | string  | нет          | Высота с единицами измерения                                                                                                                                         |
| package.weight                    | string  | нет          | Вес с единицами измерения                                                                                                                                            |

## Пример запроса

```http
PUT /importers/stocklists
Accept: application/json
Authorization: Bearer <token>
Content-Type: application/json
```
```json
[
    {
        "product" : {
            "manufacturer": "Samsung",
            "article": "NC900",
            "ean13": "2400000032632",
            "description": "Samsung NC900 16Gb"
        },
        "producer": {
            "country": "Канада",
            "factory": "ООО Кленовый сироп, Монреаль, улица Каштановая 30"
        },
        "stock": {
            "status": "in_stock",
            "quantity": 900
        },
        "recommended_retail_price": {
            "amount": "120.60",
            "currency": "BYN"
        },
        "package": {
            "width": "100 мм",
            "length": "200 мм",
            "height": "300 мм",
            "weight": "200 г"
        }
    },
    ...
]
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

Соответствует формату ответа метода для [получения результата импорта наличия товаров](https://github.com/onlinerby/onliner-b2b-api/blob/master/docs/importers/status.md#описание-полей-ответа).

## Ответ при ошибке авторизации

```http
HTTP/1.1 401 Unauthorized
```
