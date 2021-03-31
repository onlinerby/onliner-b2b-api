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
    "catalogSection": "Общая скидка на раздел",
    "package": "Скидка на пакет"
  }
}
```

**sectionsCost** - __(deprecated)__ Стоимость разделов в месяц – сумма стоимости размещения в каждом подключенном разделе; C 1го апреля значение 0. В будущем данное поле будет удалено из ответа.

**dailySectionsCost** - __(deprecated)__ Суточный расход по разделам – сумма суточных стоимостей всех подключенных разделов; C 1го апреля значение 0. В будущем данное поле будет удалено из ответа.

**sectionsCostWithDiscount** - __(deprecated)__ Стоимость разделов в месяц с учетом всех скидок; C 1го апреля значение 0. В будущем данное поле будет удалено из ответа.

**dailySectionsCostWithDiscount** - __(deprecated)__ Суточный расход по разделам с учетом всех скидок; C 1го апреля значение 0. В будущем данное поле будет удалено из ответа.

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
      "catalogSection": 5,
      "package": 3
    },
    "3": {
      "shopSection": 22,
      "catalogSection": 3,
      "package": 3
    }
  },
  "sectionsCost": 0,
  "dailySectionsCost": 0,
  "sectionsCostWithDiscount": 0,
  "dailySectionsCostWithDiscount": 0
}
```
