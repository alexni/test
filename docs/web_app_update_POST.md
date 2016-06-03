[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_update**

Обновить информацию о девайсе и приложениях.
Вызывается клиентом каждый раз при переходе из приложения и наличия токена (любого типа) в куках.

### Параметры

* **app_id** - Id приложения через которое пришел пользователь **(ОБЯЗАТЕЛЬНЫЙ)**
* **idfa** - idfa устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан device_id)**
* **device_id** - id устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан idfa)**
* **open_udid** - openUdid устройства **(НЕОБЯЗАТЕЛЬНЫЙ, если передан android_id)**
* **android_id** - android_id устройства (только для os Android) **(НЕОБЯЗАТЕЛЬНЫЙ, если передан open_udid)**
* **os_version** - версия os **(ОБЯЗАТЕЛЬНЫЙ)**
* **device_type** -  iphone|ipad|ipod **(ОБЯЗАТЕЛЬНЫЙ)**
* **uid** - id пользователя в игре **(ОБЯЗАТЕЛЬНЫЙ)**
* **token** - токен, хранящийся в куках **(ОБЯЗАТЕЛЬНЫЙ)**
* **token_type** - типа токена, возможные значения **adventize** и **guest** **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

                {
                    "token": "sdfsdfsdgsdg",
                    "type":"adventize",
                    "email": "a@example.com",
                    "confirmed_email": false,
                    "money": 1.4
                }

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Ресур не найден
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
