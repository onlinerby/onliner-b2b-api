# Экспорт данных

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions

Возвращает список позиций для указанного товара

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products/{productId}/positions**
- HTTP-метод **GET**
- Формат ответа **csv | json | xml**

### Параметры

- **currency** [optional] Валюта, в которой нужно вернуть цены
    - **BYR**
    - **USD**
    - **EUR**
    - **original**

Если параметр не передан, то цены позиций будут возвращены в долларах США.
В случае, если параметр равен 'original', то цены будут возвращены в той валюте, которая указана в списке позиций.
Если передана неправильная валюта, то будет возвращена ошибка.

### Запрос нужного формата данных

Чтобы получить нужный вам формат данных, добавьте в запрос заголовок Accept:

- CSV
    - Accept: text/csv
- JSON
    - Accept: application/json
- XML
    - Accept: application/xml

### Пример 1. Список позиций для указанного товара

```
GET /sections/2/manufacturers/851/products/53808/positions
Accept: application/json
```

```json
[
    {
        "id":"4",
        "category":"MP3-плееры",
        "vendor":"Apple",
        "model":"iPod nano 16Gb (7th generation)",
        "price":200,
        "currency":"USD",
        "status":"спец",
        "comment":"Test1",
        "warranty":"12",
        "delivery":"на следующий день",
        "isCashless":"нет",
        "isCredit":"нет"
    }
]
```

### Пример 2. Передана неправильная валюта для экспорта
```
GET /sections/240/manufacturers/12/products/34432/positions?currency=blah
Accept: application/json
```
```
HTTP/1.1 400 Bad Request

{
    "errors": {"Unknown currency code blah"}
}
```

### Пример 3. Параметр валюты задан, но его значение отсутствует
```
GET /sections/240/manufacturers/12/products/34432/positions?currency=
Accept: application/json
```
```
HTTP/1.1 400 Bad Request

{
    "errors": {"Field 'currency' cannot be empty"}
}
```
