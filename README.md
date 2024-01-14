﻿# Домашнее задание к занятию «Базы данных, их типы»

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

### Задание 1. СУБД

### Кейс

Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Приведите ответ в свободной форме.

## 1.1 Для таких задач подойдет реляционная база данных с поддержкой транзакций и ACID-свойств, чтобы гарантировать целостность данных. Примеры таких СУБД включают Microsoft SQL Server, Oracle Database, PostgreSQL, или MySQL

## 1.2 Для проектов с лендингами, где требуется быстрая и гибкая обработка данных, а также для CRM-систем, где необходимо управление клиентской информацией, разумно использовать комбинацию реляционных и NoSQL баз данных.

### Для лендингов, где обычно применяется структурированный и однотипный формат данных, можно использовать реляционную базу данных (SQL), такую как MySQL или PostgreSQL. Эти базы данных хорошо подходят для организации табличной структуры данных, обеспечивают целостность и консистентность информации, а также обладают хорошей производительностью.

### Для CRM, где данные могут быть более гетерогенными и динамичными, и могут включать неструктурированные данные, такие как контактная информация, история взаимодействия с клиентами, почтовая переписка и т.д., лучше всего использовать NoSQL базу данных, например MongoDB или Apache Cassandra. Эти базы данных позволяют хранить и обрабатывать различные типы данных, обеспечивая гибкость и масштабируемость.

### Использование комбинации SQL и NoSQL СУБД позволит обеспечить эффективное хранение и обработку данных как для лендингов, так и для CRM-системы, учитывая требования к гибкости и скорости, необходимым для эффективного управления разнообразными данными и клиентской информацией.

## 1.3 Для создания базы данных по корпоративным нормам и правилам, обучающему материалу и прочему, вам может подойти реляционная СУБД с простой и интуитивно понятной структурой, например, MySQL, PostgreSQL или Microsoft SQL Server.

### Такие СУБД имеют хорошую поддержку стандартных SQL запросов и предоставляют возможность определения четких отношений между данными в соответствии с структурой компании. Вы также можете легко организовать доступ к данным и обеспечить безопасность и целостность информации.

### Таким образом, выбор определенной СУБД будет зависеть от ваших конкретных потребностей, предпочтений и существующей инфраструктуры системы.

# 1.4Для такого запроса подойдет графовая база данных, такая как Neo4j. Графовые базы данных специально разработаны для эффективной работы с данными, связанными между собой, такими как маршруты доставки и связи между объектами и курьерами. Они способны эффективно обрабатывать сложные связи и предоставлять быстрые операции поиска и анализа для таких данных. Графовая структура базы данных также отлично подходит для моделирования сетей маршрутов и визуализации взаимосвязей между объектами и курьерами.


    
    
    

                                   

      
 
### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Приведите ответ в свободной форме.

2.1

## 1. Пользователь вводит свой номер телефона и сумму, которую желает пополнить.

## 2. Пользователь выбирает метод оплаты: кредитная карта, электронный кошелек, банковский перевод и т.д.

## 3. Система проверяет данные пользователя и сумму транзакции на корректность.

## 4. В случае успешной проверки, система формирует запрос на проведение транзакции к платежному шлюзу выбранного метода оплаты.

## 5. Платежный шлюз обрабатывает запрос, взаимодействует с банком или платежной системой, проводит транзакцию и возвращает результат обработки системе.

## 6. Система обновляет баланс счета телефона пользователя, сообщает о успешной транзакции и отправляет уведомление пользователю о пополнении баланса.


### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Приведите ответ в свободной форме.

## 1. Сложные запросы: SQL позволяет эффективно выполнять сложные выборки данных, агрегируя, фильтруя и соединяя данные.


## 2. Жесткая структура данных: SQL базы данных обычно имеют строгую схему, что обеспечивает стабильность и надежность хранения данных.


## 3. Транзакции: SQL обеспечивает поддержку транзакций, позволяющих гарантировать целостность данных при одновременном доступе к ним.


## 4. Надежность и гарантии сохранности данных: SQL-системы обычно имеют устойчивость к отказам и обладают механизмами резервного копирования и восстановления данных.

## 5. Сложные отношения: SQL поддерживает различные типы отношений между данными, такие как связи "один ко многим" и "многие ко многим", обеспечивая более удобную работу с данными, связанными между собой.

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

Приведите ответ в свободной форме.

#При выборе типа СУБД и модели распределенных вычислений для решения задачи обработки больших объемов данных, следует учитывать несколько ключевых критериев:

## 1. Поддержка параллелизма: Каждая из 1000 машин должна иметь возможность выполнять вычисления параллельно. Поэтому нам потребуется СУБД, которая ориентирована на распределенную обработку запросов и данных.

## 2. Масштабируемость: Система должна легко масштабироваться при увеличении количества узлов. Это может потребовать использования распределенной архитектуры, где данные и запросы могут быть равномерно распределены по всем узлам.

## 3. Обработка больших объемов данных: Модель должна обеспечивать эффективную обработку и хранение больших объемов данных, включая возможность работы с параллельными запросами.

Исходя из этих критериев, NoSQL базы данных, такие как Apache Cassandra, могут быть подходящим выбором. NoSQL базы данных обычно хорошо масштабируются горизонтально, что позволяет обрабатывать большие объемы данных и запросов. Распределенная модель вычислений MapReduce, используемая в Apache Hadoop, также может быть эффективной для распределенной обработки данных, так как она позволяет параллельно выполнить вычисления на большом количестве узлов.

Выбор конкретной СУБД и модели вычислений зависит от конкретных требований, архитектуры системы и типов данных, которые будут обрабатываться.

    
   


