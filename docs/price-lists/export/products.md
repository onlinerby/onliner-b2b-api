# Экспорт данных

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions

Возвращает список позиций для указанного товара

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions**
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

### Пример 1. Список позиций для указанного товара

```
GET /sections/2/manufacturers/851/products/53808/positions
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
        "comment":"Test1",
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
