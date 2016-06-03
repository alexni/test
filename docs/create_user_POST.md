[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/audit/1.0/create_user**

**Требуется наличие Audit Token в заголовке**

Создать пользователя

### Параметры

login обязательный параметр, логин
password обязательный параметр, пароль
description, обязательный параметр, фио пользователя
role не обязательный параметр, роль

### Ответ
````
{
    "login": "login",
    "password": "password",
    "role": "ADMIN",
    "description": "description",
    "lastUpdated": "время последнего изменения"
}
````
### Ошибки (error codes)

* **400** (Bad Request) Не хватает параметров
* **401** (Unauthorized) Требуется идентификация (например отсутствует токен в http headers)
* **409** (Conflict) Пользователь с логином уже с существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Home](../README.md)
