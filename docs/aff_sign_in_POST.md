[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/aff/1.0/sign_in**

Залогиниться уже существующим пользователем. 
В ответ приходит токен, который нужно хранить в куках на клиенте.
Отличие этого метода от [sign_up (POST)](sign_up_POST.md) в том, что пользователь должен указать
уже существующий **email/password**. В противном случае вернется **404** error code.  

### Параметры

* **email**  **(ОБЯЗАТЕЛЬНЫЙ)**
* **pass** - пароль пользователя **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

````
{
      "token":"sdfsdfsdgsdg",
      "email": "a@example.com",
      "confirmed_email": false
}
````

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Ресур не найден (введен не существующий логин/пароль)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
