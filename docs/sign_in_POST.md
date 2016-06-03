[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/sign_in**

**Требуется наличие Access Token Level 1 в заголовке**

Зарегистрировать пользователя в системе или совершить логин уже существующим пользователем.

МТС запрашивает **WebApp** с GET-параметрами:

* **login** - уникальный идентификатор пользователя
* **provider** - имя провайдера
* **hash** - хэш, полученный из login, provider и **salt** на стороне сервера провайдера, известной и нашему серверу.

Дальше **WebApp** напрямую передает их в **Identity**.

### Параметры

* **login** - уникальный идентификатор пользователя. Это может быть его **email** или **номер мобильного телефона** в случае с МТС **(ОБЯЗАТЕЛЬНЫЙ)**
* **password** - пароль пользователя (в случаях перехода из личных кабинетов сотовых операторов может отсутствовать)
* **provider** - имя провайдера, например "MTC" **(ОБЯЗАТЕЛЬНЫЙ в случае входа через провайдера)**
* **hash** - секретный hash **(ОБЯЗАТЕЛЬНЫЙ в случае входа через провайдера)**

### Ответ
````
{
      “access_token_level_two”:“sdsasdf4423sd”,
      “token_expires_at”:900000 //время (UNIX time) в миллисекундах, после которого токен второго уровня станет не валидным,
      
      "account_id":"asdff872bbkkd",
      "login":"bad.pig@mail.ru",
      "email_confirmed":true, //true or false
      "nick_name":"angryPig",
      "real_name":"Vladimir Ivanov",
      "sex":"yes baby!", // ;-)
      "birthday":"1987-09-23", //дата в формате YYYY-MM-DD
      
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
