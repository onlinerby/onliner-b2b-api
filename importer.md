# Onliner B2B API для импортера

Адрес API – https://b2bapi.onliner.by
  
Ресурс доступен только по протоколу HTTPS.

Для всех запросов следует указывать HTTP заголовок **Accept**. По умолчанию его необходимо передавать со значением *application/json*. Некоторые ресурсы поддерживают другие форматы, о чем будет написано на соответствующих страницах документации.

- [Список изменений](importer-changelog.md)

В случае возникновения проблем либо технических вопросов по работе с API, создавайте Issue в данном репозитории.

Для регистрации в системе и получения доступа обращайтесь на catalog@onliner.by

- [POST /importers/token](docs/importers/auth.md)
    - Авторизация импортера
- [PUT /importers/retailers](docs/importers/retailers.md)
    - Обновить список ретейлеров
- [GET /importers/retailers/{retailerListId}/status](docs/importers/retailers_status.md)
    - Получение результата обновления списка ретейлеров
- [PUT|PATCH /importers/stocklists](docs/importers/stocks.md)
    - Обновить наличие товаров
- [GET /importers/stocklists/{stockListId}/status](docs/importers/status.md)
    - Получение результата импорта наличия товаров
