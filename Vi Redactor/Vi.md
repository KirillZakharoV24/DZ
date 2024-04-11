## Задание 1

1. vi text1

2. :s/h/step/

3. Установить курсор перед тем что нужно удалить в строке и нажать shift+d

4. Переместить курсор в строку после которой хотите вставить другую строку и нажать "о" после чего редактор перенаправит в режим ввода, ввести: //--

5. Переместить курсор на первую строку, которую нужно удалить.
Нажать Shift + V, чтобы перейти в режим выделения строк.
Перемещать вниз или вверх, чтобы выделить нужное количество строк.
Нажмите d, чтобы удалить выделенные строки.

[Скрины](https://github.com/KirillZakharoV24/DZ/tree/main/Vi%20Redactor/Task1)

## Задание 2

1. vi file1.txt
2. Установить курсор в строку с переменной и в командной строке ввести: :s/Proba_start/start
3. Находясь в командном режиме переместить курсор на нужную строку и нажать shift+d
4. Войти в режим выделения строк shift+v, затем выделить нужную строку и нажать shift+p, переместить курсор на строку перед которой нужно вставить строку и нажать shift+p
5. Перейти в режим командной строки и ввести: 14,15 d (где числа это номера строк)

[Скрины](https://github.com/KirillZakharoV24/DZ/tree/main/Vi%20Redactor/Task2)

## Задание 3

1. vi file1
2. Находясь в командном режиме переместить курсор на нужную строку с коментарием и нажать shift+d
3. Переместить курсор в строку которую надо переместить затем нажать shift+v (строка выделяется), затем нажать shift+p (строка вырезается), затем переместить курсор на строку перед которой нужно вставить вырезанную строку и нажать shift+p
4. В командной строке ввести: :%s/green/blue/
5. переместить курсор в строку которую хотим удалить --> shift+v --> выделяем строки которые нужно удалить --> нажимаем клавишу "d".

[Скрины](https://github.com/KirillZakharoV24/DZ/tree/main/Vi%20Redactor/Task3)


## Контрольные вопросы

1. Какие режимы существуют у редактора vi?

- Командный режим (command mode)
- Режим вставки (insert mode)
- Режим командной строки (last line mode)

2. Прокомментируйте диаграмму переключения режимов vi.

Начало работы происходит в командном режиме, в него мы можем вернуться из любого другого режима используя "ESC". 

Переход в режим командной строки осуществляется клавишей ":".

Переход в режим вставки "i".

3. Как получать помощь по использованию vi?

Ввести в командной строке команду __:help__

- Вход в справочную систему. Справочная система организована в виде гиперссылок с использованием тэгов

4. [Команды позиционирования курсора, вставки, изменения, вырезания, вставки и удаления.](https://github.com/KirillZakharoV24/DZ/blob/main/Vi%20Redactor/%D0%A3%D1%80%D0%BE%D0%BA%206%20%D0%A2%D0%B5%D0%BA%D1%81%D1%82%D0%BE%D0%B2%D1%8B%D0%B9%20%D1%80%D0%B5%D0%B4%D0%B0%D0%BA%D1%82%D0%BE%D1%80%20vi.pdf) 