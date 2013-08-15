# Экспорт данных

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions

Возвращает список позиций для указанного товара

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions**
- HTTP-метод **GET**
- Формат ответа **CSV|JSON|XML**

### Параметры

*нет параметров*

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

- CSV
    - Accept: text/csv
- JSON
    - Accept: application/json
- XML
    - Accept: application/xml

### Пример. Список позиций для указанного товара

```
GET /sections/2/manufacturers/851/products/53808/positions
Accept: application/json
```

```json
[
    {
        "id": "1",
        "shop_id": "1",
        "section_id": "2",
        "manufacturer_id": "851",
        "product_id": "53808",
        "price": "0",
        "currency": "USD",
        "is_credit": "0",
        "is_cashless": "0",
        "status": "none",
        "delivery": "paid",
        "warranty": "0",
        "comment": "",
        "date_update": "0000-00-00 00:00:00"
    }
]
```
