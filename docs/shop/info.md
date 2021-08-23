# Общие данные по магазину

## GET /shop

Возвращает общие данные по магазину

- Ресурс **/shop**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Описание полей ответа

**balance** - Количество BYN на счету с учетом порога доверия;

**isBlocked** - Заблокирован ли магазин;

**shopDiscount** - Скидка на магазин;

**townsDiscount** - **(Неактуальное)** Скидки на город
```json
{
  "id города": {
    "title": "Название города",
    "discount": скидка
  }
}
```
**sectionsDiscounts** - Скидки на разделы
```json
{
  "id раздела": {
    "shopSection": "скидка магазина на раздел"
  }
}
```

### Пример запроса

```
GET /shop
Accept: application/json
```

```json
{
  "balance": 15.01,
  "isBlocked": false,
  "shopDiscount": 1,
  "townsDiscount": {
    "1": {
      "title": "Minsk",
      "discount": 5.2
    }
  },
  "sectionsDiscounts": {
    "2": {
      "shopSection": 13
    },
    "3": {
      "shopSection": 22
    }
  }
}
```
