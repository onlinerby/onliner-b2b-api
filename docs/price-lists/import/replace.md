# [Импорт прайс-листов](info.md)

## PUT /pricelists

Загружает новый прайс-лист с заменой всех данных.

- Ресурс **/pricelists**
- HTTP-метод **PUT**
- Тип данных **application/json, application/x-json, text/xml, application/xml, application/x-xml, text/csv**
- Формат ответа **JSON**

### Параметры

|Параметр|Тип|Описание|
|---|---|---|
|id|string|Опциональный параметр, который определяет id предложения. Можно использовать внутренний ID вашего магазина. ID должен быть уникален в рамках магазина. Можно использовать строку до 50 символов с цифрами и строчными буквами латинского алфавита|
|price|string|Цена предложения|
|currency|string|Валюта предложения, влияет на price может быть только BYN|
|article|string|Полe article - опциональное. Если оно указано, будет производиться поиск товара по названию производителя и артикулу (тогда можно не указывать категорию и название товара). Если нет - по старой схеме: по категории, производителю и названию|овара|
|stockStatus|string|Опциональный параметр. Наличие: in_stock (есть на складе и доступен для покупки), run_out_of_stock (осталось мало или заканчивается) __*__|
|termHalva|int|Срок рассрочки по Халве в месяцах (1-99). Обязательный, если указано `priceHalva`|
|priceHalva|string|Опциональный параметр. Цена в BYN по Халве. Указывается если Цена позиции по Халве отличается от основной цены. Если значение не указано, то будет использована поле `price`|
|hasOnlinerPrime|string|Опциональный параметр. Участвует ли предложение в Onliner Prime. Возможные значения: да, нет|
|courierDeliveryPrices|object|Список регионов, стоимость доставки в которые должна быть взята из прайс-листа, а не рассчитываться по тарифной сетке|

В формате CSV колонки article и id должны быть указаны всегда, но могут содержать пустое значение.

__*__ - Отображение наличия на складе для пользователей заработает только после подключения функционала "На складе". Как включить опцию, [смотрите здесь](https://b2bwiki.onliner.by/wiki/%D0%97%D0%B0%D0%B3%D0%BB%D0%B0%D0%B2%D0%BD%D0%B0%D1%8F_%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0#.D0.9D.D0.B0.D0.BB.D0.B8.D1.87.D0.B8.D0.B5_.D1.82.D0.BE.D0.B2.D0.B0.D1.80.D0.B0_.28.D0.B7.D0.BD.D0.B0.D1.87.D0.BA.D0.B8_.C2.AB.D0.9D.D0.B0_.D1.81.D0.BA.D0.BB.D0.B0.D0.B4.D0.B5.C2.BB.29)

Цена в BYN должна быть указана строкой с копейками через точку, например "20.16".

### Пример запроса

```http
PUT /pricelists
Accept: application/json
Content-Type: application/json
```
```json
[
    {
        "id": "position1",
        "category": "MP3-плееры",
        "vendor": "Apple",
        "model": "iPod nano 16Gb (7th generation)",
        "article": "ipod16gb",
        "price": "20.16",
        "currency": "BYN",
        "comment": "Ваш комментарий",
        "producer": "Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer": "ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters": "ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty": "12",
        "deliveryTownTime": 1,
        "deliveryCountryTime": 5,
        "productLifeTime": 36,
        "isCashless": "нет",
        "isCredit": "нет",
        "stockStatus": "in_stock",
        "termHalva": 3,
        "priceHalva": "20.16",
        "hasOnlinerPrime": "нет",
        "courierDeliveryPrices": {
            "region-1": {
                "type": "custom",
                "amount": "2.99"
            }
        }
    }
]
```

### Пример запроса на языке php

```php
$data = '[
             {
                 "category":"MP3-плееры",
                 "vendor":"Apple",
                 "model":"iPod nano 16Gb (7th generation)",
                 "article":"ipod16gb",
                 "price":"20.16",
                 "currency":"BYN",
                 "comment":"Ваш комментарий",
                 "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
                 "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
                 "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
                 "warranty":"12",
                 "deliveryTownTime":1,
                 "deliveryCountryTime":5,
                 "productLifeTime":36,
                 "isCashless":"нет",
                 "isCredit":"нет",
                 "stockStatus": "in_stock",
                 "termHalva":3,
                 "priceHalva":"20.16",
                 "hasOnlinerPrime":"нет",
                 "courierDeliveryPrices": {
                     "region-1": {
                         "type": "custom",
                         "amount": "2.99"
                     }
                 }
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

curl_setopt($process, CURLOPT_CUSTOMREQUEST, 'PUT');
curl_setopt($process, CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($process, CURLOPT_POSTFIELDS, $data);
$result = curl_exec($process);
curl_close($process);
```

### Пример ответа

```http
HTTP/1.1 202 Accepted
Content-Type: application/json
```
```json
{
    "id": "51b84cd3ddecce0804000001",
    "shopId": 1,
    "fileName": "price-list2013-06-12.json",
    "size": 1036,
    "date": "2013-06-12 13:26:27",
    "status": "STATUS_WAITING",
    "contentType": "json",
    "statusMessage": null
}
```
