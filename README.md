ABOLink v.1.02 - Руководство
=======
###### Постоянный адрес документации: [bit.ly/ABOLink](https://bit.ly/ABOLink)

#### Описание
- Скрипт `ABOLink` возвращает HTML код ссылки и баннера для партнерского сайта.
- Использование ссылки и/или баннера на партнерском сайте оговаривается с ведущим **СЕО-специалистом** компании ABO. Так как, может для партнера быть предоставлено только передача HTML кода ссылки или баннера.
- Для каждой страницы партнерского сайта передаются значения ссылки и/или баннера. Также, эти значения могут изменятся на одной странице при каждом ее вызове.
- Полученный  HTML код не имеет стилей, классов (CSS) и прочих атрибутов кроме всплывающей подсказки (alt, title). По желанию партнера, может быть добавлен атрибут `REL` со значением `NOFOLLOW`.
- Кэшировать данные скрипта `ABOLink` более 1 секунды **запрещается**

#### Требования
- **PHP 4 >= 4.3, PHP 5**
- Наличие на сервере библиотеки `php_curl.dll` Описание [libcurl](http://www.php.su/articles/?cat=protocols&page=004)

#### Установка
- Распакуйте архив в корневой директории сайта. Как правило, это папка с именем: `/public_html`, `/www` или с именем домена сайта.
- На странице (в блоке) вывода HTML кода необходимо подключить скрипт ABOLink с помощью PHP конструкции `include()`;
Установите данный код перед выводом HTML кода ссылки или баннера:
```php
<?php
    include("ABOLink/ABOLink.php");
?>
```

#### Вывод данных
- Для вывода ссылки скрипта `ABOLink`, необходимо в блок установить следующий PHP код:
```php
<?php ABOLink('ANCOR'); ?>
```
В ответ на сайт партнера будет возвращено HTML код ссылки. Пример:
```html
<a href="http://abo.ua/instrument/" title="Инструмент" target="_blank">
    Инструмент
</a>
```
- Для вывода банера скрипта `ABOLink`, необходимо в блок установить следующий PHP код:
```php
<?php ABOLink('BANNER'); ?>
```
В ответ на сайт партнера будет возвращено HTML код баннера. Пример:
```html
<a href="http://abo.ua/instrument/" title="Инструмент" target="_blank">
    <img src="http://firepic.org/images/2014-09/05/6pxv59onm2ph.jpg" alt="Инструмент"/>
</a>
```
- Размер картинки баннера и максимальное количество символов ссылки оговаривается с СЕО-специалистом для каждого партнерского сайта.
- Все картинки баннеров хранятся во внешних (облачных) хранилищах.
- Если для партнерского сайта не предусмотрено размещение баннера или ссылки код ABOLink вернет пустоту “ ”.
