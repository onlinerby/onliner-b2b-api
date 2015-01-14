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
{
    "id": 1,
    "category":"MP3-плееры",
    "vendor":"Apple",
    "model":"iPod classic 160Gb",
    "price":50,
    "currency":"BYR",
    "comment":"Test",
    "producer":"Apple",
    "importer":"Рога и Копыта",
    "serviceCenters":"ул. П. Бровки 5, ООО Сервис",
    "warranty":"12",
    "deliveryTownTime":1,
    "deliveryTownPrice":1,
    "deliveryCountryTime":1,
    "deliveryCountryPrice":1,
    "productLifeTime":1,
    "isCashless":"да",
    "isCredit":"да"
}
```
