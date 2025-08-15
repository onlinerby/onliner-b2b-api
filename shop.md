# Onliner B2B API для магазина

Адрес API – https://b2bapi.onliner.by
  
Ресурс доступен только по протоколу HTTPS.

Для всех запросов следует указывать HTTP заголовок **Accept**. По умолчанию его необходимо передавать со значением *application/json*. Некоторые ресурсы поддерживают другие форматы, о чем будет написано на соответствующих страницах документации.

- [Список изменений](shop-changelog.md)
- [Регистрация приложения](docs/application.md)
- [Получение доступа к API](docs/oauth20.md)

## В случае возникновения проблем либо технических вопросов по работе с API, создавайте Issue в данном репозитории.

## Магазин

- [GET /shop](docs/shop/info.md)
    - Информация о текущем магазине

## Получение справочной информации

- [GET /sections](docs/catalog/sections.md)
    - Возвращает полный список активных разделов каталога
- [GET /sections/{sectionId}](docs/catalog/section.md)
    - Возвращает параметры указанного раздела
- [GET /sections/{sectionId}/manufacturers](docs/catalog/manufacturers.md)
    - Возвращает список производителей в указанном разделе
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products](docs/catalog/products.md)
    - Возвращает список товаров указанного производителя
- [GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/articles](docs/catalog/articles.md)
    - Возвращает список артикулов для указанного товара

## Подключение и отключение разделов каталога
- [POST /sections/{id}](docs/shop/section/add.md)
    - Подключает раздел к магазину
- [DELETE /sections/{id}](docs/shop/section/remove.md)
    - Отключает раздел от магазина

## Управление позициями товаров

### Импорт/экспорт прайслистов

[Документация](https://docs.onliner.by/b2b)

### Удаление позиций

[Общая информация по удалению позиций из прайс-листов](docs/price-lists/delete/info.md)

Удалять позиции перед импортом нет необходимости, так как старые позиции и так удаляются перед добавлением новых.

- [DELETE /pricelists/all](docs/price-lists/delete/all.md)
  - Удаляет все позиции магазина
- [DELETE /pricelists/{positionId}](docs/price-lists/delete/one.md)
  - Удаляет конкретную позицию товара
- [DELETE /pricelists](docs/price-lists/delete/list.md)
  - При наличии списка удаляет позиции товаров, ID которых перечислены в списке

### Обновление актуальности

Обновлять актуальность сразу же после импорта нет необходимости, так как после импорта все обновленные позиции и так актуальны.

- [PUT /pricelist/{id}/renew](docs/price-lists/renew.md)
  - Обновляет актуальность указанной или всех позиций магазина
- [PUT /pricelist/renew](docs/price-lists/renew-list.md)
  - Обновляет актуальность указанных позиций
