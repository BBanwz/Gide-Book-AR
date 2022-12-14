Операторы if for while
======================

Условная инструкция if-elif-else (её ещё иногда называют оператором ветвления) - основной инструмент выбора в Python. Проще говоря, она выбирает, какое действие следует выполнить, в зависимости от значения переменных в момент проверки условия.

Синтаксис if
------------
Сначала записывается часть if с условным выражением, далее могут следовать одна или более необязательных частей elif, и, наконец, необязательная часть else. Общая форма записи условной инструкции if выглядит следующим образом:

if test1:
    state1
elif test2:
    state2
else:
    state3

Простой пример (напечатает 'true', так как 1 - истина):

>>> if 1:
... 	print('true')
... else:
... 	print('false')
...
true

Чуть более сложный пример (его результат будет зависеть от того, что ввёл пользователь):
::
    a = int(input())
    if a < -5:
        print('Low')
    elif -5 <= a <= 5:
        print('Mid')
    else:
        print('High')

Конструкция с несколькими elif может также служить отличной заменой конструкции switch - case в других языках программирования.

Проверка истинности в Python
●  	Любое число, не равное 0, или непустой объект - истина.
●  	Числа, равные 0, пустые объекты и значение None - ложь
●  	Операции сравнения применяются к структурам данных рекурсивно
●  	Операции сравнения возвращают True или False
●  	Логические операторы and и or возвращают истинный или ложный объект-операнд

Логические операторы:

X and Y
Истина, если оба значения X и Y истинны.

X or Y
Истина, если хотя бы одно из значений X или Y истинно.

not X
Истина, если X ложно

Трехместное выражение if/else
Следующая инструкция:

if X:
    A = Y
else:
    A = Z

довольно короткая, но, тем не менее, занимает целых 4 строки. Специально для таких случаев и было придумано выражение if/else:
A = Y if X else Z

В данной инструкции интерпретатор выполнит выражение Y, если X истинно, в противном случае выполнится выражение Z.

>>> 
>>> A = 't' if 'spam' else 'f'
>>> A

't'
В этой статье я расскажу о циклах for и while, операторах break и continue, а также о слове else, которое, будучи употребленное с циклом, может сделать программный код несколько более понятным.

Цикл while
----------
While - один из самых универсальных циклов в Python, поэтому довольно медленный. Выполняет тело цикла до тех пор, пока условие цикла истинно.
>>> 
>>> i = 5
>>> while i < 15:
...	print(i)
...	i = i + 2
...

Цикл for
--------
Цикл for уже чуточку сложнее, чуть менее универсальный, но выполняется гораздо быстрее цикла while. Этот цикл проходится по любому итерируемому объекту (например строке или списку), и во время каждого прохода выполняет тело цикла.

>>> 
>>> for i in 'hello world':
...	print(i * 2, end='')
...
hheelllloo  wwoorrlldd

Оператор continue
-----------------
Оператор continue начинает следующий проход цикла, минуя оставшееся тело цикла (for или while)
>>> 
>>> for i in 'hello world':
...	if i == 'o':
...        continue
...	print(i * 2, end='')
...
hheellll  wwrrlldd

Оператор break
--------------
Оператор break досрочно прерывает цикл.

>>> 
>>> for i in 'hello world':
...	if i == 'o':
...        break
...	print(i * 2, end='')
...
hheellll

Волшебное слово else
--------------------
Слово else, примененное в цикле for или while, проверяет, был ли произведен выход из цикла инструкцией break, или же "естественным" образом. Блок инструкций внутри else выполнится только в том случае, если выход из цикла произошел без помощи break.

>>> 
>>> for i in 'hello world':
...	if i == 'a':
...        break
... else:
...	print('Буквы a в строке нет')
...
Буквы a в строке нет
