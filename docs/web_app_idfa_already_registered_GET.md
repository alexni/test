[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/web_app_idfa_already_registered**

Возвращает true если устройство уже регистрировалось.

### Параметры

НЕТ 

### Ответ
````
 {
   "result": true
 }
 
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Home](../README.md)
