<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

## Шаблон для новых проектов на Laravel

В шаблоне настроен CI для автоматического тестирования пулл реквестов и пушей, а также для исправления стиля кода с помощью php-cs-fixer. 

Также в шаблоне подключена библиотека Laravel Sail для работы с Laravel в Docker. Конфигурация включает в себя mysql, redis и mailhog.

## Установка

Устанавливаем зависимости, создаём файл с переменными окружения и генерируем новый ключ для проекта:

```bash
composer install
cp .env.example .env
php artisan key:generate
```

Если планируется локальная разработка со стандартным сервером и sqlite в роли базы данных, следует в созданном файле **.env** заменить значение DB_CONNECTION с "mysql" на "sqlite" и создать файл **database.sqlite** в директории **database**.

Также для работы с очередями значение QUEUE_CONNECTION следует заменить с "redis" на "sync".

## Docker окружение

Запускаем проект в docker:

```bash
./vendor/bin/sail up -d
```

Для подробной информации как работать с проектом, запущенным в Docker через библиотеку Sail читайте документацию: https://laravel.com/docs/8.x/sail

В docker-окружении доступны MySQL, Redis и Mailhog.

Mailhog предоставляет веб-интерфейс для мониторинга отправляемых электронных писем на порту 8025 в дефолтной конфигурации - http://localhost:8025.
