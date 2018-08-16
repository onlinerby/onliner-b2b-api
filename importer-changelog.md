
# CHANGELOG

## 16.08.2018

* Добавлен УНП для магазина в отчет по сопоставленным товарам импортера
 * [GET /importers/match-reports/{id}](docs/importers/match_report_get.md)

## 18.04.2018

* Добавлены методы для получения отчета по сопоставленным товарам импортера
 * [POST /importers/match-reports/requests](docs/importers/match_report_request.md)
 * [GET /importers/match-reports/{id}](docs/importers/match_report_get.md)

## 11.04.2018

* Обновление списка ретейлеров теперь будет происходить асинхронно
 * Добавлен новый метод, вызвав который можно будет узнать статус обработки
 * Формат списка ретейлеров сохранен неизменным для совместимости
 * Изменения затрагивают следующие методы:
  * [docs/importers/retailers.md](docs/importers/retailers.md)
  * [docs/importers/retailers_status.md](docs/importers/retailers_status.md)
