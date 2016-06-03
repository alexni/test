[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/change_user_info**

**Требуется наличие Access Token Level 2 в заголовке**

Изменить пользовательские данные, такие как **login, nick_name, real_name, sex, birthday**.
В ответе приходят уже измененные данные.
 
### Параметры

* **login**
* **nick_name**
* **real_name**
* **sex**
* **birthday**

Нужно передавать только те параметры, которые планируется изменить.

### Ответ
````
{
      "account_id":"asdff872bbkkd",
      "login":"bad.pig@mail.ru",
      "email_confirmed":true, //true or false
      "nick_name":"angryPig",
      "real_name":"Vladimir Ivanov",
      "sex":"yes baby!", // ;-)
      "birthday":"1987-09-23", // дата в формате YYYY-MM-DD
      
      "enabled_social_networks":["FB", "VK, "OD", "TWITTER"],
      "enabled_providers":["QIWI"]
}
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **401** (Unauthorized) Требуется идентификация (например отсутствует токен первого уровня в http headers)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
