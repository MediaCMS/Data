# MediaCMS Data [beta]
## Демонстраційні дані

Демностраційні дані включають в себе дамп колекцій MongoDB, \
файли зображення для сервера зображень та дамп даних зображень БД Redis .

Скачайте демонстраційні дані з репозиторію в локальний каталог: \

`git clone https://github.com/MediaCMS/Data.git`

#### Імпорт дампу колекцій MongoDB на сервер БД

Переконайтейсь що у вас вже встановлено MongoDB та утиліта `mongorestore`

Імпортуйте дамп з локального каталогу за допомогою команди

`mongorestore -h localhost:27017 -d mediacms dump/mediacms`

За необхідності додайте параметри логіна та пароля:
`-u user -p password`

#### Імпорт файлів зображень на сервер зображень

Скопіюйте теку `images` в кореневу теку сервера зображень
`сp ./images ../image`

#### Імпорт дампу даних зображень БД Redis на сервер зображень

1. Зупиніть сервер БД Redis: \
`sudo service redis-server stop` 
2. Скопіюйте дамп БД Redis в її службову теку: \
`sudo cp ./dump.rdb /var/lib/redis/dump.rdb`
3. Змініть власника дампу БД Redis: \
`sudo chown redis: /var/lib/redis/dump.rdb`
4. Запустіть сервер БД Redis \
`sudo service redis-server start`