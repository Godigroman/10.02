# Домашнее задание к занятию "`Работа с данными (DDL/DML)`" - `Клименко Олег`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![](https://cdn.discordapp.com/attachments/1258765753096863826/1263074800054829087/image.png?ex=6698e993&is=66979813&hm=49461b3832cfc68de0f3befd76746e0da0eafee31469d6561cb0f385eef9dc3e&)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![](https://cdn.discordapp.com/attachments/1258765753096863826/1263075151872786442/image.png?ex=6698e9e7&is=66979867&hm=ffd43128f2b45bd93d9aa4ebce33df9d3920137c6ef39e605f315ee916fb8fd2&)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

```
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

1.6. По ссылке [https://downloads.mysql.com/docs/sakila-db.zip]( https://downloads.mysql.com/docs/sakila-db.zip) скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![](https://cdn.discordapp.com/attachments/1258765753096863826/1263077087258873877/image.png?ex=6698ebb4&is=66979a34&hm=1b2b52bb668865dc1d0760f69344f7e616f377e5e9ed0c405368de1bdcc38a89&)

![](https://cdn.discordapp.com/attachments/1258765753096863826/1263077497025855510/image.png?ex=6698ec16&is=66979a96&hm=7cd9d80d259d8e62f014e715cd7d00514f5e9debd9d24ff370fab2fa9f54cb4a&)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.

```
mysql> CREATE USER 'sys_temp’@‘localhost' IDENTIFIED BY '12345';

mysql> SELECT user FROM mysql.user;

mysql> GRANT ALL PRIVILEGES ON *.* TO ‘sys_temp’@‘localhost';

mysql> SHOW GRANTS FOR sys_temp@localhost;

mysql> ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY ‘12345’;

docker exec -i net-mysql sh -c 'exec mysql -uroot -p"***"' < /Users/oleg/Downloads/oleg-db/oleg-schema.sql 

docker exec -i net-mysql sh -c 'exec mysql -uroot -p"***"' < /Users/oleg/Downloads/oleg-db/oleg-data.sql

mysql> USE oleg;

mysql> SHOW TABLES;
```

---

### Задание 2

Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

```
Название таблицы | Название первичного ключа
customer         | customer_id
```

![](https://cdn.discordapp.com/attachments/1258765753096863826/1263078335685066762/2.png?ex=6698ecde&is=66979b5e&hm=5f09b260f2b0037e0170dd84ac85e734d67c9f796d45a367af503cca341f7e5b&)

---
---
