﻿#Инструкция по выполнению домашнего задания

    Сделайте fork репозитория c шаблоном решения к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
    Выполните клонирование этого репозитория к себе на ПК с помощью команды git clone.
    Выполните домашнее задание и заполните у себя локально этот файл README.md:
        впишите вверху название занятия и ваши фамилию и имя;
        в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
        для корректного добавления скриншотов воспользуйтесь инструкцией «Как вставить скриншот в шаблон с решением»;
        при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в инструкции по MarkDown.
    После завершения работы над домашним заданием сделайте коммит (git commit -m "comment") и отправьте его на Github (git push origin).
    Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
    Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.
Легенда

### Заказчик передал вам файл в формате Excel, в котором сформирован отчёт.

На основе этого отчёта нужно выполнить следующие задания.
Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

    какие данные хранятся в этих таблицах;
    какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

#### Получилось вот такие таблицы:
ФИО - VARCHAr(100)
Оклад - integer
структурное подразделение- VARCHAr(100)
адрес - VARCHAr(100)
проект - VARCHAr(100)
дата примема DATE
тип подразделения - VARCHAr(100)

### Описал сразу для PG, по сути имеем 3 типа данных, символьные, целочисленный и дата.

Приведите решение к следующему виду:

Сотрудники (

    идентификатор, первичный ключ, serial,
    фамилия varchar(50),
    ...
    идентификатор структурного подразделения, внешний ключ, integer).





1. Таблица "Должности":
* ID_должности (первичный ключ)
* Наименование_должности
* Оклад

Связь с таблицей "Сотрудники":
 ID_должности из таблицы "Сотрудники" будет внешним ключом, связанным с ID_должности из таблицы "Должности".

2. Таблица "Типы подразделений":
* ID_типа_подразделения (первичный ключ)
* Наименование_типа_подразделения

Связь с таблицей "Сотрудники":
 ID_типа_подразделения из таблицы "Сотрудники" может быть внешним ключом, связанным с ID_типа_подразделения из таблицы "Типы подразделений".

3. Таблица "Структурные подразделения":
* ID_подразделения (первичный ключ)
* Наименование_подразделения

Связь с таблицей "Сотрудники":
 ID_подразделения из таблицы "Сотрудники" будет внешним ключом, связанным с ID_подразделения из таблицы "Структурные подразделения".

4. Таблица "Проекты":
* ID_проекта (первичный ключ)
* Наименование_проекта

Связь с таблицей "Сотрудники":
 ID_проекта из таблицы "Сотрудники" будет внешним ключом, связанным с ID_проекта из таблицы "Проекты".

5. Таблица "Адреса филиалов":
* ID_адреса (первичный ключ)
* Наименование_адреса (или другие поля, описывающие адрес)

Связь с таблицей "Сотрудники":
  ID_адреса из таблицы "Сотрудники" может быть внешним ключом, связанным с ID_адреса из таблицы "Адреса филиалов".

6. Таблица "Даты найма":
* ID_даты (первичный ключ)
* Дата_найма

Связь с таблицей "Сотрудники":
  ID_даты из таблицы "Сотрудники" может быть внешним ключом, связанным с ID_даты из таблицы "Даты найма".

7.Таблица "Сотрудники":
* ID_сотрудника
* ФИО сотрудника
* Дата найма
* Адрес филиала
* ID_должности (внешний ключ на таблицу "Должности")
* ID_подразделения (внешний ключ на таблицу "Структурные_подразделения")
* ID_проекта (внешний ключ на таблицу "Проекты")









