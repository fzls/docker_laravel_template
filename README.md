# usage
1. put other files into your project
2. cp docker-compose-custom.yml.example docker-compose-custom.yml
3. fill in db related setting in the new file
4. cp .env.example.{ENV} .env.{ENV}
5. fill in the necessary info in the new file
6. cp .env.{YOUR_CURRENT_ENV} .env // change current env

# deploy
1. git clone your_project
2. cd your_project
3. do steps in #usage {2->6}
4. vim .env ## change into production settings, and password .etc
5. sh dev.sh up -d
6. docker logs -f {DIRECTORY-NAME}_php_1 ## wait for it to install all the settings
7. if first time, then docker exec -it {DIRECTORY-NAME}_php_1 php artisan key:generate
8. if need migrate, then docker exec -it {DIRECTORY-NAME}_php_1 php artisan migrate
