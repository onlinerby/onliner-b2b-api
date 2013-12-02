# Onliner B2B API

Адрес API – https://b2bapi.onliner.by

Ресурс доступен только по протоколу HTTPS.

- [Регистрация приложения](docs/application.md)
- [Получение доступа к API](docs/oauth20.md)

## Версионирование

- [Работа с версиями API](docs/versioning.md)

Текущая версия: `v2`

Поддерживаются версии `v1` и `v2`

## Магазин

- [GET /shop](docs/v1/shop/info.md)
    - Информация о текущем магазине
- [PUT /shop](docs/v1/shop/edit.md)
    - Редактирование параметров магазина

## Получение справочной информации

- [GET /sections](docs/v1/catalog/sections.md)
    - Возвращает полный список активных разделов каталога
- [GET /sections/{sectionId}](docs/v1/catalog/section.md)
    - Возвращает параметры указанного раздела
- [GET /sections/{sectionId}/manufacturers](docs/v1/catalog/manufacturers.md)
    - Возвращает список производителей в указанном разделе
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products](docs/v1/catalog/products.md)
    - Возвращает список товаров указанного производителя
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions](docs/v1/price-lists/positions.md)
    - Возвращает список позиций указанного товара    

## Подключение и отключение разделов каталога
- [POST /sections/{id}](docs/v1/shop/section/add.md)
    - Подключает раздел к магазину
- [DELETE /sections/{id}](docs/v1/shop/section/remove.md)
    - Отключает раздел от магазина

## Прайс-лист

### Импорт
[Общая информация по импорту прайс листов](docs/v1/price-lists/import/info.md)

- [PATCH /pricelists](docs/v1/price-lists/import/update.md)
    - Добавление и редактирование позиций
- [PUT /pricelists](docs/v1/price-lists/import/replace.md)
    - Загрузка нового прайс-листа

### Отчет по импорту

- [GET /pricelists/{pricelistId}/status](docs/v1/price-lists/import/status.md)
    - Возвращает статус обработки прайс-листа
- [GET /pricelists/{pricelistId}/report](docs/v1/price-lists/import/report.md)
    - Возвращает список ошибок, возникших во время импорта
    
### Удаление позиции товара

[Общая информация по удалению позиций из прайс листов](docs/v1/price-lists/delete/info.md)

- [DELETE /pricelists/all](docs/v1/price-lists/delete/all.md)
    - Удаляет все позиции магацина
- [DELETE /pricelists/{positionId}](docs/v1/price-lists/delete/one.md)
    - Удаляет конкретную позицию товара
- [DELETE /priceists](docs/v1/price-lists/delete/list.md)
    - При наличии списка удаляет позиции товаров, ID которых перечисланы в списке
    
### Обновление актуальности

- [PUT /pricelist/{id}/renew](docs/v1/price-lists/renew.md)
    - Обновляет актуальность указанной или всех позиций магазина
- [PUT /pricelist/renew](docs/v1/price-lists/renew-list.md)
    - Обновляет актуальность указанных позиций

### Экспорт прайс листов и позиций товаров

- [GET /positions](docs/v1/price-lists/export/positions.md)
    - Возвращает полный список позиций магазина
- [GET /sections/{sectionId}/positions](docs/v1/price-lists/export/sections.md)
    - Возвращает список позиций для указанного раздела
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/positions](docs/v1/price-lists/export/manufacturers.md)
    - Возвращает список позиций для указанного производителя
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions](docs/v1/price-lists/export/products.md)
    - Возвращает список позиций для указанного товара