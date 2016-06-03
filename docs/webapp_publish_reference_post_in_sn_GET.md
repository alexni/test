[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/webapp_publish_reference_post_in_sn**

Публикует запись с реферальной ссылкой в ленту акаунта пользователя в социальной сети 

### Параметры

* **sn**  Тип социальной сети (например, vk, vkontakte, google, twitter и т.д.) **(ОБЯЗАТЕЛЬНЫЙ)**
* **account_id**  Идентификатор пользователя в социальной сети
* **device_id** Идентификатор устройства
* **app_id** Идентификатор приложения
* **open_udid** open_udid устройства
* **os_version** версия OS
* **device_type** тип устройства
* **uid** uid устройства 

### Ответ
````
 The 
 
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **401** (Not Authorized) Пользовательская сессия в социальной сети неавторизована.
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Home](../README.md)
