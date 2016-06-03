[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/webapp_process_sign_in_for_social_network**

Обрабатывает callback со стороны социальной сети после успешной аунтефикации пользователя и авторизует приложение делать запросы 
от имени пользователя, инициируя сессию с секретным токеном доступа, возвращая объект токена с информацией о пользователе
 в социальной сети

### Параметры

* **sn**  Тип социальной сети (например, vk, vkontakte, google, twitter и т.д.) **(ОБЯЗАТЕЛЬНЫЙ)**
* **rc**  Reference code - код который может быть использован для начисления бонусов пользователю, порекомендовавшему зарегистрироваться новому пользователю
* **auth_code**  Ключ, передаваемый социальной сетью, необходимый для инициации сессии. **(ОБЯЗАТЕЛЬНЫЙ)**
* **device_id** Идентификатор устройства
* **app_id** Идентификатор приложения
* **open_udid** open_udid устройства
* **os_version** версия OS
* **device_type** тип устройства
* **uid** uid устройства

### Ответ
````
 {
 
     "accountId": "355747",
     "confirmed_email": false,
     "money": 0,
     "token": "9fec5c7f-6b45-4a73-98a4-90a724011197",
     "type": "socialnetwork",
     "name": "Кондрат Семиухий",
     "avatarPic": "http://cs456.vk.me/u355747/e_cbgds6d6.jpg",
     "socialNetworkType": "vk"
 
 }
 
````
### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **401** (Not Authorized) Не удалось получить авторизованную сессию для выполнения запросов к социальной сети.
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Home](../README.md)
