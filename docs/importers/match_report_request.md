## Заявка на генерацию отчета по сопоставленным товарам импортера

### POST /importers/match-reports/requests

При выполнении запроса должен быть указан токен авторизации.

### Пример запроса

```http
POST /importers/match-reports/requests
Accept: application/json
Authorization: Bearer <token>
```

###  Пример ответа

```http
HTTP/1.1 202 Accepted
Content-Type: application/json; charset=utf-8
```
```json
{
    "id": "5a16c41acab2fd0202641102",
    "importerId": 1,
    "createdAt": "2018-04-01T12:00:00+03:00",
    "updatedAt": "2018-04-01T12:00:00+03:00",
    "status": "pending",
    "report": []
}
```

#### Описание полей ответа

Соответствует формату ответа метода для получения отчета `GET /importers/match-reports/{id}`.

### Ответ при ошибке авторизации

```http
HTTP/1.1 401 Unauthorized
```
