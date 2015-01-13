### Примеры формата прайс-листов

## JSON

```json
[{"category":"GPS-навигаторы","vendor":"ALGA","model":"AS 6005 BTHD","price":"1000000","currency":"BYR","comment":"Ваш комментарий","importer":"Рога и Копыта","service_centers":"ул. П. Бровки 5, ООО Сервис","warranty":"12","delivery_town_time":1,"delivery_town_price":1,"delivery_country_time":1,"delivery_country_price":1,"isCashless":"Да","isCredit":"Нет"}]
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
            <category>GPS-навигаторы</category>
            <vendor>ALGA</vendor>
            <model>AS 6005 BTHD</model>
            <price>1000000</price>
            <currency>BYR</currency>
            <comment>Ваш комментарий</comment>
            <producer>Изготовитель</producer>
            <importer>Импортер</importer>
            <service_centers>Сервисные центры</service_centers>
            <warranty>12</warranty>
            <delivery_town_time>1</delivery_town_time>
            <delivery_town_price>1</delivery_town_price>
            <delivery_country_time>1</delivery_country_time>
            <delivery_country_price>1</delivery_country_price>
            <isCashless>Да</isCashless>
            <isCredit>Нет</isCredit>
        </item>
    </items-list>
</price-list>
```

## CSV

```
Мобильные телефоны;Apple;iPhone 4S (16Gb);2450000;BYR;Склад;Цена действительна при безналичном расчете. Стоимость товара указана с НДС. Быстро выставляем счет. Быстрая отгрузка товара. Полный пакет документов. Дополнительные скидки для постоянных партнеров.Накопительная дисконтная карта RedCard. Оперативная доставка по всей Беларуси, по Минску - в течение 1-2 часов. Квалифицированная консультация. Установка программ и техническая поддержка в течение всего ;0;;Бесплатная;Да;Нет
...
```

### Допустимые значения полей
```
status - нет, склад, заказ, спец, предзаказ (только для игр)
currency - USD, EUR, BYR
```
