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
Data: [{"category":"GPS-навигаторы","vendor":"ALGA","model":"AS 6005 BTHD","price":"1000000","currency":"BYR","comment":"Ваш комментарий","warranty":"12","delivery_town_time":1,"delivery_town_price":1,"delivery_country_time":1,"delivery_country_price":1,"isCashless":"Да","isCredit":"Нет"}]
```
### Пример запроса на языке php
```php
$data = '[{"category":"AV-ресиверы и усилители","vendor":"Anthem","model":"A2","price":"10000","currency":"BYR","comment":"Ваш комментарий","producer":"Apple","importer":"Рога и Копыта","service_centers":"ул. П. Бровки 5, ООО Сервис","warranty":"12","delivery_town_time":1,"delivery_town_price":1,"delivery_country_time":1,"delivery_country_price":1,"isCashless":"Да","isCredit":"Нет"}]';
$process = curl_init("https://b2bapi.onliner.by/pricelists");
curl_setopt(
	$process, 
	CURLOPT_HTTPHEADER, 
	array(
		'Accept: application/json', 
		'Content-Type: application/json', 
		'Authorization: Bearer RECIVED_TOKEN_STRING'
	)
);
curl_setopt($process, CURLOPT_CUSTOMREQUEST, 'PUT');
curl_setopt($process, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($process, CURLOPT_POSTFIELDS, $data);
$result = curl_exec($process);
curl_close($process);
```

```json
HTTP/1.1 202 Accepted
{"id":"51b84cd3ddecce0804000001","shopId":1,"fileName":"price-list2013-06-12.json","size":1036,"date":"2013-06-12 13:26:27","status":"STATUS_WAITING","contentType":"json","statusMessage":null}
```
