# [Удаление позиций товаров](../Delete.md)

## DELETE DELETE /pricelists

Удаляет позиции товаров по списку id товара для магазина.
Данные отправляются в виде json-массива

- Ресурс **/pricelists**
- Тип данных: **application/json, application/x-json**
- HTTP-метод **DELETE**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 202 Accepted - Задача на удаление успешно поставлена в очередь
```

```
HTTP/1.1 400 Bad Request
{"errors":"Delete subject are not specified"}
```

```
HTTP/1.1 500  Internal Server Error - Ошибка постановки задачи в очередь
```

### Пример запроса

```
DELETE /pricelists
Accept: application/json
```
Request Body:
```json
[
  1,2,3
]
```
```
HTTP/1.1 202 Accepted
```
