# Получение справочной информации

## GET /sections/{sectionId}/manufacturers

Возвращает список производителей в указанном разделе

- Ресурс **/sections/{sectionId}/manufacturers**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

- **title** [optional] Поиск по имени производителя (по подстроке)

### Пример 1. Список производителей в разделе

```
GET /sections/1/manufacturers
```

```json
{
    1:"Panasonic",
    2:"Pantech",
    3:"Philips"
}
```

### Пример 2. Поиск по названию

```
GET /sections/1/manufacturers?title=pan
```

```json
{
    1:"Panasonic",
    2:"Pantech"
}
```
