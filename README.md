# Домашнее задание к занятию "`Заббикс 1"`" - `Корниенко Сергей`


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




   1.[Админка заббикс](https://drive.google.com/file/d/14MayiSTu4IwfNhLYSxni1RRhnyv3AdIW/view?usp=drive_link)
   2.wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
     dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
     apt update 
     apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
     sudo -u postgres createuser --pwprompt zabbix
     sudo -u postgres createdb -O zabbix zabbix 
     zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
     sudo nano /etc/zabbix/zabbix_server.conf
     sudo systemctl restart zabbix-server zabbix-agent apache2
     sudo systemctl enable zabbix-server zabbix-agent apache2 

### Задание 2
    1.[Хосты](https://drive.google.com/file/d/1I2OoF-DLuwXcUix-3vm2kzmmxFNXeEE3/view?usp=drive_link)
    2.[Агенты](https://drive.google.com/file/d/1thkNRLy_Rp3vNBtusH202BdOHbmS0R7n/view?usp=drive_link)
    3.[Latest data](https://drive.google.com/file/d/1I2OoF-DLuwXcUix-3vm2kzmmxFNXeEE3/view?usp=drive_link)
    4.[коммит](https://drive.google.com/file/d/1e0nlhTHAvawElPPOCVULipZ2WOUySWJQ/view?usp=drive_link)
