# Получение справочной информации

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions

Возвращает список позиций указанного товара

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример. Список позиций указанного товара

```
GET /sections/2/manufacturers/1/products/1/positions
```

```json
[
    {
        "id": 1,
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":200000,
        "currency":"BYR",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
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
