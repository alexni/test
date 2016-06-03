[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/user_info**

**Требуется наличие Access Token Level 2 в заголовке**

Возвращает информацию по текущему **ЗАРЕГИСТРИРОВАННОМУ** пользователю

### Параметры

НЕТ 

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

* **401** (Unauthorized) Требуется идентификация (например отсутствует токен второго уровня в http headers)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Home](../README.md)
