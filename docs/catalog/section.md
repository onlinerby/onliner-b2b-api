# Получение справочной информации

## GET /sections/{sectionId}

Возвращает параметры указанного раздела

- Ресурс **/sections/{sectionId}**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример. Полный список разделов

```
GET /sections/1
```

```json
{
    "id":1,
    "title":"Телевизоры",
    "positionsCount":15,
    "enabled":false
}
```
