# BitrixDock
BitrixDock позволяет легко и просто запускать **Bitrix CMS** на **Docker**.

Для ускорения используется **docker-sync**.

## Содержит:
- php7.1
- apache
- mysql 8
- phpmyadmin

## Порядок разработки

- Установите docker
- Установите docker-sync (http://docker-sync.io/)

### Начало работы
- Склонируйте репозиторий bitrixdock
```
git clone https://github.com/barysh/bitrixdock.git
```

- Выполните настройку окружения

```
PHP_VERSION=php71                     # Версия php 

WEB_SERVER_TYPE=apache                # Веб-сервер

MYSQL_DATABASE=bitrix                 # Имя базы данных
MYSQL_USER=bitrix                     # Пользователь базы данных
MYSQL_PASSWORD=123                    # Пароль для доступа к базе данных
MYSQL_ROOT_PASSWORD=123               # Пароль для пользователя root базы данных

INTERFACE=127.0.0.1                   # На данный интерфейс будут проксироваться порты

SITE_PATH=./www/bitrix/testdock.ru    # Фактический путь к директории Вашего сайта
SITE_NAME=testdock.ru                 # Доменное имя сайта

```

- Создайте директорию в **www/bitrix** соответствующую доменному имени сайта

- Переместите в неё нужный файл для развертывания **Bitrix** (bitrixsetup.php / restore.php) из **www/bitrix** и папку **www/bitrix/bitrix**

- Запустите bitrixdock:
```
docker-sync-stack start
```
- или
```
docker-compose up (для запуска без docker-sync)
```