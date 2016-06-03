[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_sign_up**

Зарегистрировать пользователя в системе. В ответ приходит токен (типа adventize), который нужно хранить в куках на клиенте. Если аккаунт с таким email
уже существует то вернется 412 error code.

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
* **412** (Precondition Failed Exception) Аккаунт с таким email уже существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
