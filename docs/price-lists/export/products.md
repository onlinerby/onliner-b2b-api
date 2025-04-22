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

```http
GET /sections/2/manufacturers/851/products/53808/positions
Accept: application/json
```

```json
[
    {
        "id": 1,
        "productId": 53808,
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":"20.00",
        "currency":"BYN",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryCountryTime":5,
        "isCashless":"нет",
        "stockStatus": "in_stock",
        "termHalva": "0",
        "hasOnlinerPrime": "да",
        "pricePromo": "18.00",
        "increasedMinipayInstallment": "нет",
        "creditForNationalGoods": "нет",
        "courierDeliveryPrices": {
            "region-1": {
                "type": "custom",
                "amount": "2.99"
            },
            "region-2": {
                "type": "no"
            }
        }        
    }
]
```
