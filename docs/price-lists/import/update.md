# [Импорт прайс-листов](info.md)

## PATCH /pricelists

Производит обновление данных по позициям

 Если вы хотите добавить позиции товара, либо внести изменения в уже существующие,
 то присланные вами данные должны содержать все позиции данного товара,
 так как ___после получения запроса все позиции товара заменяются на новые!___

 Например, если вам нужно добавить третью позицию товара, то данные должны содержать также информацию по остальным двум позициям.


- Ресурс **/pricelists**
- HTTP-метод **PATCH**
- Тип данных **application/json, application/x-json, text/xml, application/xml, application/x-xml, text/csv**
- Формат ответа **JSON**

### Параметры

|Параметр|Тип|Описание|
|---|---|---|
|id|integer|Опциональный параметр, который определяет id предложения|
|price|float|Цена предложения|
|currency|string|Валюта предложения, влияет на price, deliveryTownPrice, deliveryCountryPrice, может быть только BYN|

Цена в BYN должна быть указана строкой с копейками через точку, например "20.16".

### Пример запроса

```
PATCH /pricelists
Accept: application/json
Content-Type: application/json

[
    {
        "id":"1",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":"20.16",
        "currency":"BYN",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryTownPrice":"1.00",
        "deliveryCountryTime":5,
        "deliveryCountryPrice":"2.00",
        "productLifeTime":36,
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```
### Пример запроса с использованием библиотеки curl
```
curl https://b2bapi.onliner.by/pricelists \
-d '[
        {
            "category":"MP3-плееры",
            "vendor":"Apple",
            "model":"iPod nano 16Gb (7th generation)",
            "price":"20.16",
            "currency":"BYN",
            "comment":"Ваш комментарий",
            "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
            "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
            "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
            "warranty":"12",
            "deliveryTownTime":1,
            "deliveryTownPrice":"1.00",
            "deliveryCountryTime":5,
            "deliveryCountryPrice":"2.00",
            "productLifeTime":36,
            "isCashless":"нет",
            "isCredit":"нет"
        }
    ]' \
-H 'Accept: application/json' -H 'Content-Type: application/json' -H 'Authorization: Bearer RECEIVED_TOKEN_STRING' -X PATCH
```
### Пример запроса на языке php
```php
$data = '[
             {
                 "category":"MP3-плееры",
                 "vendor":"Apple",
                 "model":"iPod nano 16Gb (7th generation)",
                 "price":"20.16",
                 "currency":"BYN",
                 "comment":"Ваш комментарий",
                 "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
                 "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
                 "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
                 "warranty":"12",
                 "deliveryTownTime":1,
                 "deliveryTownPrice":"1.00",
                 "deliveryCountryTime":5,
                 "deliveryCountryPrice":"2.00",
                 "productLifeTime":36,
                 "isCashless":"нет",
                 "isCredit":"нет"
             }
         ]';
$process = curl_init("https://b2bapi.onliner.by/pricelists");
curl_setopt(
	$process, 
	CURLOPT_HTTPHEADER, 
	array(
		'Accept: application/json', 
		'Content-Type: application/json', 
		'Authorization: Bearer RECEIVED_TOKEN_STRING'
	)
);
curl_setopt($process, CURLOPT_CUSTOMREQUEST, 'PATCH');
curl_setopt($process, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($process, CURLOPT_POSTFIELDS, $data);
$result = curl_exec($process);
curl_close($process);
```

```json
HTTP/1.1 202 Accepted
{"id":"51b84cd3ddecce0804000001","shopId":1,"fileName":"price-list2013-06-12.json","size":1036,"date":"2013-06-12 13:26:27","status":"STATUS_WAITING","contentType":"json","statusMessage":null}
```
