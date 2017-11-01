# Получение справочной информации (список артикулов по товару)

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/articles

Возвращает список артикулов по указанному товару

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/articles**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Пример 1. Список артикулов по указанному товару

```http
GET /sections/187/manufacturers/2340/products/736768/articles
Accept: application/json
```
```json
    [
        {"article": "910-002941"},
        {"article": "910-002944"},
        {"article": "910-003117"}
    ]
```

