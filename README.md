Задание 1
---

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

![Снимок14](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/f567a6d8-8b68-4aa3-9a49-4cb2990a6e83)


1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![Снимок15](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/71f75fd5-d4d5-4360-a669-9e6ee299d951)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![Снимок16](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/45983575-8dbe-40ad-9d1e-a77d6222cc89)


1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

![Снимок17](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/9c52bc30-a5d6-4015-aad2-df782e1170d7)


1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![Снимок18](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/1a109fa5-ba7f-479e-89ba-d0e1f5d6d2e1)

![Снимок19](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/972351b2-8a20-49b4-8d6c-52a77bcf725f)


CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'password';

SELECT user FROM mysql.user;

GRANT ALL PRIVILEGES ON * . * TO 'sys_temp'@'localhost';

SHOW GRANTS FOR 'sys_temp'@'localhost';

ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY '1234';

***

Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. 
---

Пример: (скриншот/текст)

Название таблицы | Название первичного ключа
customer         | customer_id

**Ответ:**

![Снимок20](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/9fe92764-7876-48e3-866d-5597decf4fb5)

![Снимок21](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/0ec01a46-9c13-47dc-be38-549aae6a6c57)

***

Дополнительные задания (со звёздочкой*)

Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

Задание 3*
---
3.1. Уберите у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila.

3.2. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

**Ответ:**

до

![Снимок22](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/21c3b31d-4f74-4111-b41f-cca866c01ee3)


После команды revoke insert, update, alter, delete on sakila.* from 'sys_temp'@'localhost';

![Снимок23](https://github.com/AlexanderSchelokov/Working-with-data-DDL-DML--hw/assets/121572590/7a7ea979-46c5-486f-a2e1-8f81c38d4132)


