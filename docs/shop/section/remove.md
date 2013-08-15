# Подключение/отключение разделов каталога

## DELETE /sections/{id}

Отключает раздел от магазина

- Ресурс **/sections/{id}**
- HTTP-метод **DELETE**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Варианты ответа

```
HTTP/1.1 204 OK - Раздел успешно отключен
```

```
HTTP/1.1 400 Bad Request - Не достаточно средств на счете
```
```json
{"id":{id}, "errors": {"Not enough money on balance"}}
```

```
HTTP/1.1 400 Bad Request - Магазин заблокирован
```
```json
{"errors": {"Not acceptable action for blocked shop"}}
```

```
HTTP/1.1 404 Not Found - Раздел каталога с указанным id не подключен к магазину
```
```json
{"id":{id}, "errors": {"Catalog section not added to your shop"}}
```

### Пример. Отключение раздела 3G-модемы

```
DELETE /sections/1
```

```
HTTP/1.1 204 No Content
```