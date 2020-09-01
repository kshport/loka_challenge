# Задание
Предположим, у нас есть код, позволяющий вывести список групп товаров, а также товары, находящиеся в каждой группе. Задача заключается в том, что необходимо добавить к имеющемуся коду функциональность вложенных групп товаров.

В приложенном файле ***test_base.sql*** находится дамп базы данных MySQL, содержащий две таблицы:

1.	**groups** – таблица групп товаров, содержит поля:
    - id – идентификатор группы
    - id_parent – идентификатор «родительской» группы
    - name – название группы
2.	**products** – таблица товаров, содержит  поля:
    - id – идентификатор товара
    - id_group – идентификатор группы товаров
    - name – название товара


Необходимо написать PHP-скрипт, удовлетворяющий следующим требованиям:
1.	При запуске выводит список (ul) групп товаров первого уровня (groups.id_parent=0), название каждой группы является ссылкой, которая вызывает этот же скрипт с GET-параметром “group”, равным id группы. Возле названия должно быть написано общее количество товаров в группе (количество товаров в самой группе и во всех ее подгруппах). Пока не выбрана ни одна группа – также выводится список всех товаров.
2.	При переходе по ссылке (выборе группы товаров первого уровня) – кроме списка групп товаров первого уровня выводится также список всех подгрупп выбранной группы, все имена подгрупп также являются ссылками, и возле названия подгруппы находится количество товаров, содержащихся в этой подгруппе. Также выводятся все товары, отнесенные к выбранной группе (и всем ее подгруппам). 
3.	Количество уровней вложенности групп не ограничено.
4.	Набор используемых технологий ограничен: php, mysql, html. При реализации использование каких-либо библиотек или фреймворков разрешается только для шаблонизации (вывода информации).
5.	Допустимо добавление новых полей в таблицы. Изменять  логику работы или типы полей, удалять поля в любой таблице запрещено в целях сохранения обратной совместимости с имеющимся кодом (предполагаем что он есть). В случае добавления полей для всех вновь добавленных полей необходимо подготовить запрос/скрипт, заполняющий их данными, либо описать словами логику работы такого запроса/скрипта. 
6.	Никакое специальное оформление не требуется, оцениваться будет логика работы с вложенными группами товаров – sql-запросы и код php, реализующий эту логику, а также html код, реализующий вложенные списки.
 
