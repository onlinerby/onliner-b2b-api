# Экспорт данных

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions

Возвращает список позиций для указанного товара. В версии `v1` цена позиции всегда возвращаются в `USD`,
в версии `v2` есть возможность указать валюту. Если валюта не задана, цены возвращаются в валюте, указанной для позиции.

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions**
- HTTP-метод **GET**
- Формат ответа **`CSV`|`JSON`|`XML`**

### Параметры

- Версия `v1`

    *нет параметров*

- Версия `v2`

    -   `currency` [optional] - Валюта, в которой нужно вернуть цены (`BYR`, `USD` или `EUR`).
        - Если параметр не передан, то цены позиций будут возвращены в той валюте, которая указана в списке позиций.
        - Если передана неправильная валюта, будет возвращена ошибка:

        ```
HTTP/1.1 400 Bad Request
{"errors": ["Unknown currency code CODE_SENT"]}
```
    - Если параметр `currency` передан пустым, будет возвращена ошибка:

        ```
HTTP/1.1 400 Bad Request
{"errors": ["'currency' can not be empty"]}
```

Вне зависимости от того, в каком формате данные запрашиваются, текст ошибки возвращается в формате `json`.

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

- для версии `v1`

    - `json` - application/json
    - `xml` - application/xml
    - `csv` - text/csv

- для версии `v2`

    - `json` - application/vnd.onliner.v2+json
    - `xml` - application/vnd.onliner.v2+xml
    - `csv` - application/vnd.onliner.v2+csv

### Пример. Список позиций для товара

- Версия `v1`

    ```
GET /v2/sections/2/manufacturers/851/products/53808/positions
Accept: application/vnd.onliner.v2+json
```

    ```json
[
    {
        "id":"4",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":200,
        "currency":"USD",
        "status":"спец",
        "comment":"Test1",
        "warranty":"12",
        "delivery":"на следующий день",
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

- Версия `v2`

    ```
GET /v2/sections/2/manufacturers/851/products/53808/positions
Accept: application/vnd.onliner.v2+json
```

    ```json
[
    {
        "id":"4",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":200,
        "currency":"EUR",
        "status":"спец",
        "comment":"Test1",
        "warranty":"12",
        "delivery":"на следующий день",
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

### Пример 2. Передана неправильная валюта для экспорта
```
GET /v2/sections/2/manufacturers/851/products/53808/positions?currency=FOO
Accept: application/vnd.onliner.v2+json
```
```
HTTP/1.1 400 Bad Request
{"errors": ["Unknown currency code FOO"]}
```

### Пример 3. Передан парамерт `currency` без значения
```
GET /v2/sections/2/manufacturers/851/products/53808/positions?currency=
Accept: application/vnd.onliner.v2+json
```
```
HTTP/1.1 400 Bad Request
{"errors": ["'currency' can not be empty"]}
```
