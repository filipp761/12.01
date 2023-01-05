# 12.01 «Базы данных»

Легенда
Заказчик передал вам файл в формате Excel, в котором сформирован отчёт.

На основе этого отчёта нужно выполнить следующие задания.

# Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

какие данные хранятся в этих таблицах;

какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

идентификатор, первичный ключ, serial,

фамилия varchar(50),

...

идентификатор структурного подразделения, внешний ключ, integer).

Дополнительные задания (со звёздочкой*)

Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.
____
**Ответ**

**Таблицы:
1.	Сотрудники (Staff) – ФИО (varchar(50)), дата найма (date)
2.	Должности (Post) – Должность (varchar(50))
3.	Тип подразделения (Type_Devison) – Тип подразделения(varchar(20))
4.	Подразделение (Devision) - Структурное подразделение (varchar(50))
5.	Адреса филиалов (Branch_address) – адрес (varchar(50))
6.	Данные о зарплате сотрудников (Employee_salary) – зарплата (serial)
7.	Проекты (Project) – наименование проекта (varchar())

![alt text](https://github.com/filipp761/12.01/blob/main/schema.png)


# Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
___
**Ответ**

•	Название проекта зависит от первичного ключа ФИО сотрудника

•	Название структурного подразделения зависит от типа подразделения и адреса филиала

•	Зарплата зависит от  ФИО сотрудника

•	Данные сотрудника зависят от должности и подразделения

**Чтобы нормализовать данные необходимо привести данные в таблице как минимум к 3-м нормальным формам, а именно:

•	Значения в каждом столбце, должны быть атомарными, т.е. значения в домене каждого атрибута отношения не является ни списками, ни множествами простых или сложных значений

•	Все столбцы, которые не являются частью ключа, зависят от этого ключа.

•	Значения, входящие в запись и не являющиеся частью ключа этой записи, не принадлежат таблице 
