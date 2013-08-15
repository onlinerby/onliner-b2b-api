# Авторизация
Авторизация в API осуществляется по протоколу [OAuth 2.0](http://oauth.net/2/).

Для получения авторизационного токена необходимо послать POST-запрос c указанием Basic Authentication на адрес авторизации (https://b2bapi.onliner.by/oauth/token). Параметры для авторизации должны быть _Clinet ID_ и _Client Secret_ со страницы настройки OAuth-приложения. 
Так же необходимо передать параметр POST-запроса _grant_type_ со значением _client_credentials_:

Пример с использованием библиотеки curl:
```
curl -u 204da9b95e2480a3455f:7a4bbb61262fdf41d410645292a0489ba752c6b9 https://b2bapi.onliner.by/oauth/token -d 'grant_type=client_credentials'
```

# Запрос к API
После получения _Access Token_ вы можете обращаться к ресурасм API, указав токен одним из двух способов:

- аргумент запроса (пример с использованием библиотеки curl)
```
curl -H 'Accept: application/json' \
  https://b2bapi.onliner.by/shop?access_token=RECIVED_TOKEN_STRING
```

- в заголовке HTTPS-запроса (пример с использованием библиотеки curl)
```
curl -H 'Accept: application/json' \
  -H 'Authorization: Bearer RECIVED_TOKEN_STRING' \
  https://b2bapi.onliner.by/shop
```

## Время действия токена
Токен действителен в течение одного часа. По прошествии этого времени вы можете сделать следующий запрос авторизации, чтобы получить новый _Access Token_.