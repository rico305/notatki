# BAZY DANYCH

## Praca na bazie dancyh
Wyświetlanie listy baz: `show databases;`<br>
Wybieranie tabeli użytkowej: `use 'name';`

## Tworzenie
Tworzenie bazy danych: `create database 'database_name';`<br>
Tworzenie tabeli: `create table 'table_name' (column1 datatype(size), column2 datatype(size), ...);`<br>
Tworzenie klucza głównego: `create table 'table_name (primary_key_name int primary key auto_increment);`

## Usuwanie
Usuwanie tabeli: `drop table 'table_name'`;

## Praca na tabeli
Wyświetlanie informacji o tabeli: `desc 'table_name';`<br>

### Dodawanie rekordów do tabeli:
- `insert into 'table_name' values (value1, value2, value3);`
- `insert into 'table_name'(column1, column2, column3) values (value1, value2, value3);` 

### Pobieranie rekordów z tabeli:
Wybieranie wszystkich danych: `select * from 'table_name';`<br>
Wybieranie konkretnych danych: `select column1, column2 from 'table_name';`<br>
Wybieranie warunkowe danych: `select column1, column2 from 'table_name' where column_name =/>/< value and/or ...`<br>

### Usuwanie rekordów z tabeli:
Usuwanie: `delete from 'table_name' where column_name=value and/or ...`<br>
Najlepiej do usuwania używać klucza głównego.
