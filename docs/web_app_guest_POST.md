[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_guest**

Получить токен типа **guest**. 

### Параметры

* **app_id** - Id приложения через которое пришел пользователь **(ОБЯЗАТЕЛЬНЫЙ)**
* **idfa** - idfa устройства **(ОБЯЗАТЕЛЬНЫЙ)**
* **open_udid* - openUdid устройства **(ОБЯЗАТЕЛЬНЫЙ)**
* **os_version** - версия os **(ОБЯЗАТЕЛЬНЫЙ)**
* **device_type** -  iphone|ipad|ipod **(ОБЯЗАТЕЛЬНЫЙ)**
* **uid** - id пользователя в игре **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

````
{
      "token":"sdfsdfsdgsdg",
      "type":"guest", //тип токена
      "email": null,
      "confirmed_email": false,
      "money": null
}
````

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
