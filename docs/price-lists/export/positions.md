# Экспорт данных

## GET /positions

Возвращает полный список позиций магазина

- Ресурс **/positions**
- HTTP-метод **GET**
- Формат ответа **csv | json | xml**

### Параметры

- **currency** [optional] Валюта, в которой нужно вернуть цены
    - **BYR**
    - **USD**
    - **EUR**

Если параметр не передан, то цены позиций будут возвращены в той валюте, которая указана в списке позиций.
Если передана неправильная валюта, то будет возвращена ошибка.

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

- CSV
    - Accept: text/csv
- JSON
    - Accept: application/json
- XML
    - Accept: application/xml

### Пример 1. Список позиций магазина

```
GET /positions
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
GET /positions?currency=blah
Accept: application/json
```
```
HTTP/1.1 400 Bad Request

{
    "errors": {"Unknown currency code blah"}
}
```

### Пример 3. Параметр валюты задан, но его значение отсутствует
```
GET /positions?currency=
Accept: application/json
```
```
HTTP/1.1 400 Bad Request

{
    "errors": {"Field 'currency' cannot be empty"}
}
```
