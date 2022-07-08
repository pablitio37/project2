# project2
my darey.io.project 2

# STEP 1 – INSTALLING THE NGINX WEB SERVER

Step 1 – Installing the Nginx Web Server
In order to display web pages to our site visitors, we are going to employ Nginx, a high-performance web server. We’ll use the apt package manager to install this package.

Since this is our first time using apt for this session, start off by updating your server’s package index. Following that, you can use apt install to get Nginx installed:
![project 2 text1](https://user-images.githubusercontent.com/108102087/178061293-07dad3ca-2c87-4f36-8781-a651032feb0f.PNG)


# STEP 2 — INSTALLING MYSQL

![text3](https://user-images.githubusercontent.com/108102087/178069413-d490fc52-6b6a-4d52-965e-8a7e6ab1e7d9.PNG)

i also changed my root password

![text4](https://user-images.githubusercontent.com/108102087/178070888-731713ca-2312-4505-a06d-fd2ce50757b7.PNG)

Mysql is now installed and secured by my new password

# STEP 3 – INSTALLING PHP

Step 3 – Installing PHP
You have Nginx installed to serve your content and MySQL installed to store and manage your data. Now you can install PHP to process code and generate dynamic content for the web server.

While Apache embeds the PHP interpreter in each request, Nginx requires an external program to handle PHP processing and act as a bridge between the PHP interpreter itself and the web server. This allows for a better overall performance in most PHP-based websites, but it requires additional configuration. You’ll need to install php-fpm, which stands for “PHP fastCGI process manager”, and tell Nginx to pass PHP requests to this software for processing. Additionally, you’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. Core PHP packages will automatically be installed as dependencies

To install these 2 packages at once, run

![text5](https://user-images.githubusercontent.com/108102087/178071868-26f9edf1-2b84-4a1f-a04d-6d85dfb438ce.PNG)

Php installed successffully

# STEP 4 — CONFIGURING NGINX TO USE PHP PROCESSOR

When using the Nginx web server, we can create server blocks (similar to virtual hosts in Apache) to encapsulate configuration details and host more than one domain on a single server. In this guide, we will use projectLEMP as an example domain name.

On Ubuntu 20.04, Nginx has one server block enabled by default and is configured to serve documents out of a directory at /var/www/html. While this works well for a single site, it can become difficult to manage if you are hosting multiple sites. Instead of modifying /var/www/html, we’ll create a directory structure within /var/www for the your_domain website, leaving /var/www/html in place as the default directory to be served if a client request does not match any other sites.

![text6](https://user-images.githubusercontent.com/108102087/178072502-47521a5f-2265-4398-9b04-8bc8dd87bf35.PNG)
configuration file in nginx

![text7](https://user-images.githubusercontent.com/108102087/178072935-020f058b-0209-456c-89b2-38f741396ed5.PNG)

configuration file test is successfull

![text8](https://user-images.githubusercontent.com/108102087/178073611-1d18fd76-1d12-4f20-9e38-210ad9635429.PNG)

# STEP 5 – TESTING PHP WITH NGINX

![text9](https://user-images.githubusercontent.com/108102087/178074003-4e7d1d13-dceb-4ad8-83f8-ae23b7489827.PNG)

I was able to access this page in your web browser by visiting the domain name or public IP address i set up in my Nginx configuration file, followed by /info.php:

# STEP 6 – RETRIEVING DATA FROM MYSQL DATABASE WITH PHP (CONTINUED)

Step 6 — Retrieving data from MySQL database with PHP
In this step you will create a test database (DB) with simple "To do list" and configure access to it, so the Nginx website would be able to query data from the DB and display it.

At the time of this writing, the native MySQL PHP library mysqlnd doesn’t support caching_sha2_authentication, the default authentication method for MySQL 8. We’ll need to create a new user with the mysql_native_password authentication method in order to be able to connect to the MySQL database from PHP.

We will create a database named example_database and a user named example_user, but you can replace these names with different values.

First, connect to the MySQL console using the root account:

![text10](https://user-images.githubusercontent.com/108102087/178074819-d831f944-48dc-4aa4-aca5-1e2deae7ae2d.PNG)
Databases

![text11](https://user-images.githubusercontent.com/108102087/178075626-f643fa30-8dc0-44af-b6bf-f932819a7282.PNG)

I was able to access this page in my web browser by visiting the domain name or public IP address configured for my website, followed by /todo_list.php:
