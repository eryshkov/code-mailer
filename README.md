Mailer project on base [Nano Ninja Docker Boilerplate](https://github.com/nanoninja/docker-nginx-php-mysql)

## Use Docker commands

###Composer install
```
docker run --rm -v $(pwd)/web:/app composer install
```

###Create the database & tables
```
docker-compose exec php php ./bin/console doctrine:database:create
docker-compose exec php php ./bin/console doctrine:migrations:migrate
docker-compose exec php php ./bin/console doctrine:fixtures:load
```


### Connecting MySQL from [PDO](http://php.net/manual/en/book.pdo.php)

```php
<?php
    try {
        $dsn = 'mysql:host=mysql;dbname=test;charset=utf8;port=3306';
        $pdo = new PDO($dsn, 'dev', 'dev');
    } catch (PDOException $e) {
        echo $e->getMessage();
    }
?>
```

___

## Help us

All other commands and features at [Nano Ninja github](https://github.com/nanoninja/docker-nginx-php-mysql)