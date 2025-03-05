# DZ12-01
# Домашнее задание к занятию «Базы данных» Тимохин Вячеслав Витальевич

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания.

---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).



1.	ФИО Сотрудники (Employees)
      Идентификатор (employee_id): PRIMARY KEY, serial.
      Фамилия (lastname): varchar(50).
      Имя (firstname): varchar(50).
      Должность (job_title): varchar(50).
      Тип подразделения (department_type): varchar(50).
      Идентификатор подразделения (department_id): external key, integer.
      Дата найма (hire_date): date.
2.	Структурное подразделение (Departments)
      Идентификатор подразделения (department_id): PRIMARY KEY, serial.
      Название подразделения (department_name): varchar(100).
      Тип подразделения (department_type): varchar(50).
      Структурное подразделение (structural_department): varchar(100).
      Адрес филиала (branch_address): varchar(200).
3.	Проект на который назначен (Projects)
      Идентификатор проекта (project_id): PRIMARY KEY, serial.
      Название проекта (project_name): varchar(100).
      Описание проекта (project_description): text.
      Статус проекта (project_status): varchar(50).
4.	Адрес филиала (Branches)
      Идентификатор филиала (branch_id): PRIMARY KEY, serial.
      Название филиала (branch_name): varchar(100).
      Адрес филиала (branch_address): varchar(200).
5.	Оклад (Salaries)
      Идентификатор заработной платы (salary_id): PRIMARY KEY, serial.
      Идентификатор сотрудника (employee_id): external key, integer.
      Оклад (salary): numeric(10, 2).
6.	Должность (Jobs)
      Идентификатор должности (job_id): PRIMARY KEY, serial.
      Название должности (job_title): varchar(50).
      Описание должности (job_description): text.
7.	Тип подразделения (DepartmentTypes)
      Идентификатор типа подразделения (department_type_id): PRIMARY KEY, serial.
      Название типа подразделения (department_type_name): varchar(50).



## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.


### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
