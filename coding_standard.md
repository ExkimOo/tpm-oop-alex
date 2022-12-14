# Coding Standard PEP8
## Внешний вид кода
### Отступы
Используйте 4 пробела на каждый уровень отступа.
### Табуляция или пробелы?
Пробелы - самый предпочтительный метод отступов.
### Максимальная длина строки
Ограничьте длину строки максимум 79 символами.

Для более длинных блоков текста с меньшими структурными ограничениями (строки документации или комментарии), длину строки следует ограничить 72 символами.

Ограничение необходимой ширины окна редактора позволяет иметь несколько открытых файлов бок о бок, и хорошо работает при использовании инструментов анализа кода, которые предоставляют две версии в соседних столбцах.

### Пустые строки   
Отделяйте функции верхнего уровня и определения классов двумя пустыми строками.

Определения методов внутри класса разделяются одной пустой строкой.

Дополнительные пустые строки возможно использовать для разделения различных групп похожих функций. Пустые строки могут быть опущены между несколькими связанными однострочниками (например, набор фиктивных реализаций).

Используйте пустые строки в функциях, чтобы указать логические разделы.

### Импорты
Каждый импорт, как правило, должен быть на отдельной строке.

Правильно:

    import os
    import sys
Неправильно:

    import sys, os
В то же время, можно писать так:

    from subprocess import Popen, PIPE
Импорты всегда помещаются в начале файла, сразу после комментариев к модулю и строк документации, и перед объявлением констант.

Импорты должны быть сгруппированы в следующем порядке:

1. импорты из стандартной библиотеки
2. импорты сторонних библиотек
3. импорты модулей текущего проекта
Вставляйте пустую строку между каждой группой импортов.

## Пробелы в выражениях и инструкциях
### Избегайте использования пробелов в следующих ситуациях:
Непосредственно внутри круглых, квадратных или фигурных скобок.

Правильно:

    spam(ham[1], {eggs: 2})
Неправильно:

    spam( ham[ 1 ], { eggs: 2 } )
Непосредственно перед запятой, точкой с запятой или двоеточием:

Правильно:

    if x == 4: print(x, y); x, y = y, x
Неправильно:

    if x == 4 : print(x , y) ; x , y = y , x
Сразу перед открывающей скобкой, после которой начинается список аргументов при вызове функции:

Правильно:

    spam(1)
Неправильно:

    spam (1)
Сразу перед открывающей скобкой, после которой следует индекс или срез:

Правильно:

    dict['key'] = list[index]
Неправильно:

    dict ['key'] = list [index]
Использование более одного пробела вокруг оператора присваивания (или любого другого) для того, чтобы выровнять его с другим:

Правильно:

    x = 1
    y = 2
    long_variable = 3
Неправильно:

    x             = 1
    y             = 2
    long_variable = 3

## Комментарии
Комментарии, противоречащие коду, хуже, чем отсутствие комментариев. Всегда исправляйте комментарии, если меняете код!

Комментарии должны являться законченными предложениями. Если комментарий — фраза или предложение, первое слово должно быть написано с большой буквы, если только это не имя переменной, которая начинается с маленькой буквы (никогда не изменяйте регистр переменной!).

Если комментарий короткий, можно опустить точку в конце предложения. Блок комментариев обычно состоит из одного или более абзацев, составленных из полноценных предложений, поэтому каждое предложение должно оканчиваться точкой.

Ставьте два пробела после точки в конце предложения.

Комментарии должны быть на английском языке.

### Блоки комментариев
Блок комментариев обычно объясняет код (весь, или только некоторую часть), идущий после блока, и должен иметь тот же отступ, что и сам код. Каждая строчка такого блока должна начинаться с символа # и одного пробела после него (если только сам текст комментария не имеет отступа).

Абзацы внутри блока комментариев разделяются строкой, состоящей из одного символа #.

### "Встрочные" комментарии
Старайтесь реже использовать подобные комментарии.

Такой комментарий находится в той же строке, что и инструкция. "Встрочные" комментарии должны отделяться по крайней мере двумя пробелами от инструкции. Они должны начинаться с символа # и одного пробела.

Комментарии в строке с кодом не нужны и только отвлекают от чтения, если они объясняют очевидное. Не пишите вот так:

    x = x + 1                 # Increment x
Впрочем, такие комментарии иногда полезны:

    x = x + 1                 # Компенсация границы

## Соглашения по именованию
Соглашения по именованию переменных в python немного туманны, поэтому их список никогда не будет полным — тем не менее, ниже мы приводим список рекомендаций, действующих на данный момент. Новые модули и пакеты должны быть написаны согласно этим стандартам, но если в какой-либо уже существующей библиотеке эти правила нарушаются, предпочтительнее писать в едином с ней стиле.

### Имена классов
Имена классов должны обычно следовать соглашению CapWords.

Вместо этого могут использоваться соглашения для именования функций, если интерфейс документирован и используется в основном как функции.

Обратите внимание, что существуют отдельные соглашения о встроенных именах: большинство встроенных имен - одно слово (либо два слитно написанных слова), а соглашение CapWords используется только для именования исключений и встроенных констант.

### Имена исключений
Так как исключения являются классами, к исключениям применяется стиль именования классов. Однако вы можете добавить Error в конце имени (если, конечно, исключение действительно является ошибкой).

### Имена глобальных переменных
Будем надеяться, что глобальные переменные используются только внутри одного модуля. Руководствуйтесь теми же соглашениями, что и для имен функций.

### Имена функций
Имена функций должны состоять из маленьких букв, а слова разделяться символами подчеркивания — это необходимо, чтобы увеличить читабельность.

Стиль mixedCase допускается в тех местах, где уже преобладает такой стиль, для сохранения обратной совместимости.

### Аргументы функций и методов
Всегда используйте self в качестве первого аргумента метода экземпляра объекта.

### Имена методов и переменных экземпляров классов
Используйте тот же стиль, что и для имен функций: имена должны состоять из маленьких букв, а слова разделяться символами подчеркивания.

Используйте один символ подчёркивания перед именем для непубличных методов и атрибутов.

Чтобы избежать конфликтов имен с подклассами, используйте два ведущих подчеркивания.

### Константы
Константы обычно объявляются на уровне модуля и записываются только заглавными буквами, а слова разделяются символами подчеркивания. Например: MAX_OVERFLOW, TOTAL.
