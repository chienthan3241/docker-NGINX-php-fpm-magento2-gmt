Docker composer running NGINX, PHP, MySQL, PHPMyAdmin all requirements for magento2

## Install pre-requirements
All pre-requirements should be available for your distribution. The most important are :

* [Git](https://git-scm.com/downloads)
* [Docker](https://docs.docker.com/engine/installation/)
* [Docker Compose](https://docs.docker.com/compose/install/)

### Images to use

* [Nginx](https://hub.docker.com/_/nginx/)
* [MySQL](https://hub.docker.com/_/mysql/)
* [PHP](https://hub.docker.com/r/tmchut/php-fpm-magento2/tags/)
* [PHPMyAdmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)

| Server     | Port |
|------------|------|
| MySQL      | 8989 |
| PHPMyAdmin | 8080 |
| Nginx      | 8000 |

You can change the host name by editing the `.env` file.

### Project tree

```sh
.
├── README.md
│── docker
│   └── data
│       ├── db
│       │   └── mysql
│       └── etc
│           ├── nginx
│           │   ├── default.conf
│           │   └── default.sample.conf
│           └── php
│               └── php.ini
│
├── docker-compose.yml
├── .env
├── .gitignore
└── magento
    
```


1. clone the magento2 pack
```sh
cd magento
git clone git@github.com:chienthan3241/magento-fullpakage.git .
cd ..
``` 
2. Start docker
```sh
sudo docker-compose up -d
``` 
3. Server Logs
```sh
sudo docker-compose logs -f # Follow log output
```
3. Stop and clear services
```sh
sudo docker-compose down -v
```

* [http://localhost:8000](http://localhost:8000/) and follow the install wizard
* [http://localhost:8080](http://localhost:8080/) PHPMyAdmin (see `.env` file)