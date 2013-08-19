# [Импорт прайс-листов](info.md)

## PUT /pricelists

Загружает новый прайс-лист с заменой всех данных.

- Ресурс **/pricelists**
- HTTP-метод **PUT**
- Тип данных **application/json, application/x-json, text/xml, application/xml, application/x-xml, text/csv**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример запроса

```
PUT /pricelists
Accept: application/json
Content-Type: application/json
Data: [{"category":"GPS-навигаторы","vendor":"ALGA","model":"AS 6005 BTHD","price":"1000000","currency":"BYR","status":"Склад","comment":"Ваш комментарий","warranty":"12","delivery":"На сегодня","isCashless":"Да","isCredit":"Нет"}]
```

```json
HTTP/1.1 202 Accepted
{"id":"51b84cd3ddecce0804000001","shopId":1,"fileName":"price-list2013-06-12.json","size":1036,"date":"2013-06-12 13:26:27","status":"STATUS_WAITING","contentType":"json","statusMessage":null}
```
