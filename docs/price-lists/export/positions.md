# Экспорт данных

## GET /positions

Возвращает полный список позиций магазина

- Ресурс **/positions**
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

### Пример. Список позиций магазина

```
GET /positions
Accept: application/json
```

```json
[
    {
        "id": "4",
        "shop_id": "1",
        "section_id": "2",
        "manufacturer_id": "2181",
        "product_id": "126528",
        "price": "0",
        "currency": "USD",
        "is_credit": "0",
        "is_cashless": "0",
        "status": "none",
        "delivery": "paid",
        "warranty": "0",
        "comment": "",
        "date_update": "0000-00-00 00:00:00"
    },
    {
        "id": "5",
        "shop_id": "1",
        "section_id": "2",
        "manufacturer_id": "2181",
        "product_id": "126531",
        "price": "0",
        "currency": "USD",
        "is_credit": "0",
        "is_cashless": "0",
        "status": "none",
        "delivery": "paid",
        "warranty": "0",
        "comment": "",
        "date_update": "0000-00-00 00:00:00"
    },
    {
        "id": "6",
        "shop_id": "1",
        "section_id": "2",
        "manufacturer_id": "2181",
        "product_id": "126538",
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
