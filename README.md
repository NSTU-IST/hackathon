# Задача
Разработать REST API для получения расписания занятий.

# Структура базы данных

## auditory 
Кабинеты. В таблице хранится только номер кабинета. Например - **101**. Номер представлен в текстовом виде, т.к. не всегда это число. Номер корпуса указан в отдельной таблице. Поле **NAME** может быть пустой строкой, т.к. не у всех дисциплин указана аудитория.

|Название|Тип|Длина|Беззнаковое|По умолчанию|Описание|
|--------|---|-----|-----------|------------|--------|
|**ID**|INT|10|Да|AUTO_INCREMENT|уникальный идентификатор|
|**NAME**|VARCHAR|200|-|-|название кабинета|
|**ID_CORPUS**|INT|10|Да|-|идентификатор корпуса (внешний ключ на таблицу corpus)|

<details>
  <summary>Индексы</summary>
  
>**ID** - PRIMARY KEY

>**ID_CORPUS** - FOREIGN KEY
</details>

<details>
  <summary>Пример</summary>
  
![auditory](img/auditory.png)
</details>



## corpus 
Учебные корпуса. Номер представлен в текстовом виде, т.к. не всегда это число. Поле **NAME** может быть пустой строкой, т.к. не у всех дисциплин указан корпус.

|Название|Тип|Длина|Беззнаковое|По умолчанию|Описание|
|--------|---|-----|-----------|------------|--------|
|**ID**|INT|10|Да|AUTO_INCREMENT|уникальный идентификатор|
|**NAME**|VARCHAR|200|-|-|номер корпуса|

<details>
  <summary>Индексы</summary>
  
>**ID** - PRIMARY KEY
</details>

<details>
  <summary>Пример</summary>
  
![corpus](img/corpus.png)
</details>



## day 
Названия дней недели. 

|Название|Тип|Длина|Беззнаковое|По умолчанию|Описание|
|--------|---|-----|-----------|------------|--------|
|**ID**|INT|10|Да|-|уникальный идентификатор|
|**NAME**|VARCHAR|50|-|-|название дня недели|
|**SHORT**|VARCHAR|50|-|-|сокращенное название|

<details>
  <summary>Индексы</summary>
  
>**ID** - PRIMARY KEY
</details>

<details>
  <summary>Пример</summary>
  
![day](img/corpus.png)
</details>

