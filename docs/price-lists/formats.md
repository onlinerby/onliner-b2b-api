### Примеры формата прайс-листов

## JSON

```json
[
    {
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":20.16,
        "currency":"BYN",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryTownPrice":10000,
        "deliveryCountryTime":5,
        "deliveryCountryPrice":20000,
        "productLifeTime":36,
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

## XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<price-list version="1.0">
    <settings>
        <currency>BYR</currency>
    </settings>
    <items-list>
        <item>
            <category>MP3-плееры</category>
            <vendor>Apple</vendor>
            <model>iPod nano 16Gb (7th generation)</model>
            <price>20.16</price>
            <currency>BYN</currency>
            <comment>Ваш комментарий</comment>
            <producer>Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China</producer>
            <importer>ООО Музтрейд, г.Минск, ул. Кропоткина, 12&#13;ООО Плеерсервис, г.Гомель, ул. Платонова, 16</importer>
            <serviceCenters>ООО Музсервис, г.Минск, ул. П. Бровки, 5&#13;ООО Плеерсервис, г.Гомель, ул. Платонова, 16</serviceCenters>
            <warranty>12</warranty>
            <deliveryTownTime>1</deliveryTownTime>
            <deliveryTownPrice>10000</deliveryTownPrice>
            <deliveryCountryTime>5</deliveryCountryTime>
            <deliveryCountryPrice>20000</deliveryCountryPrice>
            <productLifeTime>36</productLifeTime>
            <isCashless>нет</isCashless>
            <isCredit>нет</isCredit>
        </item>
    </items-list>
</price-list>
```

## CSV

```
MP3-плееры;Apple;iPod nano 16Gb (7th generation);20.16;BYN;Ваш комментарий;Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China;ООО Музтрейд, г.Минск, ул. Кропоткина, 12;"ООО Музсервис, г.Минск, ул. П. Бровки, 5\nООО Плеерсервис, г.Гомель, ул. Платонова, 16";12;1;10000;5;20000;36;нет;нет
```
