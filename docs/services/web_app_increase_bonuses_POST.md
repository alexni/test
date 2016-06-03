[Home](../../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**POST   https://{cloud root}/identity/service/1.0/webapp_increase_bonus**

Обязательно наличие хэдера **X-Service-To-Service-Access-Token**

Добавить пользователю денег/очков/ или других благ. Если аккаунта с таким **email** не существует, то возвращается ошибка 404.

### Параметры

* **email**  **(ОБЯЗАТЕЛЬНЫЙ)**
* **amount** - количество денег/благ **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

empty

### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found Exception) Ресурс не найден
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../../README.md)
