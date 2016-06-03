[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/webapp_get_sign_in_url_for_social_network**

Возвращает url, куда нужно перенаправит пользователя для логина в социальную сеть.

### Параметры

* **sn**  Тип социальной сети (например, vk, vkontakte, google, twitter и т.д.) **(ОБЯЗАТЕЛЬНЫЙ)**
* **rc**  Reference code - код который может быть использован для начисления бонусов пользователю, порекомендовавшему зарегистрироваться новому пользователю

### Ответ
````
http://sn.ru/login?callback=http%3A%2F%2Fadvetize.ru
 
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Home](../README.md)
