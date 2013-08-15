# Получение справочной информации

## GET /sections/{sectionId}/manufacturers/{manufacturerId}/products

Возвращает список товаров указанного производителя

- Ресурс **/sections/{sectionId}/manufacturers/{manufacturerId}/products**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

- **title** [optional] Поиск по имени товара (по подстроке)

### Пример 1. Список товаров указанного производителя

```
GET /sections/1/manufacturers/2/products
```

```json
{
    1:"Panasonic Eluga",
    2:"Panasonic Eluga Power",
    3:"Panasonic GD55"
}
```

### Пример 2. Поиск по названию

```
GET /sections/1/manufacturers/2/products?title=eluga
```

```json
{
    1:"Panasonic Eluga",
    2:"Panasonic Eluga Power"
}
```
