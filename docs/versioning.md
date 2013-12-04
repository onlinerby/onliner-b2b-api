# Работа с версиями API

Для указания версии есть 2 способа:

-   **Указать в URL**

    ```
    GET /<version>/path/to/resource
    ```
    
    - `<version>` - версия API.
    - формат запрашиваемых данных передается в заголовке `Accept:`:
        - `json` - *application/json, application/x-json;*
        - `xml` - *text/xml, application/xml, application/x-xml;*
        - `csv` - *text/csv.*

-   **Указать в заголовке** `Accept:`

    ```
    HTTP/1.1
    Accept: application/vnd.onliner.<version>+<format>
    ```

    - `application/vnd.onliner` - неизменяемая часть заголовка;
    - `<version>` - запрашиваемая версия API;
    - `<format>` - формат запрашиваемых данных. Может быть `json`, `xml`, `csv`.

Варианты не исключают друг друга, но приоритет имеет версия, переданная в `URL`.
Это значит, что если будет выполнен запрос с указанием версии и в заголовке и в URL, будет возвращен результат версии, указанной в `URL`.

Если версия не указана явно ни одним из способов, то возвращается результат версии по умолчанию.
Обычно это последняя версия.

## Ошибки

-   Неправильно указан формат запрашиваемых данных

    Request:

    ```
    HTTP/1.1
    Accept: application/vnd.onliner.v2+foo
    ```
    
    Response:

    ```
    HTTP/1.1 415 Unsupported Media Type
    ```

-   Зарошена неподдерживаемая версия

    Request:

    ```
    GET /v9999/path/to/resource
    ```
    
    ```
    HTTP/1.1
    Accept: application/vnd.onliner.v9999+json
    ```
    
    Response:

    ```
    HTTP/1.1 404 Not Found
    ```
