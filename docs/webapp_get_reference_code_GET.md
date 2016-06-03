[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/webapp_get_reference_code**

Возвращает Reference Code для пользователя, который может быть использован другими пользователями 
(опосредованно через переход по ссылкам) при регистрации для получения бонусов.

### Параметры

* **account_id**  Почта пользователя или идентификатор в соц. сети **(ОБЯЗАТЕЛЬНЫЙ)**
* **sn**  Тип социальной сети (например, vk, vkontakte, google, twitter и т.д.) 

### Ответ
````
 lld8s9dfdskjfnnvns989fsdKTfsa899
 
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Home](../README.md)
