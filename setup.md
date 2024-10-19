## install astro cli 

1. Install the Astro cli [Link](https://www.astronomer.io/docs/astro/cli/overview)
2. Open a new empty folder and say `astro dev init`-> This will create files and folder, basically sets up the environment.
3. Write the dag inside dags folder- > `weather_etl.py`
4. After that create  `docker-compose.yml` file.
5. Then run `astro dev start` - > Make sure docker-desktop should be running in the background.
`astro dev restart`

Once your project is up and running:
From http://127.0.0.1:8080/ where Airflow is running, go to Admin-> Connections.

    Connection Id : postgres_default
    Connection Type: Postgres
    Host : etl-piepline_f304df-postgres-1  (Where the ETL container is running)
    POSTGRES_USER: postgres
    POSTGRES_PASSWORD: postgres
    POSTGRES_DB: postgres
    Port: 5432 (default)


Make another connection: 
    Connection Id : open_meteo_api
    Connection Type: HTTP
    Host : https://api.open-meteo.com/

If Everthhing works fine, you can verify if the data is present inside postgres or not using PgAdmin or any other tool.

In Pg admin: 
Create a new server connection
    host: localhost
    port:5432
    database: postgres
    username: postgres
    password: postgres

Error Handling through Chatgpt
https://chatgpt.com/share/6713c49e-bdb0-8011-b5f5-90bb06101ad0
