
![dashboard](https://user-images.githubusercontent.com/43060981/194300822-e84f128d-c473-423e-b072-47c68d9f6772.JPG)
![Laravel-и-еще-1-страница-—-Личный_-Microsoft_-Edge-2022-10-06-14-02-09](https://user-images.githubusercontent.com/43060981/194301655-96b2f02d-9e3d-4ff9-8b91-ea42a1a4d518.gif)
## Установка

Laravel:  

    curl -s "https://laravel.build/AmoCRM-to-PostgreSQL" | bash  
    
PostgreSQL: 

    docker run --name postgresdb -p 5432:5432 -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=postgres -d postgres

Ngrock: 

    docker run --net=host -it ngrok/ngrok http 80  

## Страницы  

Главная страница:

    переход на /dashboard и /update

/update 

    обновляет базу данных выгружая данные из amoCRM

/dashboard 

    выводит базу данных без обновления

## Функции DealsController  

oAuthCRMtodb(): 

    подключение к amoCRM

updateOrCreatetodb(): 

    выгрузка из amoCRM в базу данных

store_***(): 

    сохранение данных о модели *** в базу данных

## Ngrok  

ngrok — простейшая утилита для создания туннеля к localhost.

    Туннель необходим так как amoCRM не даёт выбрать localhost как ссылку для перенаправления после авторизации

## Настройки  .env

Параметры БД  

    DB_CONNECTION=pgsql  //база данных PostgreSQL
    DB_HOST=host ip  
    DB_PORT=5432  
    DB_DATABASE=postgres  
    DB_USERNAME=postgres  
    DB_PASSWORD=postgres  

Параметры amoCRM  

    CRM_CLIENT_ID=621ae166-8715-4036-ab18-2b251bd7924d // ID интеграции из интеграции amoCRM  

    CRM_SECRET=8ZAETzthuODhYuAueW8nIeclfr1vaKZ67rIWGEELXq2Xt8tNPqEhrsPTJjA4uwvO // секретный ключ из интеграции amoCRM  

    CRM_URL=ngrock forwarding ip //ссылка для перенаправления из ngrok

## Создание интеграции в amoCRM 

Интеграция создаётся в amoМаркет->меню в правом верхнем углу->+ Создать интеграцию->Внешняя интеграция->Ссылка для перенаправления берем из ngrock
