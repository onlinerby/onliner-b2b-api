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
GET /sections/2/manufacturers/1/products/1
```

```json
{
    "id": 1,
    "sectionId": 2,
    "manufacturerId": 1,
    "productId": 1,
    "productTitle": "LG BD75",
    "price": 100,
    "isCashless": false,
    "status": "none",
    "description": "Comment",
    "warranty": 12,
    "delivery": "none"
}
```
