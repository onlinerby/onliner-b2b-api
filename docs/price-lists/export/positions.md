# Экспорт данных

## GET /positions

Возвращает полный список позиций магазина

- Ресурс **/positions**
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
        "currency":"BYR",
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
        "currency":"BYR",
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
