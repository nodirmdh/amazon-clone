# Amazon Clone 

## (Laravel, Vue JS, Inertia JS, Pinia, Tailwind CSS, Stripe)

### Привет

Это собственный онлайн-рынок, как Amazon.
Мощная и масштабируемая платформа электронной коммерции, с использованием Laravel, Vue JS, Pinia, Tailwind CSS, Inertia JS и Stripe.

## Установка


```
composer install 

cp .env.example .env 

php artisan cache:clear 

composer dump-autoload 

php artisan key:generate

composer require laravel/breeze vue --dev

php artisan breeze:install vue --inertia

php artisan serve
```

Создайте БД
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=amazon_clone
DB_USERNAME=root
DB_PASSWORD=
```
Теперь перенесите свою БД
```
php artisan migrate

php artisan db:seed
```

Добавьте детали в **.env**

Теперь запустите эти команду, чтобы запустить проект
```
npm i

npm run dev
```

