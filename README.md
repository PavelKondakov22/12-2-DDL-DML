# 12-2-DDL-DML  Кондаков Павел  

### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.  

1.2. Создайте учётную запись sys_temp.   

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)  
**Ответ:**  
![alt text](https://github.com/PavelKondakov22/12-2-DDL-DML/blob/main/s1.png)  

1.4. Дайте все права для пользователя sys_temp.   

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)  
**Ответ:**  
![alt text](https://github.com/PavelKondakov22/12-2-DDL-DML/blob/main/s2.png)  
1.6. Переподключитесь к базе данных от имени sys_temp.  
**Ответ:**  
![alt text](https://github.com/PavelKondakov22/12-2-DDL-DML/blob/main/s3.png)
Для смены типа аутентификации с sha2 используйте запрос:   
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';  
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.  

1.7. Восстановите дамп в базу данных.  

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)  
**Ответ:**  
![alt text](https://github.com/PavelKondakov22/12-2-DDL-DML/blob/main/s4.png)  
*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*  
```
sudo su  
apt install mysql-server mysql-client  
mysql –u root –p  
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'password';  
SELECT user FROM mysql.user;  
GRANT ALL PRIVILEGES ON * . * TO 'sys_temp'@'localhost';  
SHOW GRANTS FOR ‘sys_temp’@’localhost’;  
exit  
mysql –u sys_temp –p
wget https://downloads.mysql.com/docs/sakila-db.zip  
apt install unzip  
unzip sakila-db.zip  
mysql -u sys_temp -p  
mysql> CREATE DATABASE `sakila`;  
mysql> SHOW DATABASES;  
mysql> exit  
export DBNAME=sakila  
mysql -u sys_temp -p ${DBNAME} < /home/pavel/sakila-db/sakila-schema.sql  
mysql -u sys_temp -p ${DBNAME} < /home/pavel/sakila-db/sakila-data.sql  
mysql -u sys_temp -p  
mysql> SHOW DATABASES;  
mysql> USE sakila;  
mysql> SHOW TABLES;  
  ```
### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа
customer         | customer_id
```
**Ответ:**  
![alt text](https://github.com/PavelKondakov22/12-2-DDL-DML/blob/main/s5.png)  
