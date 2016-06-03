[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/user/1.0/access**

**Можно вызывать без Access Token-а**

Получить Access Token **(Level 1)**, который используется для вызовов всех остальных методов сервиса, пока не будет получен Access Token **(Level 2)**. Access Token передается в заголовке всех HTTP/HTTPS запросов. 

Время жизни  Access Token **(Level 1)** 15 суток, после этого он становиться не валидным.

### Параметры

* **deviceId** - уникальный идентификатор устройства **(ОБЯЗАТЕЛЬНЫЙ)**
* **deviceType** - тип устройства iPad/iPhone/iPod/Web **(ОБЯЗАТЕЛЬНЫЙ)**
* **clientVersion** - версия клиента (имеется в виду версия приложения клиента, текущая версия "1.0") **(ОБЯЗАТЕЛЬНЫЙ)**
* **os** - операционная система iOS/Android/Windows **(ОБЯЗАТЕЛЬНЫЙ)**
* **osVersion** - версия операционной системы **(ОБЯЗАТЕЛЬНЫЙ)**

Часть параметров может отсутствовать в случае, если их невозможно получить.


### Ответ
````
{
      “access_token_level_one”:“sdsasdf4423sd”,
      “token_expires_at”:900000, //время (UNIX time) в миллисекундах, после которого токен первого уровня станет не валидным
      "redirect_url":"link"
}
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
