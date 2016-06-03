[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/audit/1.0/get_all_internal_users**

**Требуется наличие Audit Token в заголовке**

Возвращает информацию по  всем пользователям админки

### Параметры


### Ответ
````
{
    {
    "login": "login",
    "password": "password",
    "role": "ADMIN",
    "description": "description",
    "lastUpdated": "время последнего изменения"
    }
    ...
}
````
### Ошибки (error codes)

* **401** (Unauthorized) Требуется идентификация (например отсутствует токен в http headers)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Home](../README.md)
