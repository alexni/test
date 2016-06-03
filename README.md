[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)



Identity
====

Краткое обоснование сервиса можно посмотреть [тут](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/IdentityService.md)

### API сервиса Identity

**API** сервиса построено на базе [соглашений](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/RESTAPIBasic.md), принятых в наше платформе.

Взаимодействие с сервером ведется по REST архитектуре.

Если запрос обработался без ошибок возвращается success code = **200**. 

Ошибки обрабатываются с помощью HTTP error codes.

Для запросов **GET** набор необходимых заголовков следующий :

* **Accept-Language** : **ru** или **en** изменяется в зависимости от установленной локализации на клиенте
* **X-Access-Token** : **{accessToken}**
* **X-Application-Flag** : **{application flag}** //флаг для того, чтобы отделить тестовую версию приложения
* **X-Application-Name** : **{application name}**
* Единственный метод не требующий, чтобы в заголовке присутствовал **X-Access-Token** это метод получения accessToken-а [access (POST)](docs/access_POST.md)

Для запросов **POST** набор необходимых заголовков следующий :

* **Content-Type** : **application/x-www-form-urlencoded**
* **Accept-Language** - **ru** или **en** изменяется в запаскевисимости от установленной локализации на клиенте
* **X-Access-Token** - **{accessToken}**
* **X-Application-Flag** : **{application flag}** //флаг для того, чтобы отделить тестовую версию приложения
* **X-Application-Name** : **{application name}**
* Единственный метод не требующий, чтобы в заголовке присутствовал **X-Access-Token** это метод получения accessToken-а [access (POST)](docs/access_POST.md)

### Методы партнеров

[sign_up (POST)](docs/aff_sign_up_POST.md) - зарегестрироваться

[sign_in (POST)](docs/aff_sign_in_POST.md) - залогиниться

[change_password (POST)](docs/aff_change_password_POST.md) - сменить пароль

[send_confirm_mail (POST)](docs/aff_send_confirm_mail_POST.md) - запрос на отправку письма для подтверждения почтового адреса

[send_password_recovery (POST)](docs/aff_send_password_recovery_POST.md) - запрос на отправку письма c новым паролем.


### Методы WebApp

Методы WebApp-а не требуют наличия заголовков **X-Access-Token**, **X-Application-Flag**, **X-Application-Name**

[webapp_sign_up (POST)](docs/web_app_sign_up_POST.md) - зарегестрироваться

[webapp_sign_in (POST)](docs/web_app_sign_in_POST.md) - залогиниться

[webapp_fetch_infos (GET)](docs/web_app_fetch_infos_GET.md) - получить информацию о девайсе и приложениях

[webapp_update (POST)](docs/web_app_update_POST.md) - обновить информацию

[webapp_change_password (POST)](docs/web_app_change_password_POST.md) - сменить пароль

[webapp_send_confirm_mail (POST)](docs/web_app_send_confirm_mail_POST.md) - запрос на отправку письма для подтверждения почтового адреса

[webapp_send_password_recovery (POST)](docs/web_app_send_password_recovery_POST.md) - запрос на отправку письма c новым паролем.

[web_app_idfa_already_registered (GET)](docs/web_app_idfa_already_registered_GET.md) - информация о регистрации устройства

### Методы для гостя отключены

[web_app_guest (POST)](docs/web_app_guest_POST.md) - получить гостевой токен


### Методы WebApp для **service** уровня.

**Все эти методы требуют наличия в хэдере токена уровня ServiceToService  (имя хэдера : X-Service-To-Service-Access-Token)  **

[webapp_increase_bonus (POST)](docs/services/web_app_increase_bonuses_POST.md) - начисление бонусов/благ.

### Методы

[access (POST)](docs/access_POST.md) - получить accessToken

[sign_in (POST)](docs/sign_in_POST.md) - зарегистрироваться/залогиниться в системе 

[auth_redirect (GET)](docs/auth_redirect_GET.md) - авторизоваться через социальную сеть или подключить новую

[remove_network (POST)](docs/remove_network_POST.md) - отключить социальную сеть от аккаунта

[forgot_password (POST)](docs/forgot_password_POST.md) - забыл пароль

[user_info (GET)](docs/user_info_GET.md) - получить информацию о **ЗАЛОГИНЕННЫМ** пользователе

[change_user_info (POST)](docs/change_user_info_POST.md) - изменить пользовательские данные

[Технологический стэк & Архитектура Платформы Adventize](https://github.com/WiseWaveCorporationLimited/platform-architecture/blob/master/README.md)

### Методы админки Audit

[get_user_info (GET)](docs/get_user_info_GET.md) - получить информацию о пользователе

[check_access_right (GET)](docs/check_access_right_GET.md) - проверить права пользователя для данного метода

[get_all_internal_users (GET)](docs/get_all_internal_users_GET.md) - получить всех пользователей

[get_all_roles (GET)](docs/get_all_roles_GET.md) - получить все роли

[get_all_logs (GET)](docs/get_all_logs_GET.md) - получить все логи

[get_logs_by_login (GET)](docs/get_logs_by_login_GET.md) - получить логи по логину

[get_logs_by_method (GET)](docs/get_logs_by_method_GET.md) - получить логи по методу




[login (POST)](docs/login_POST.md) - логин

[set_access_right (POST)](docs/set_access_right_POST.md) - установка прав для метода

[set_user_role (POST)](docs/set_user_role_POST.md) - установка роли пользователя

[create_user (POST)](docs/create_user_POST.md) - создать пользователя

[update_user (POST)](docs/update_user_POST.md) - изменить информацию о пользователе

[delete_user (POST)](docs/delete_user_POST.md) - удалить пользователя

[create_method (POST)](docs/create_method_POST.md) - создать метод

[update_method (POST)](docs/update_method_POST.md) - изменить метод

[delete_method (POST)](docs/delete_method_POST.md) - удалить метод

### Сообщения
[send_message (POST)] (docs/send_message_POST.md) - отправить сообщение

[set_readed (POST)] (docs/set_readed_POST.md) - сообщения прочитаны

[set_unreaded (POST)] (docs/set_unreaded_POST.md) - сообщения непрочитаны

[remove (POST)] (docs/remove_POST.md) - удалить сообщения




