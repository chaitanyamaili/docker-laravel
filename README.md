# docker-laravel
Docker compose laravel 2 tier architecture.

# Steps to follow:
1. docker-compose up -d (To run the docker containers in detached mode)
2. docker-compose exec app composer install (Install packages)
3. docker-compose exec app php artisan config:cache (To clear the php cache)
4. docker-compose exec db bash (To create the user and give access to database)
   1. mysql -uroot -plaravelroot
   2. GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'laravelroot';
   3. FLUSH PRIVILEGES;
   4. exit; (To exit from the mysql console)
   5. exit (To exit from the bash console)
5. docker-compose exec app php artisan migrate (To migrate the table structure)
6. Open the browser and type "http://localhost/" in the url.
7. Type the task to [Add](screenshots/AddTask.png?raw=true "Add Task screen").
8. [List task](screenshots/ListTask.png?raw=true "List task screen").