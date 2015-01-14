### Примеры формата прайс-листов

## JSON

```json
[{"category":"GPS-навигаторы","vendor":"ALGA","model":"AS 6005 BTHD","price":"1000000","currency":"BYR","comment":"Ваш комментарий","importer":"Рога и Копыта","serviceCenters":"ул. П. Бровки 5, ООО Сервис","warranty":"12","deliveryTownTime":1,"deliveryTownPrice":1,"deliveryCountryTime":1,"deliveryCountryPrice":1,"productLifeTime":1,"isCashless":"Да","isCredit":"Нет"}]
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
            <serviceCenters>Сервисные центры</serviceCenters>
            <warranty>12</warranty>
            <deliveryTownTime>1</deliveryTownTime>
            <deliveryTownPrice>1</deliveryTownPrice>
            <deliveryCountryTime>1</deliveryCountryTime>
            <deliveryCountryPrice>1</deliveryCountryPrice>
            <productLifeTime>1</productLifeTime>
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
