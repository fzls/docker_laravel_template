# usage
1. put other files into your project
2. change db settings in docker-compose-common's db service
3. change .env.example setting's db setting

# deploy
1. git clone your_project
2. cd your_project
3. cp .env.example .env
4. vim .env ## change into production settings, and password .etc
5. sh dev.sh up -d
6. docker logs -f {DIRECTORY-NAME}_php_1 ## wait for it to install all the settings
7. if first time, then docker exec -it {DIRECTORY-NAME}_php_1 php artisan key:generate
8. if need migrate, then docker exec -it {DIRECTORY-NAME}_php_1 php artisan migrate
