# Получение справочной информации

## GET /sections

Возвращает полный список активных разделов каталога

- Ресурс **/sections**
- HTTP-метод **GET**
- Формат ответа **JSON**

### Параметры

- **filter** [optional] Фильтр для раздела подключен/неподключен
    - **enabled** Только подключенные разделы к магазину
    - **disabled** Только неподключенные разделы к магазину
- **title** [optional] Поиск по имени раздела (по подстроке)

### Пример 1. Полный список разделов

```
GET /sections
```

```json
{
    1:"Телефоны",
    2:"Зарядные устройства для телефонов",
    3:"Компьютеры"
}
```

### Пример 2. Список подключенных разделов

```
GET /sections?filter=enabled
```

```json
{
    1:"Телефоны",
    3:"Компьютеры"
}
```

### Пример 3. Поиск разделов по названию

```
GET /sections?title=теле
```

```json
{
    1:"Телефоны",
    2:"Зарядные устройства для телефонов",
}
```
