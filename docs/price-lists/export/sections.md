# Экспорт данных

## GET /sections/{sectionId}/positions

Возвращает список позиций для указанного раздела

- Ресурс **/sections/{sectionId}/positions**
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

### Пример 1. Список позиций для раздела в валюте, указанной для позиции

- Версия `v1`

    ```
GET /sections/2/positions
Accept: application/json
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
    },
    {
        "id":"5",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":250,
        "currency":"USD",
        "status":"спец",
        "comment":"Test2",
        "warranty":"12",
        "delivery":"нет",
        "isCashless":"нет",
        "isCredit":"нет"
    },
    {
        "id":"6",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":300,
        "currency":"USD",
        "status":"нет",
        "comment":"Test3",
        "warranty":"12",
        "delivery":"платная",
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

- Версия `v2`

    ```
GET /v2/sections/2/positions
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
    },
    {
        "id":"5",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":250,
        "currency":"EUR",
        "status":"спец",
        "comment":"Test2",
        "warranty":"12",
        "delivery":"нет",
        "isCashless":"нет",
        "isCredit":"нет"
    },
    {
        "id":"6",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":300000,
        "currency":"BYR",
        "status":"нет",
        "comment":"Test3",
        "warranty":"12",
        "delivery":"платная",
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

### Пример 2. Передана неправильная валюта для экспорта
```
GET /v2/sections/2/positions?currency=FOO
Accept: application/vnd.onliner.v2+json
```
```
HTTP/1.1 400 Bad Request
{"errors": ["Unknown currency code FOO"]}
```

### Пример 3. Передан парамерт `currency` без значения
```
GET /v2/sections/2/positions?currency=
Accept: application/vnd.onliner.v2+json
```
```
HTTP/1.1 400 Bad Request
{"errors": ["'currency' can not be empty"]}
```
