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
        "price":200000,
        "currency":"BYR",
        "comment":"Ваш комментарий",
        "producer":"Apple Inc. 1 Infinite Loop Cupertino, CA 95014",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12",
        "serviceCenters":"ООО Музсервис, ул. П. Бровки, 5
            ООО Плеерсервис, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryTownPrice":10000,
        "deliveryCountryTime":5,
        "deliveryCountryPrice":20000,
        "productLifeTime":36,
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```
