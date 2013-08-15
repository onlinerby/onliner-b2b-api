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
HTTP/1.1 400 Bad Request - Не достаточно средств на счете
```
```json
{
   "id":{
      id
   },
   "errors":{
      "Not enough money on balance"
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
   "id":4,
   "shopId":1,
   "section":{
      "id":1,
      "title":"Телевизоры",
      "price":1.3,
      "discount":10,
      "products_count":15,
      "priceWithDiscount":1.17
   },
   "discount":0,
   "discountExpiration":null,
   "status":1
}
```