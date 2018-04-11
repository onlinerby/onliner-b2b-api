## Авторизация импортера

### POST /importers/token

### Параметры запроса<a name="parameters"></a>:

|Параметр|Тип|Описание|
|---|---|---|
|client_id|string|Client ID импортера|
|client_secret|string|Client Secret импортера|

### Пример запроса на авторизацию

```http
POST /importers/token
Accept: application/json
Content-Type: application/json
```
```json
{
    "client_id": "c781563eab0532a65a3z",
    "client_secret": "953fce619ae9055113fdce74494bea36b68f515b"
}
```

### Ответ в случае успешной авторизации<a name="response"></a>:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```
```json
{
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ",
    "expires_in": 600,
    "token_type": "Bearer"
}
```

### Описание полей ответа<a name="fields"></a>:

|Параметр|Тип|Описание|
|---|---|---|
|access_token|string|Авторизационный токен|
|expires_in|integer|Время жизни токена (в секундах)|
|token_type|string|Тип авторизационного токена|

### Ответ при ошибке авторизации

```http
HTTP/1.1 404 Not Found
```

### Ответ при возникновении ошибок валидации

```http
HTTP/1.1 422 Unprocessable Entity
Content-Type: application/json; charset=utf-8
```
```json
{
    "code": {
        "id": "validation.failed",
        "text": "Validation failed"
    },
    "errors": {
        "client_id": [
            {
                "id": "validation.required", 
                "text": "The client_id field is required"
            }
        ]
    }
}
```

### Возможные ошибки для полей<a name="errors"></a>:

|Параметр|Идентификатор ошибки|Текст ошибки|
|---|---|---|
|client_id|validation.required|The client_id field is required|
|client_id|validation.string|Value may only be a string|
|client_secret|validation.required|The client_secret field is required|
|client_secret|validation.string|Value may only be a string|
