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

**sectionsCost** - Стоимость разделов в месяц – сумма стоимости размещения в каждом подключенном разделе;

**dailySectionsCost** - Суточный расход по разделам – сумма суточных стоимостей всех подключенных разделов;

**daysOfWork** - Прогноз отключения - количество дней до автоматической блокировки. Рассчитывается как (баланс лицевого счета) /
(сумма суточных стоимостей всех подключенных разделов с учетом скидок магазинов
+ суточный расход по аукционам у всех магазинов по данному лицевому счету);

**sectionsCostWithDiscount** - Стоимость разделов в месяц с учетом всех скидок;

**dailySectionsCostWithDiscount** - Суточный расход по разделам с учетом всех скидок;

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
  "sectionsCost": 173.46,
  "dailySectionsCost": 5.78,
  "daysOfWork": 274,
  "sectionsCostWithDiscount": 120.6,
  "dailySectionsCostWithDiscount": 4.02
}
```
