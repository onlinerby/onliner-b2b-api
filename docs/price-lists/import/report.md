# Отчет по импорту

## GET /pricelists/{pricelistId}/report

Возвращает список ошибок, возникших во время импорта

- Ресурс **/pricelists/{pricelistId}/report**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Возможные ошибки валидации прайс-листа

- id ID позиции
    - VALUE_NOT_IN_GIVEN_FORMAT "ID позиции может содержать только цифры и строчные буквы латинского алфавита"
    - ERROR_POSITION_ID_NOT_UNIQUE "ID позиции уже используется, укажите уникальный ID"
    - ERROR_POSITION_ID_REQUIRED "Укажите ID позиции, может содержать только цифры и строчные буквы латинского алфавита"
- category Раздел каталога
    - ERROR_CATEGORY_NOT_FOUND "Неверно указан или не указан раздел"
- vendor Производитель
    - ERROR_VENDOR_NOT_FOUND "Неверно указан или не указан производитель товара"
    - ERROR_VENDOR_NOT_ALLOWED "Производитель не попадает под программу «Монобренд»"
- model Товар
    - ERROR_MODEL_NOT_FOUND "Неверно указана или не указана модель товара"
- article Артикул
    - WARNING_INVALID_ARTICLE "Неверно указан артикул" (это предупреждение, а не ошибка)
- price Цена
    - NOT_LESS_EQUAL_TO "превышает допустимое значение"
    - ERROR_INVALID_MONEY_FORMAT "Недопустимый формат цены"
- currency Валюта
    - ERROR_INVALID_CURRENCY "недопустимое значение"
    - NOT_IN_ARRAY "Неверное значение поля"
- isCashless, isCredit Только для юр. лиц, Кредит
    - ERROR_INVALID_FLAG "недопустимое значение поля"
- deliveryTownTime, deliveryTownPrice, deliveryCountryTime, deliveryCountryPrice
    - NOT_GREATER_THAN "недопустимое значение поля"
    - MUST_NOT_BE_BLANK "поле является обязательным"
    - ERROR_INVALID_MONEY_FORMAT "Недопустимый формат цены"
- productLifeTime
    - NOT_GREATER_THAN "недопустимое значение поля"
- warranty Гарантия
    - NOT_LESS_EQUAL_TO "превышает допустимое значение"
- stockStatus Наличие
    - ERROR_INVALID_STOCK_STATUS "недопустимое значение поля"
- общие ошибки
    - ERROR_POSITION_LIMIT_EXCEEDED "Превышено максимальное количество позиций данной модели товара"

### Пример 1. Получение отчета по несуществующему прайс-листу

```
GET /pricelists/51b056d8ee8a1efa1b000099/report
```

```
HTTP/1.1 404 Not Found
```

### Пример 2. Список ошибок импорта

```
GET /pricelists/51b056d8ee8a1efa1b000001/report
```

```json
[
    {
        "values": {
            "category":"MP3-плееры",
            "vendor":"Apple",
            "model":"iPod nano 16Gb (7th generation)",
            "article":"ipod16gb",
            "price":"2000.00",
            "currency":"BYN",
            "comment":"Ваш комментарий",
            "producer":"Foxconn,No.2,2nd Donghuan Road,10th Yousong Industrial District,Longhua,Baoan,Shenzhen City,Guangdong Province,China",
            "importer":"ООО Музтрейд, г.Минск, ул. Кропоткина, 12",
            "serviceCenters":"ООО Музсервис, г.Минск, ул. П. Бровки, 5\r\nООО Плеерсервис, г.Гомель, ул. Платонова, 16",
            "warranty":"12",
            "deliveryTownTime":-5,
            "deliveryTownPrice":"100.00",
            "deliveryCountryTime":5,
            "deliveryCountryPrice":"200.00",
            "productLifeTime":36,
            "isCashless":"xxx",
            "isCredit":"xxx"
        },
        "errors": {
            "isCredit": [
                {
                    "code": "ERROR_INVALID_FLAG",
                    "message": "недопустимое значение поля"
                }
            ],
            "isCashless": [
                {
                    "code": "ERROR_INVALID_FLAG",
                    "message": "недопустимое значение поля"
                }
            ],
            "deliveryTownTime": [
                {
                    "code": "NOT_GREATER_THAN",
                    "message": "недопустимое значение поля"
                }
            ]
        }
        "warnings": {
            "article": [
                {
                    "code": "WARNING_INVALID_ARTICLE",
                    "message": "Неверно указан артикул"
                }
            ]
        }
    }
]
```
