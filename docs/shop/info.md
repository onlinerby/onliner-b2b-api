# Общие данные по магазину

## GET /shop

Возвращает общие данные по магазину

- Ресурс **/shop**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Описание полей ответа

**balance** - Количество тарифных единиц на счету с учетом порога доверия и обещанного платежа;

**isBlocked** - Заблокирован ли магазин;

**shopDiscount** - Скидка на магазин;

**townsDiscount** - Скидки на город
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
    "shopSection": "скидка магазина на раздел",
    "package": "Скидка на пакет"
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
  "balance": 1500,
  "isBlocked": false,
  "shopDiscount": 1,
  "townsDiscount": {
    "1": {
      "title": "Minsk",
      "discount": 5.2
    },
    "2": {
      "title": "Brest",
      "discount": 12.5
    }
  },
  "sectionsDiscounts": {
    "2": {
      "shopSection": 13,
      "package": 3
    },
    "3": {
      "shopSection": 22,
      "package": 3
    }
  }
}
```
