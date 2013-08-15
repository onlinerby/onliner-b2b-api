# Обновление актуальности

## PUT /pricelist/renew

Обновляет актуальность указанных позиций

- Ресурс **/pricelist/renew**
- HTTP-метод **PUT**
- Тип данных: **application/json, application/x-json**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 200 OK
```

```
HTTP/1.1 400 Bad Request
{
    "errors": {
        "Positions id list is required and must not be empty"
    }
}
```
Возвращается в случае, если список Id не получен

### Пример 1. Обновить актуальность указанных позиций (ID=1,2,3)

```
PUT /pricelist/renew
```

Request Body:
```json
[
    1,2,3
]
```

```
HTTP/1.1 200 OK
```
```json
[
    {"id":1, "dateUpdate":"2013-01-01 12:00:00"},
    {"id":2, "dateUpdate":"2013-01-01 12:00:00"},
    {"id":3, "dateUpdate":"2013-01-01 12:00:00"}
]
```

### Пример 2. Обновить актуальность позиций, часть из которых не существует

В этом случае ни одна позиция не обновляется

```
PUT /pricelist/renew
```
Request Body:
```json
[
    1,2,99
]
```
```
HTTP/1.1 400 Bad Request
```
```json
{
    "errors": {99: "Not found"}
}
```
