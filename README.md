# docker-laravel ð³

<p align="center">
    <img src="https://user-images.githubusercontent.com/35098175/145682384-0f531ede-96e0-44c3-a35e-32494bd9af42.png" alt="docker-laravel">
</p>

<!-- ###ãã£ã¬ã¯ããª
.
âââ infra
â âââ php
â | âââ Dockerfile
â | âââ php.ini # PHP ã®è¨­å®ãã¡ã¤ã«
â âââ nginx
â | âââ default.conf # nginx ã®è¨­å®ãã¡ã¤ã«
| |
â âââ mysql
â âââ Dockerfile
â âââ my.cnf # MySQL ã®è¨­å®ãã¡ã¤ã«
âââ src # Laravel ãã¤ã³ã¹ãã¼ã«ãããã£ã¬ã¯ããª
âââ docker-compose.yml
âââ README.md -->

## container
laravel éçºç°å¢æ§ç¯

âââ app<br>
âââ web<br>
âââ db<br>


**app container**<br>
- Base image<br>
    - php:8.1-fpm-buster<br>
    - composer:2.2

**web container**<br>
- Base image<br>
    - nginx:1.20-alpine

**db container**<br>
- Base image<br>
    - mysql/mysql-server:8.0


## ç°å¢æ§ç¯æ¹æ³
Laravel ã®ç°å¢ãæ§ç¯ããããã£ã¬ã¯ããªã§ `git clone` ãè¡ãããã©ã«ããä½æããã
docker compose.yml ãã¡ã¤ã«ããããã£ã¬ã¯ããªã§ä»¥ä¸ã®ã³ãã³ããé ã«æã¤

1. `docker compose build` ã³ãã³ãã§ã¤ã¡ã¼ã¸ä½æ
2. `docker compose up -d` ã³ãã³ãã§ã³ã³ãããä½æããããã¯ã°ã©ã¦ã³ãã§å®è¡
3. `docker compoes exec app bash` ã³ãã³ãã§ app ã³ã³ããã«å¥ã
4. `chmod -R 777 storage bootstrap/cache` ã³ãã³ãã§æ¸ãè¾¼ã¿æ¨©éãä»ä¸
5. `composer install` ã³ãã³ãã§ vendor ãã£ã¬ã¯ããªã¸ã©ã¤ãã©ãªç¾¤ãã¤ã³ã¹ãã¼ã«
6. .envãgitã®ç®¡çä¸ã«ãªãçæãããªãã®ã§ã.env.example ã.env ã«ååãå¤æ´ãã
7. `php artisan key:generate` ã³ãã³ãã§ã¢ããªã±ã¼ã·ã§ã³ã­ã¼ãä½æ
8. `php artisan storage:link` ãã³ãã³ãã§ã·ã³ããªãã¯ãªã³ã¯ãå¼µã
9. localhost:8080ã«ã¢ã¯ã»ã¹

ãã¾ã  
`docker compoes exec app bash` ã³ãã³ãã§ app ã³ã³ããã«å¥ãã  
`php artisan migrate` ã³ãã³ããæã¤ã¨ãdb ã¨ã®æ¥ç¶ãç¢ºèªã§ããã  
ã¨ã©ã¼ãåºãå ´åã¯ã  
infraâmysqlâDockerfile ã®ç°å¢å¤æ°ã¨ srcâvendorâ.env ã®ç°å¢å¤æ°ãç­ãããã  
.env ãã¡ã¤ã«ã® DB_HOST ãèªåã® db ã³ã³ããã®ååã¨ç­ãããç¢ºèªãã¦ã¿ã¦ãã ããã