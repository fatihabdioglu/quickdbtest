# QuickTestDb
## Dockerfile
### This Dockerfile sets up an Ubuntu 20.04 environment and installs the necessary dependencies to run a PHP script that accesses a Microsoft SQL Server database. The following steps are performed:
* Update the package list and install curl and software-properties-common.
* Add the Ondrej PHP PPA repository and install PHP 8.1, along with some required extensions.
* Install the Microsoft ODBC driver and tools, as well as unixodbc-dev.
* Install the PHP drivers for Microsoft SQL Server using pecl.
* Install Apache and libapache2-mod-php8.1.
* Copy a PHP script to the root folder of Apache2.
* Set the APACHE_ENVVARS environment variable and run Apache2 Server.

## docker-compose
* This docker-compose file contains two services: database and myapp.
* The database service uses the mcr.microsoft.com/mssql/server:2022-latest image, sets the environment variables ACCEPT_EULA, MSSQL_SA_PASSWORD, and MSSQL_PID, and maps the container port 1433 to the host port 1433.
* The myapp service builds a Docker image from the ./php-mssql-apache2/ directory, sets the container name to myapp, always restarts the container, depends on the database service, and maps the container port 80 to the host port 80.

![alt text](./test.png)
