# Отчет по импорту

## GET /pricelists/{pricelistId}/report

Возвращает список ошибок, возникших во время импорта

- Ресурс **/pricelists/{pricelistId}/report**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Возможные ошибки валидации прайс-листа

- category Раздел каталога
    - ERROR_CATEGORY_NOT_FOUND "Неверно указан или не указан раздел"
- vendor Производитель
    - ERROR_VENDOR_NOT_FOUND "Неверно указан или не указан производитель товара"
- model Товар
    - ERROR_MODEL_NOT_FOUND "Неверно указана или не указана модель товара"
- price Цена
    - NOT_LESS_EQUAL_TO "превышает допустимое значение"
- currency Валюта
    - ERROR_INVALID_CURRENCY "недопустимое значение"
    - NOT_IN_ARRAY "Неверное значение поля"
- isCashless, isCredit Безнал, Кредит
    - ERROR_INVALID_FLAG "недопустимое значение поля"
- status Статус товара (нет в наличии, на складе, ...)
    - ERROR_INVALID_STATUS "недопустимое значение поля"
    - NOT_IN_ARRAY "неверное значение поля"
- delivery Тип доставки
    - ERROR_INVALID_DELIVERY "Тип доставки: недопустимое значение поля"
    - NOT_IN_ARRAY "неверное значение поля"
- warranty Гарантия
    - NOT_LESS_EQUAL_TO "превышает допустимое значение"
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
            "currency": "BYR",
            "category": "GPS-навигаторы",
            "vendor": "Jagga",
            "model": "X4",
            "price": "8120",
            "status": "Нет",
            "comment": "фывфы",
            "warranty": "250",
            "delivery": "",
            "isCashless": "",
            "isCredit": ""
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
            "delivery": [
                {
                    "code": "ERROR_INVALID_DELIVERY",
                    "message": "недопустимое значение поля"
                },
                {
                    "code": "VALUE_NOT_INCLUDED_IN_ARRAY",
                    "message": "неверное значение поля"
                }
            ]
        }
    },
    {
        "values": {
            "currency": "BYR",
            "category": "GPS-навигаторы",
            "vendor": "Jagga",
            "model": "X4",
            "price": "8120",
            "status": "Нет",
            "comment": "фывфы",
            "warranty": "250",
            "delivery": null,
            "isCashless": null,
            "isCredit": null
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
            "delivery": [
                {
                    "code": "ERROR_INVALID_DELIVERY",
                    "message": "недопустимое значение поля"
                },
                {
                    "code": "VALUE_NOT_INCLUDED_IN_ARRAY",
                    "message": "неверное значение поля"
                }
            ]
        }
    }
]
```
