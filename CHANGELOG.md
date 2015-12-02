
# CHANGELOG

## 02.12.2015

* Добавлен ID позиции во все методы, возвращающие информацию о позициях товаров
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/positions.md](docs/price-lists/positions.md)
 * [docs/price-lists/export/positions.md](docs/price-lists/export/positions.md)
 * [docs/price-lists/export/sections.md](docs/price-lists/export/sections.md)
 * [docs/price-lists/export/manufacturers.md](docs/price-lists/export/manufacturers.md)
 * [docs/price-lists/export/products.md](docs/price-lists/export/products.md)
* При импорте прайс-листа можно (опционально) указывать id предложения
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/import/update.md](docs/price-lists/import/update.md)
 * [docs/price-lists/import/replace.md](docs/price-lists/import/replace.md)

## 14.01.2015

* Удален параметр currency для экспорта позиций товара
 * Больше нельзя указывать, в какой валюте возвращать цены при экспорте
 * Цены теперь возвращаются только в белорусских рублях (BYR)
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/export/products.md](docs/price-lists/export/products.md)
 * [docs/price-lists/export/positions.md](docs/price-lists/export/positions.md)
 * [docs/price-lists/export/manufacturers.md](docs/price-lists/export/manufacturers.md)
 * [docs/price-lists/export/sections.md](docs/price-lists/export/sections.md)

* Изменились требования к полю currency при изменении позиций товара
 * Поле стало обязательным для заполнения
 * Цена может быть указана только в белорусских рублях (BYR)
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/formats.md](docs/price-lists/formats.md)
 * [docs/price-lists/import/replace.md](docs/price-lists/import/replace.md)
 * [docs/price-lists/import/report.md](docs/price-lists/import/report.md)
 * [docs/price-lists/import/update.md](docs/price-lists/import/update.md)
 * [docs/price-lists/positions.md](docs/price-lists/positions.md)

* Появились новые поля для позиции товара
 * producer - изготовитель товара, обязательное поле, строка до 500 символов
 * importer - импортер товара, обязательное поле, если импортера нет - указывается то же, что и в поле изготовитель, строка до 500 символов
 * serviceCenters - сервисные центры, обязательное поле, если несколько - через символ перевода строки, строка до 1500 символов
 * deliveryTownTime - срок доставки по городу в днях, обязательное, если указана стоимость доставки по городу
 * deliveryTownPrice - стоимость доставки по городу в белорусских рублях, 0 - бесплатная доставка
 * deliveryCountryTime - срок доставки по стране в днях, обязательное, если указана стоимость доставки по стране
 * deliveryCountryPrice - стоимость доставки по стране в белорусских рублях, 0 - бесплатная доставка
 * productLifeTime - срок службы (годности) товара в месяцах, 0 - неограничен
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/formats.md](docs/price-lists/formats.md)
 * [docs/price-lists/import/replace.md](docs/price-lists/import/replace.md)
 * [docs/price-lists/import/report.md](docs/price-lists/import/report.md)
 * [docs/price-lists/import/update.md](docs/price-lists/import/update.md)
 * [docs/price-lists/positions.md](docs/price-lists/positions.md)

* Удалены следующие поля для позиции товара
 * status
 * delivery
 * Изменения затрагивают следующие методы:
 * [docs/price-lists/formats.md](docs/price-lists/formats.md)
 * [docs/price-lists/import/replace.md](docs/price-lists/import/replace.md)
 * [docs/price-lists/import/report.md](docs/price-lists/import/report.md)
 * [docs/price-lists/import/update.md](docs/price-lists/import/update.md)
 * [docs/price-lists/positions.md](docs/price-lists/positions.md)

* Удален метод обновления курсов валют магазина

* Удалено поле currencyRates из свойств магазина
 * Изменения затрагивают следующие методы:
 * [docs/shop/info.md](docs/shop/info.md)
