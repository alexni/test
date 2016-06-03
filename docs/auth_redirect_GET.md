[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/auth_redirect**

**Требуется наличие Access Token Level 1 или Level 2 заголовке**

Вызывается для логина через социальную сеть или для подключения социальной сети. В ответ сервер редиректит на социальную сеть для осуществления логина. После того, как пользователь авторизовался в соц. сети, сервер делает еще один редирект в приложение **(GET запрос)**, передавая в качестве параметра **Access Token Level 2**.

### Параметры

* **social_network** - имя социальной сети **(ОБЯЗАТЕЛЬНЫЙ)**


### Ответ

НЕТ

### Ошибки (error codes)

**Ошибки должны быть обработаны на стороне сервера, т.к. в случае WebApp, приложение передает управление серверу**

* **400** (Bad Request) Некоторые параметры запросы не верны
* **401** (Unauthorized) Требуется идентификация (например отсутствует токен первого уровня в http headers)
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
