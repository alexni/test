[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/message/1.0/send_message**

Отправить сообщение адресату

### Параметры

* **account_id** - уникальный идентификатор адресата **(ОБЯЗАТЕЛЬНЫЙ)**
* **body** - сообщение **(ОБЯЗАТЕЛЬНЫЙ)**
* **category** - вид сообщения (news/message/notification) **(ОБЯЗАТЕЛЬНЫЙ)**

Часть параметров может отсутствовать в случае, если их невозможно получить.


### Ответ
````
в ответ приходит статус сообщения
{"result: "ok"}
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
