# Подключение/отключение разделов каталога

## POST /sections/{id}

Подключает раздел к магазину

- Ресурс **/sections/{id}**
- HTTP-метод **POST**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 201 Created - Раздел успешно подключен
Response Data: {Данные по подключенному разделу}
```

```
HTTP/1.1 400 Bad Request - Магазин заблокирован
```
```json
{
   "errors":{
      "Not acceptable action for blocked shop"
   }
}
```

```
HTTP/1.1 400 Bad Request - Попытка подключить уже подключенный раздел
```
```json
{
   "id":{
      id
   },
   "errors":{
      "Section is already added"
   }
}
```

```
HTTP/1.1 404 Not Found - Раздел каталога с указанным id не найден
```
```json
{
   "id":{
      id
   },
   "errors":{
      "Catalog section not found"
   }
}
```

### Пример. Подключение раздела 3G-модемы

```
POST /sections/1
```

```
HTTP/1.1 201 Created
```

```json
{
    "id": 98496,
    "shopId": 9584,
    "section": {
        "id": 1,
        "title": "3G-модемы",
        "products_count": 0,
        "positions_limit": 0,
        "positions_limit_coefficient": 5,
        "product_service": 1,
        "status": 1,
        "show_contacts": 1,
        "rev_share_percent": 2,
        "rev_share_max_value": 5
    },
    "discount": 0,
    "discountExpiration": null
}
```
