[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_sign_in**

Залогиниться уже существующим пользователем. 
В ответ приходит токен (типв adventize), который нужно хранить в куках на клиенте.
Отличие этого метода от [web_app_sign_up (POST)](web_app_sign_up_POST.md) в том, что пользователь должен указать 
уже существующий **email/password**. В противном случае вернется **404** error code.  

### Параметры

* **email**  **(ОБЯЗАТЕЛЬНЫЙ)**
* **pass** - пароль пользователя **(ОБЯЗАТЕЛЬНЫЙ)**
* **app_id** - Id приложения через которое пришел пользователь **(ОБЯЗАТЕЛЬНЫЙ)**
* **idfa** - idfa устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан device_id)**
* **device_id** - id устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан idfa)**
* **open_udid** - openUdid устройства **(НЕОБЯЗАТЕЛЬНЫЙ, если передан android_id)**
* **android_id** - android_id устройства (только для os Android) **(НЕОБЯЗАТЕЛЬНЫЙ, если передан open_udid)**
* **os_version** - версия os **(ОБЯЗАТЕЛЬНЫЙ)**
* **device_type** -  iphone|ipad|ipod **(ОБЯЗАТЕЛЬНЫЙ)**
* **uid** - id пользователя в игре **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

````
{
      "token":"sdfsdfsdgsdg",
      "type":"adventize", //тип токена, возможные значения adventize или guest
      "email": "a@example.com",
      "confirmed_email": false,
      "money": 1.4
}
````

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Ресур не найден (введен не существующий логин/пароль)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
