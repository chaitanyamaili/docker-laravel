# docker-laravel
Docker compose laravel.

# Steps to follow:
1. docker-compose up -d
2. docker-compose exec app php artisan config:cache
3. docker-compose exec db bash
   1. mysql -uroot -plaravelroot
   2. GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'laravelroot';
   3. FLUSH PRIVILEGES;
   4. exit;
4. docker-compose exec app php artisan migrate
