# [Удаление позиций товаров](info.md)

## DELETE /pricelists/{positionId}

Удаляет конкретную позицию товара для магазина.

- Ресурс **/pricelists/{positionId}**
- HTTP-метод **DELETE**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 202 Accepted - Задача на удаление успешно поставлена в очередь
```

```
HTTP/1.1 500  Internal Server Error - Ошибка постановки задачи в очередь
```

### Пример запроса

```
DELETE /pricelists/1
Accept: application/json
```

```
HTTP/1.1 202 Accepted
```

