[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_change_password**


Поменять пароль. Возможно использовать только при наличии токена типа **adventize**.

### Параметры

* **old_password** - текущий пароль пользователя **(ОБЯЗАТЕЛЬНЫЙ)**
* **new_password** - новый пароль пользователя **(ОБЯЗАТЕЛЬНЫЙ)**
* **token** - token **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

НЕТ

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Старый пароль не совпал с присланным old_password или пользователя с таким токеном не существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
