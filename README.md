# Docker Compose for Omeka S and Neatline 3

1. Clone this repo.

    `git clone https://github.com/scholarslab/neatline-omeka-s-docker.git folderName`

2. Initialize submodules (get Neatline stuff)

   `git submodule update --init --recursive`

   - or if you need to update the contents of the submodules

   `git submodule foreach --recursive git pull origin master`

3. Create a `.env` file for the secrets.

    ```
    MYSQL_ROOT_PASSWORD=SuperSecretRootPassword
    MYSQL_DATABASE=databaseName
    MYSQL_USER=userName
    MYSQL_PASSWORD=userPass
    OMEKA_DB_HOST=omekaS_test_db:3306
    OMEKA_TABLE_PREFIX=prefix_
    ```

4. Create a `database.ini` file to put the secrets into OmekaS

    ```
    user     = "userName"
    password = "userPass"
    dbname   = "databaseName"
    host     = "omekaS_test_db"
    ```

5. Start up docker
  - When using Traefik

    `docker-compose -f traefik.docker-compose.yml up -d`

  - When not using Traefik

    `docker-compose up -d`

6. Viewing the site
  - When using Traefik
    - change your local `/etc/hosts` file to point a domain to your local computer
      ```
      127.0.0.1 testing.neatline.org
      ```
    - Browse to http://testing.neatline.org
  - When not using Traefik
    - Browse to http://localhost:9000
