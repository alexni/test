[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/aff/1.0/send_confirm_mail**

Присылает сообщение с линкой на подтверждение почтового ящика.
### Параметры

* **token** - token **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

НЕТ

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Ресур не найден, означает, что пользователя с таким токеном не существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
