# Экспорт данных

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/positions

Возвращает список позиций для указанного производителя

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/positions**
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

### Пример 1. Список позиций для указанного производителя

```
GET /sections/2/manufacturers/851/positions
Accept: application/json
```

```json
[
    {
        "id": 1,
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":"20.00",
        "currency":"BYN",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5
            ООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryTownPrice":"1.00",
        "deliveryCountryTime":5,
        "deliveryCountryPrice":"2.00",
        "productLifeTime":36,
        "isCashless":"нет",
        "isCredit":"нет",
        "stockStatus": "in_stock"
    }
]
```
