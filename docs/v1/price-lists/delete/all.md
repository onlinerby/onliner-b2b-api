# [Удаление позиций товаров](info.md)

## DELETE /pricelists/all

Удаляет все позиции товаров для магазина.

- Ресурс **/pricelists/all**
- HTTP-метод **DELETE**

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
DELETE /pricelists/all
Accept: application/json
```

```
HTTP/1.1 202 Accepted
```
