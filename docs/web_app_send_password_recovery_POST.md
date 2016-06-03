[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/webapp_send_password_recovery**

Прислать письмо с линком на метод изменения пароля, работает только с ранее подтвержденными почтовыми адресами.

### Параметры

* **email** - **(ОБЯЗАТЕЛЬНЫЙ)**

* **app_id** идентификатор паблишера из Manager Dashboard **(НЕ ОБЯЗАТЕЛЬНЫЙ)**
* **idfa** - idfa устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан device_id)**
* **device_id** - id устройства. Передавать либо idfa, либо device_id. **(НЕОБЯЗАТЕЛЬНЫЙ, если передан idfa)**
* **open_udid** - openUdid устройства **(НЕОБЯЗАТЕЛЬНЫЙ, если передан android_id)**
* **android_id** - android_id устройства (только для os Android) **(НЕОБЯЗАТЕЛЬНЫЙ, если передан open_udid)**
* **os_version** версия операционной системы **(НЕ ОБЯЗАТЕЛЬНЫЙ)**
* **device_type** тип устройства, варианты: iphone|ipad|ipod **(НЕ ОБЯЗАТЕЛЬНЫЙ)**
* **uid** идентификатор пользователя **(НЕ ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

НЕТ

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Email не найден или не подтвержден или пользователь с таким токеном не существует
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)