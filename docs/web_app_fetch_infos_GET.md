[Home](../README.md)

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Описание


**GET   https://{cloud root}/identity/user/1.0/webapp_fetch_infos**

Получить информацию об устройстве и установленных приложениях. В параметрах передается токен и его тип.

### Параметры

* **token** - токен, который храниться на клиенте, в куках **(ОБЯЗАТЕЛЬНЫЙ)**
* **token_type** - типа токена, возможные значения **adventize** и **guest** **(ОБЯЗАТЕЛЬНЫЙ)**

### Ответ

                {
                    "email": "a@example.com",
                    "confirmed_email": false,
                    "money": 1.4,
                    "user_app_info" : [
                        {
                            "device_id":"sdssfdssdsd",
                            "open_udid":"sdc23eee",
                            "os_version":"7.1",
                            "device_type":"iphone",
                            "uid":"userUid",
                            "app_id":"9001"
                        },
                        {
                            "device_id":"sdssfdssdsd2222",
                            "open_udid":"sdc23eee2222",
                            "os_version":"7.1",
                            "device_type":"iphone",
                            "uid":"userUid2",
                            "app_id":"9002"
                        }
                    ]
                }
                
### в случае, если был передан токен типа **guest** ответ может выглядеть так

                    {
                    "email": null,
                    "confirmed_email": false,
                    "money": null,
                    "user_app_info" : [
                        {
                            "device_id":"sdssfdssdsd",
                            "open_udid":"sdc23eee",
                            "os_version":"7.1",
                            "device_type":"iphone",
                            "uid":"userUid",
                            "app_id":"9001"
                        }
                    ]
                }


### Ошибки (error codes)

* **400** (Bad Request) Некоторые параметры запросы не верны
* **404** (Not Found) Ресур не найден
* **429** (Too Many Requests) Превышен лимит обращений к этому методу API. В нашей платформе используется схема [rate limit](http://en.wikipedia.org/wiki/Rate_limiting)
* **500** (Internal Server Error) Ошибка на стороне сервера. Можно повторить запрос.


[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

[Home](../README.md)
