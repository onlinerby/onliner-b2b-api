# Onliner B2B API

Адрес API – https://b2bapi.onliner.by
  
Ресурс доступен только по протоколу HTTPS.

- [Регистрация приложения](docs/aplication.md)
- [Получение доступа к API](docs/oauth20.md)

## Магазин

- [GET /shop](docs/shop/info.md)
    - Информация о текущем магазине
- [PUT /shop](docs/shop/edit.md)
    - Редактирование параметров магазина

## Получение справочной информации

- [GET /sections](docs/catalog/sections.md)
    - Возвращает полный список активных разделов каталога
- [GET /sections/{sectionId}](docs/catalog/section.md)
    - Возвращает параметры указанного раздела
- [GET /sections/{sectionId}/manufacturers](docs/catalog/manufacturers.md)
    - Возвращает список производителей в указанном разделе
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products](docs/catalog.products.md)
    - Возвращает список товаров указанного производителя
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions](docs/price-lists/positions.md)
    - Возвращает список позиций указанного товара    

## Подключение и отключение разделов каталога
- [POST /sections/{id}](docs/shop/section/add.md)
    - Подключает раздел к магазину
- [DELETE /sections/{id}](docs/shop/section/remove.md)
    - Отключает раздел от магазина

## Прайс-лист

### Импорт
[Общая информация по импорту прайс листов](docs/price-lists/import/info.md)

- [PATCH /pricelists](docs/price-lists/import/update.md)
    - Добавление и редактирование позиций
- [PUT /pricelists](docs/import/price-lists/import/replace.md)
    - Загрузка нового прайс-листа

### Отчет по импорту

- [GET /pricelists/{pricelistId}/status](docs/price-lists/import/status.md)
    - Возвращает статус обработки прайс-листа
- [GET /pricelists/{pricelistId}/report](docs/price-lists/report.md)
    - Возвращает список ошибок, возникших во время импорта
    
### Удаление позиции товара

[Общая информация по удалению позиций из прайс листов](docs/price-lists/delete/info.md)

- [DELETE /pricelists/all](docs/price-lists/delete/all.md)
    - Удаляет все позиции магацина
- [DELETE /pricelists/{positionId}](docs/price-lists/delete/one.md)
    - Удаляет конкретную позицию товара
- [DELETE /priceists](docs/price-lists/delete/list.md)
    - При наличии списка "list" удаляет позиции товаров, ID которых перечисланы в списке
    
### Обновление актуальности

- [PUT /pricelist/{id}/renew](docs/price-lists/renew.md)
    - Обновляет актуальность указанной или всех позиций магазина
- [PUT /pricelist/renew](docs/price-lists/renew-list.md)
    - Обновляет актуальность указанных позиций

### Экспорт прайс листов и позиций товаров

- [GET /positions](docs/price-lists/export/positions.md)
    - Возвращает полный список позиций магазина
- [GET /sections/{sectionId}/positions](docs/price-lists/export/sections.md)
    - Возвращает список позиций для указанного раздела
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/positions](docs/eprice-lists/export/manufacturers.md)
    - Возвращает список позиций для указанного производителя
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions](docs/price-lists/export/products.md)
    - Возвращает список позиций для указанного товара
