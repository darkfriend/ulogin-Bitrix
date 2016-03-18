# uLogin

Donate link: [https://ulogin.ru](https://ulogin.ru "https://ulogin.ru")  
Tags: ulogin, login, social, authorization  
Requires at least: 11.0.0  
Tested up to: 15.5.10  
Stable tag: 2.1.5  
License: GNU General Public License, version 2  

**uLogin** — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток пользователей из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)

## Установка (Marketplace)

- Зайдите в раздел администрирования Marketplace.
- Найдите модуль **ulogin** от разработчика **DelaWeb**, прописав в поле поиска *ulogin*, и установите его.
- Установленный модуль заработает сразу после активации с настройками по умолчанию.
- Используйте виджет авторизации uLogin в визуальном HTML-редакторе, в качестве Служебного компонента.
- Используйте виджет синхронизации аккаунтов uLoginSync в визуальном HTML-редакторе личного кабинета, в качестве Служебного компонента.

Более детальную информацию смотрите на сайте [uLogin](https://ulogin.ru/help.php "Помощь")

## Модуль "uLogin"

Данный модуль находится в визуальном HTML-редакторе, в качестве компонента *Служебные*.

#### Компонент *Ulogin*:
Настройки:

**uLogin ID общая форма №1:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);  
**uLogin ID общая форма №2:** дополнительное общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);  
**Отправлять email администратору при регистрации пользователя:** установите флажок, если необходимо выслать письмо администратору при регистрации через uLogin;  
**Сохранять ссылку на страницу пользователя в соцсети:** установите флажок, если необходимо сохранять ссылку на страницу пользователя в соцсети при регистрации через uLogin;  
**Группа клиентов по умолчанию:** группа, присваиваемая пользователям, зарегистрированных с помощью uLogin. По умолчанию "Зарегистрированные пользователи";  

#### Компонент *Ulogin_sync*:
Настройки:

**ulogin ID для панели синхронизации №1:** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);
**ulogin ID для панели синхронизации №2:** дополнительное общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);

Более детальную информацию смотрите на сайте [uLogin](https://ulogin.ru/help.php "Помощь")

## Настройки виджета uLogin

При установке расширения uLogin авторизация пользователей будет осуществляться с настройками по умолчанию.
Для более детальной настройки виджетов uLogin Вы можете воспользоваться сервисом uLogin.

Вы можете создать свой виджет uLogin и редактировать его самостоятельно:

для создания виджета необходимо зайти в Личный Кабинет (ЛК) на сайте [uLogin](http://ulogin.ru/lk.php "Личный Кабинет")
добавить свой сайт к списку Мои сайты и на вкладке Виджеты добавить новый виджет. После этого вы можете отредактировать свой виджет.

В графе «Возвращаемые поля профиля пользователя» вы можете включить поля, например, **Пол** и **Дата рождения**.

**Важно!** Для успешной работы плагина необходимо включить в обязательных полях профиля поле **Еmail** в Личном кабинете uLogin.
Заполнять поля в графе «Тип авторизации» не нужно, т.к. расширение uLogin настроено на автоматическое заполнение данных параметров.

Созданный в Личном Кабинете виджет имеет параметры **uLogin ID**.
Скопируйте значение **uLogin ID** вашего виджета в соответствующее поле в настройках плагина на вашем сайте и сохраните настройки.

Если всё было сделано правильно, виджет изменится согласно вашим настройкам.


## Особенности

Для вывода панели *авторизации* в любом месте шаблона темы 1C Bitrix используйте визуальный редактор страницы,
и просто перетащите Служебный Компонент *Ulogin* в то место, куда ходите установить панель авторизации.


Для вывода панели *синхронизации* в любом месте шаблона темы 1C Bitrix используйте визуальный редактор страницы,
и просто перетащите Служебный Компонент *Ulogin_sync* в то место, куда ходите установить панель синхронизации, например, в профиль пользователя.

Для использования панели авторизации в редакторе php-кода 1C Bitrix используйте код:  
				`<?php
   					$APPLICATION->IncludeComponent(
  					"ulogin:auth",
					"",
  					Array(
						"PROVIDERS" => "vkontakte,odnoklassniki,mailru,facebook",
						"HIDDEN" => "other",
						"TYPE" => "small",
						"SEND_MAIL" => "N",
						"SOCIAL_LINK" => "Y",
						"GROUP_ID" => array("5"),
						"ULOGINID1" => "",
						"ULOGINID2" => ""
					));
				?>`


## Изменения

#### 2.1.6.
 - Добавлено сохранение nickname пользователя в поле SECOND_NAME

#### 2.1.5.
 - Исправление ошибок предыдущих версий

#### 2.1.2.
 - Исправление инициализации виджета при динамическом добавлении его на страницу

#### 2.1.1.
 - Изменение логики uloginGetCurrentPageUrl на рекомендованное документацией битрикс

#### 2.1.0.
 - Добавлена опция "Использовать email в качестве логина" в настройках компонента

#### 2.0.9.
 - Улучшена функция генерации redirect_uri, теперь учитываются все компоненты адреса.

#### 2.0.8.
 - Исправлена ошибка с присвоением группы новым пользователям

#### 2.0.7.
 - Исправлена ошибка с подключением файла Ulogin.class.php

#### 2.0.4.
 - Исправлена ошибка с подключением файла Ulogin.class.php

#### 2.0.3.
 - Исправлена ошибка с именем базы данных uLogin_users

#### 2.0.2.
 - Улучшена совместимость со старой версией плагина.
 - Улучшена совместимость с кодировками.

#### 2.0.1.
 - В архив на GitHub добавлены все файлы модуля;
 - Добавлена настройка плагина: сохранение ссылки на соц.профиль в поле PERSONAL_WWW
 - Исправлен баг, когда данные о пользователе не записывались в базу.
 - Добавлено заполнение дополнительной информации о пользователе: телефон, город, страна.
 - Атрибут id панели виджета заменён на class;

#### 2.0.0.
 - Полное изменение логики модуля;
 - Функционал модуля вынесен в отдельный класс ulogin;
 - Исправлена ошибка дублирования аккаунта пользователя;
 - Исправлена ошибка c отсутствием параметров по умолчанию;
 - Добавлено создание и использование таблицы ulogin_users;
 - Рефакторинг кода;

### 1.0.14.
 - Сохранения имён пользователей uLogin в кодировке сайта.

### 1.0.13.
 - Добавлена обработка ошибки при получении данных пользователя с помощью токена от uLogin.

### 1.0.12.
 - Баг фикс.

### 1.0.11.
 - Добавлены изменения в свойства компонента Ulogin:auth.

### 1.0.9.
 - Добавлен компонент привязки социальных сетей, предоставляемых uLogin, к текущему профилю.

### 1.0.7.
 - В свойствах компонента добавлено: -Вкл\выкл уникальности email; -Вкл\выкл отправки уведомлений о новом пользователе.

### 1.0.5.
 - Добавлена возможность выбрать id группы, в которую должен будет попадать пользователь.

### 1.0.3.
 - В этой версии пользователи автоматически попадают в группу "зарегистрированные пользователи".

#### 1.0.0.
*В свойствах компонента добавлено:
 - Вкл\выкл уникальности email;
 - Вкл\выкл отправки уведомлений о новом пользователе;
 - Добавлен компонент привязки социальных сетей, предоставляемых uLogin, к текущему профилю;
 - Добавлены минорные изменения в свойствах компонента Ulogin:auth;
 - Добавлена обработка ошибки при получении данных пользователя с помощью токена от uLogin;
 - Добавлена конвертация имен пользователей в кодировку сайта.
  
*Исправлена ошибка создания аккаунта пользователя.
	
