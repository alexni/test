[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/audit/1.0/create_method**

**Требуется наличие Audit Token в заголовке**

Создать метод

### Параметры

method обязательный параметр, имя метода.
description обязательный параметр, описание метода
role - не обязательный параметр, роль, которой разрешена работа с методом


### Ответ
````
{
"method": "MethodName",
"description": "Description",
"role" : "ADMIN, BIS_DEV"
}
````
### Ошибки (error codes)

* **400** (Bad Request) Не хватает параметров
* **401** (Unauthorized) Требуется идентификация (например отсутствует токен в http headers)
* **409** (Conflict) Метод с таким именем уже существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Home](../README.md)
