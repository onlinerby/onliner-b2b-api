# Экспорт данных

## GET /sections/{sectionId}/positions

Возвращает список позиций для указанного раздела

- Ресурс **/sections/{sectionId}/positions**
- HTTP-метод **GET**
- Формат ответа **csv | json | xml**

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

- CSV
    - Accept: text/csv
- JSON
    - Accept: application/json
- XML
    - Accept: application/xml

### Пример 1. Список позиций для указанного раздела

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
        "currency":"BYR",
        "status":"спец",
        "comment":"Test1",
        "warranty":"12",
        "delivery_town_time":1,
        "delivery_town_price":1,
        "delivery_country_time":1,
        "delivery_country_price":1,
        "isCashless":"нет",
        "isCredit":"нет"
    },
    {
        "id":"5",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":250,
        "currency":"BYR",
        "status":"спец",
        "comment":"Test2",
        "warranty":"12",
        "delivery_town_time":1,
        "delivery_town_price":1,
        "delivery_country_time":1,
        "delivery_country_price":1,
        "isCashless":"нет",
        "isCredit":"нет"
    },
    {
        "id":"6",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":300,
        "currency":"BYR",
        "status":"нет",
        "comment":"Test3",
        "warranty":"12",
        "delivery_town_time":1,
        "delivery_town_price":1,
        "delivery_country_time":1,
        "delivery_country_price":1,
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```
