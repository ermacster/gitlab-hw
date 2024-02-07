﻿# Домашнее задание к занятию «Резервное копирование баз данных»

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

### Кейс

Финансовая компания решила увеличить надёжность работы баз данных и их резервного копирования.

Необходимо описать, какие варианты резервного копирования подходят в случаях:

1.1. Необходимо восстанавливать данные в полном объёме за предыдущий день.

#### Создание полного резервного копирования базы данных ежедневно в конце дня. 
#### Некоторые СУБД позволяют вести журнал транзакций, который фиксирует все изменения, внесенные в базу данных. Это позволяет восстанавливать данные на основе журнала транзакций на определенный момент времени
#### например, за предыдущий день.
#### Инкрементное резервное копирование: Если полное резервное копирование нежелательно из-за размера базы данных, вы можете рассмотреть вариант инкрементного резервного копирования, при котором создаются копии только измененных данных с определенного момента до конца дня.
#### Репликация: Еще один способ обеспечения восстановления данных - это использование репликации, когда данные реплицируются на отдельные серверы или в облако. 

1.2. Необходимо восстанавливать данные за час до предполагаемой поломки.

#### Восстановление из бинарных журналов, предварительно их включив. 

#### Восстановление с использованием точки восстановления (PITR): При необходимости восстановить данные на определенный момент времени (например, за час до поломки),  воспользоваться функцией восстановления до точки во времени (PITR) с использованием бинарных журналов, чтобы восстановить состояние базы данных до нужного момента.
#### Так же в базе MySQL со специальным движком INNODB, включается журналирование  и так же можно откатить до поломки.

    

                                   

      
 
### Задание 2. PostgreSQL


2.1. С помощью официальной документации приведите пример команды резервирования данных и восстановления БД (pgdump/pgrestore).

## pg_restore -U username -d dbname backup.dump
## pg_dump -U username -d dbname > backup.sql

Где:
- `-U username`: указывает имя пользователя базы данных PostgreSQL.
- `-d dbname`: указывает имя базы данных, в которую необходимо восстановить данные.
- `backup.dump`: файл резервной копии, из которого производится восстановление.




### Задание 3. MySQL

3.1. С помощью официальной документации приведите пример команды инкрементного резервного копирования базы данных MySQL.

## mysqldump --single-transaction -u username -p dbname > backup.sql


Где:
- `--single-transaction`: Этот параметр гарантирует создание копии данных, отражающей состояние транзакций на момент начала выполнения команды `mysqldump`. Это позволяет избежать блокировки таблиц на время создания резервной копии.
- `-u username`: Указывает имя пользователя базы данных MySQL.
- `-p`: Параметр для запроса пароля пользователя.



