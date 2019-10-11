# Лабораторная №2 (`WW_strings`)

## Содержание
1. [Содержание](#содержание)
1. [Задание](#задание)
1. [Требования к корректности решения](#требования-к-корректности-решения)
    1. [Стандартные требования](#стандартные-требования)
    1. [Прочие требования](#прочие-требования)
    1. [Структура репозитория](#структура-репозитория)
1. [Сроки сдачи](#сроки-сдачи)

## Задание
Реализуйте следующие функции в файлах `str.c` и `str.h`, соответствующие стандартным функциям из `<string.h>`:

* `strcpy`
* `strcat`
* `strcmp`
* `strlen`

Точные сигнатуры функций возьмите из стандарта языка Си: [C11](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1256.pdf).
Он большой, но читать целиком не надо, достаточно найти описание функций.
Под словом «string» обычно подразумевается строка в стиле Си (с замыкающим нулём).
Ключевые слова `const` и `restrict` пока можно игнорировать, равно как и не требуется
ничего специального делать для случая неопределённого поведения (на то оно и неопределённое).

Имена реализованных функций должны иметь вид `my_xxx`, где «xxx» - имя стандартной функции. Так, например, поведение стандартной функции `strcpy` должно быть реализовано в функции с именем `my_strcpy`.

В отдельных файлах `test_str.c` и `test_str.h` реализуйте хотя бы один автоматический тест
для каждой из функций выше.
Автоматический тест — это функция, которая делает несколько вызовов тестируемой функции
и, если та работает правильно, ничего не делает, а если неправильно — роняет программу
(можно ещё вывести сообщение об ошибке, но необязательно).
Например, функция `test_strcpy` может запустить `strcpy` на пустой строчке и упасть
по `assert`, если на выходе строчка получилась непустая.

Ключевое отличие от обычных тестов — для проверки автоматических тестов их можно просто
запустить и проверить, что программа не упала, не надо читать ни исходный код, ни
вывод программы.
Например, функция, которая просто выводит на экран длину строчки по мнению `strlen`, автоматическим
тестом не является, потому что эту длину надо проверять глазами.

В файле `test.c` реализуйте `main()` с вызовом всех автоматических тестов.
Таким образом при запуске исполняемого файла `lab_02` должны проверяться все ваши функции из пункта 1.

## Требования к корректности решения
### Стандартные требования
Эти требования будут обычно применяться ко всем будущим домашним заданиям
и лабораторным.

* Действуют все требования корректности из первой лабораторной к поведению `Makefile`,
  но с изменением имён:
  * Папка и исполняемый файл должны называться в соответствии с номером лабораторной: `lab_02` и `lab_02`, соответственно
    (в первой лабе было `lab_01/correct` и `lab01`).
  * Папка для объектных файлов — не `bin`, а `obj`.
* Действуют все требования корректности из первой лабораторной к `.h`-файлам.
* В заголовочных файлах необходимо использовать include guards.
* Включение заголовочных файлов (`*.h`) должно производиться командой
  вроде `#include "str.h"`, не `#include "../include/str.h"`.
* Автоматические тесты не должны требовать _никакой_ дополнительной проверки глазами.
* Ваше реализация должна проходить ваши автоматические тесты.
* Должна существовать реализация задания, при которой ваши автоматические тесты не проходят или приводят к UB.

### Прочие требования
* Ключевые слова `const` и `restrict` можно игнорировать, но надо оставить в сигнатурах функций и в объявлениях, и в определениях.
* При реализации функций `str*`:
   * Запрещается использовать `[]`.
   * Запрещается использовать функции стандартной библиотеки, используйте только средства языка.
   * Разрешается творить жесть с арифметикой указателей вроде `while (*s++)`, даже если это
     вредит читаемости.
     В следующих заданиях такого не будет: развлекайтесь, пока есть возможность!
     Приоритеты операторов и такой синтаксис полезно знать и прочувствовать руками.
* В тестовых функциях и `main` жуткую арифметику использовать не надо, пишите лучше
  понятный код.

### Структура репозитория
```
<корень-личного-репозитория>
|--lab_02
   |--include
   |  |-- str.h
   |  |-- test_str.h
   |--src
   |  |-- str.c
   |  |-- test_str.c
   |  |-- test.c
   |--Makefile
```

Папку `obj`, объектные и исполняемые файлы класть в репозиторий не разрешается.

## Сроки сдачи

Задание выдано 23.09.2019 (понедельник).
Крайний срок сдачи — 02.10.2019 (среда) 22:59 по Москве.
Первая попытка — 28.09.2019 (суббота) 22:59 по Москве. Рекомендуется ей воспользоваться, чтобы вы могли в случае чего исправить замечания и получить баллы.
