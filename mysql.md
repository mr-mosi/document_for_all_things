## MySql first install

After installing:

- enter this command to open mysql:
`mysql -u root -p` if request password and you do not set password press Enter. if not worked and you see an error enter this command: `sudo mysql -u root -p` most of time works.

- after entering mysql env creation a new user for database is recommended. in this way create it.
 ```
 mysql> USE mysql;

 mysql> CREATE USER 'YOUR_SYSTEM_USER'@'localhost' IDENTIFIED BY '<password>';

 mysql> GRANT ALL PRIVILEGES ON *.* TO 'YOUR_SYSTEM_USER'@'localhost';

mysql> UPDATE user SET plugin='auth_socket' WHERE User='YOUR_SYSTEM_USER';

mysql> FLUSH PRIVILEGES;

mysql> exit;


$ service mysql restart

 ```

 - One of the best way to use mysql is using the mysql workbench the graphical interface of mysql.
	- after installing the proper version, create a new mysql user and set a password for it after that in the mysql workbench connect to mysql server by new user you create.

	