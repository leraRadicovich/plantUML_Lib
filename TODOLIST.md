sequence/SequenceLib.v3_lite
Тут фиксируются идеи по доработке библиотеки, возникающие в процессе работы с ней
1. Реализовать проксисервис rq и rs. Будет просто пробрасывать цепочку вызов из А в D: a - b, b - c, c- d, при этом будет описан по аналогии с rq
2. Придумать механизм включения и отключения либ, чтобы его можно было перед текстом диаграммы указывать, а не в конце. Вероятно, единственное решение - через легенду. тогда нужно сделать ее склеиваемой из разных блоков.ты@ 
3. ГОТОВО: Реализовать автоrs, который запоминает последнее обращение к этому участнику и вызывает с уже заданными параметрами процедуру rs
4. ГОТОВО: Реализовать список доработок - процедура, которая позволяет оставить заметки к диаграмме, с перечислением моментов для доработки
5. Реализовать ссылки - например, у нас есть действие a - b. Мы понимаем, что оно может повториться - мы берем его идентификатор, размечаем уникальной ссылкой, при вызове в другом месте диаграммы нам нужно просто передать имя ссылки - будет вызвано то же действие
6. ГОТОВО: Доработать процедуру создания легенды с доп информацией: легенда должна быть расширяемой, чтобы при необходимости можно было добавлять раздел, имя раздела, настраиваемую таблицу. За основу для развития взять создание заметки со списком изменений.
7. ГОТОВО: Процесс создания карты процесса переписан - каждая стрелка теперь является уникальной переменной со своим значением, аналогично реализовано формирование таблицы с описанием событий аудита
8. Переписать процедуры aliasToName и partiesMapper - использовать уникальность имени и переменные, сейчас используется общая мапа, которую приходится парсить