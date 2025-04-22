### Примеры формата прайс-листов

## JSON

```json
[
    {
        "productId":1,
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "article": "ipod_article",
        "id": 1,
        "price":"20.16",
        "currency":"BYN",
        "comment":"Ваш комментарий",
        "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
        "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
        "warranty":"12",
        "deliveryTownTime":1,
        "deliveryCountryTime":5,
        "isCashless":"нет",
        "stockStatus": "in_stock",
        "termHalva": 3,
        "hasOnlinerPrime": "да",
        "pricePromo": "18.00",
        "increasedMinipayInstallment": "нет",
        "creditForNationalGoods": "нет",
        "courierDeliveryPrices": {
            "region-1": {
                "type": "custom",
                "amount": "2.99"
            },
            "region-2": {
                "type": "no"
            },
            "region-3": {
                "type": "free"
            },
            "region-4": {
                "type": "default"
            }
        }
    }
]
```

## XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<price-list version="1.0">
    <settings>
        <currency>BYN</currency>
    </settings>
    <items-list>
        <item>
            <productId>2</productId>
            <category>MP3-плееры</category>
            <vendor>Apple</vendor>
            <model>iPod nano 16Gb (7th generation)</model>
            <article>ipod_article</article>
            <id>1</id>
            <price>20.16</price>
            <currency>BYN</currency>
            <comment>Ваш комментарий</comment>
            <producer>Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China</producer>
            <importer>ООО Музтрейд, г.Минск, ул. Кропоткина, 12&#13;ООО Плеерсервис, г.Гомель, ул. Платонова, 16</importer>
            <serviceCenters>ООО Музсервис, г.Минск, ул. П. Бровки, 5&#13;ООО Плеерсервис, г.Гомель, ул. Платонова, 16</serviceCenters>
            <warranty>12</warranty>
            <deliveryTownTime>1</deliveryTownTime>
            <deliveryCountryTime>5</deliveryCountryTime>
            <isCashless>нет</isCashless>
            <stockStatus>in_stock</stockStatus>
            <termHalva>3</termHalva>
            <hasOnlinerPrime>да</hasOnlinerPrime>
            <pricePromo>18.00</pricePromo>
            <increasedMinipayInstallment>нет</increasedMinipayInstallment>
            <creditForNationalGoods>нет</creditForNationalGoods>
            <courierDeliveryPrices>
                <item>
                    <region>region-1</region>
                    <type>custom</type>
                    <amount>2.99</amount>
                </item>
                <item>
                    <region>region-2</region>
                    <type>no</type>
                </item>
                <item>
                    <region>region-3</region>
                    <type>free</type>
                </item>
                <item>
                    <region>region-4</region>
                    <type>default</type>
                </item>
            </courierDeliveryPrices>
        </item>
    </items-list>
</price-list>
```

## CSV с названием колонок

  * Названия колонок должны находиться в первой строке
  * В прайс-листе можно менять порядок колонок
  * Не допускается добавление пустых колонок в начало и средину таблицы
  * Названия колонок:
    * Onliner ID
    * Раздел
    * Производитель
    * Товар
    * Артикул
    * id-предложения
    * Цена
    * Валюта
    * Описание предложения
    * Изготовитель
    * Импортер
    * Сервисный центр
    * Гарантия
    * Срок доставки по Минску
    * Срок доставки по РБ
    * Срок службы
    * Только для юр. лиц
    * Наличие на складе
    * Срок рассрочки по Халве
    * Onliner Prime
    * Цена по промокоду
    * Повышенная рассрочка Minipay
    * Кредит на «Родныя тавары»
    * Курьерская доставка в _НАЗВАНИЕ_РЕГИОНА_ИЗ_ТАРИФНОЙ_СЕТКИ_

Описание значения полей для курьерской доставки доступно в [разделе описания стоимости курьерской доставки](import/courier_delivery.md).
Описание значения полей для рассрочки "Халва" доступно в [разделе описания рассрочки Халва](import/halva.md).
```
Onliner ID;Раздел;Производитель;Товар;Артикул;"id-предложения";Цена;Валюта;"Описание предложения";Изготовитель;Импортер;"Сервисный центр";Гарантия;"Срок доставки по Минску";"Срок доставки по РБ";"Срок службы";"Только для юр. лиц";"Наличие на складе";"Курьерская доставка в Регион 1";"Курьерская доставка в Регион 2";"Курьерская доставка в Регион 3";"Курьерская доставка в Регион 4";"Срок рассрочки по Халве";"Onliner Prime";"Цена по промокоду";"Повышенная рассрочка Minipay";"Кредит на «Родныя тавары»"
1;MP3-плееры;Apple;iPod nano 16Gb (7th generation);ipod_article;1;20.16;BYN;Ваш комментарий;Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China;ООО Музтрейд, г.Минск, ул. Кропоткина, 12;"ООО Музсервис, г.Минск, ул. П. Бровки, 5\nООО Плеерсервис, г.Гомель, ул. Платонова, 16";12;1;5;36;нет;in_stock;2.99;Нет доставки;Бесплатная доставка;Общий тариф;3;да;18.00;нет;нет
```
