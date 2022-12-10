## documentation of project2-lEMP

`sudo apt update`

`sudo apt install nginx`

`sudo systemctl status nginx`
![nginx running successfuly](nginxrunning.png)

`curl http://localhost:80`
![local access of the nginx server](./local%20view.png)

`http://<Public-IP-Address>:80`
![web browser view ](./welcome.png)

`sudo apt install mysql-server`

`sudo mysql`
![mysql is running](./mysql.png)

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

`exit`

`sudo mysql_secure_installation`
![password validation](./pasword%20validation.png)

`sudo mysql -p`

`exit`

`sudo apt install php-fpm php-mysql`

`sudo mkdir /var/www/projectLEMP`

`sudo chown -R $USER:$USER /var/www/projectLEMP`

`sudo nano /etc/nginx/sites-available/projectLEMP`
![writting on the empty file](./siteavailable.png)

`sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`
`sudo nginx -t`
![testing nginx](./test%20nginx.png)

`sudo unlink /etc/nginx/sites-enabled/default`

`sudo systemctl reload nginx`

`sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`

`http://<Public-IP-Address>:80`
![brower view](hello.png)

`sudo nano /var/www/projectLEMP/info.php`
![write up in the new file](./new-file.png)
![outcome of the php file on browswer](./php-info.png)

`sudo rm /var/www/your_domain/info.php`

`sudo mysql -p`

`CREATE DATABASE `example_database`;`

`CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 
'password';`

`GRANT ALL ON example_database.* TO 'example_user'@'%';`

`mysql -u example_user -p`

`SHOW DATABASES;`

`CREATE TABLE example_database.todo_list (item_id INT AUTO_INCREMENT,
   content VARCHAR(255),
   PRIMARY KEY(item_id) );`

   `INSERT INTO example_database.todo_list (content) VALUES ("My first important item");`

   `SELECT * FROM example_database.todo_list;`
   ![todo_list database created](./todo-list.png)

   `exit`

`nano /var/www/projectLEMP/todo_list.php`

[browswer link](http://<Public_domain_or_IP>/todo_list.php)
![browser view of todo_list](browser_todo.png)




