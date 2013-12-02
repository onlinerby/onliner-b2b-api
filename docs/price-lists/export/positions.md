# Экспорт данных

## GET /`<version>`/positions

Возвращает полный список позиций магазина

-   Ресурс **/**`<version>`**/positions**
-   HTTP-метод **GET**
-   Формат ответа `CSV`**|**`JSON`**|**`XML`

### Параметры

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
{"errors": ["'currency' can not be emty"]}
```

Вне зависимости от того, в каком формате данные запрашиваются, текст ошибки возвращается в формате `json`.

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

-   `json` - application/vnd.onliner.`<version>`+json;
-   `xml` - application/vnd.onliner.`<version>`+xml;
-   `csv` - application/vnd.onliner.`<version>`+csv.

### Пример 1. Список позиций магазина в валюте, указанной для позиции

```
GET /<version>/positions 
Accept: application/vnd.onliner.<version>+json
```

```json
[
  {
    "id": "4",
    "category": "MP3-плееры",
    "vendor": "Apple",
    "model": "iPod nano 16Gb (7th generation)",
    "price": 200,
    "currency": "USD",
    "status": "спец",
    "comment": "Test1",
    "warranty": "12",
    "delivery": "на следующий день",
    "isCashless": "нет",
    "isCredit": "нет"
  },
  {
    "id": "5",
    "category": "MP3-плееры",
    "vendor": "Apple",
    "model": "iPod nano 16Gb (7th generation)",
    "price": 250,
    "currency": "EUR",
    "status": "спец",
    "comment": "Test2",
    "warranty": "12",
    "delivery": "нет",
    "isCashless": "нет",
    "isCredit": "нет"
  },
  {
    "id": "6",
    "category": "MP3-плееры",
    "vendor": "Apple",
    "model": "iPod nano 16Gb (7th generation)",
    "price": 300000,
    "currency": "BYR",
    "status": "нет",
    "comment": "Test3",
    "warranty": "12",
    "delivery": "платная",
    "isCashless": "нет",
    "isCredit": "нет"
  }
]
```

### Пример 2. Передана неправильная валюта для экспорта

```
GET /<version>/positions?currency=FOO 
Accept: application/vnd.onliner.<version>+json
```
```
HTTP/1.1 400 Bad Request
{"errors": ["Unknown currency code FOO"]}
```

### Пример 3. Передан парамерт `currency` без значения

```
GET /<version>/positions?currency= 
Accept: application/vnd.onliner.<version>+json
```

```
HTTP/1.1 400 Bad Request
{"errors": ["'currency' can not be emty"]}
```
