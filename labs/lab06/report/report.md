---
## Front matter
title: "ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ № 6"
subtitle: "дисциплина:	Архитектура компьютера"
author: "Лисовская Арина Валерьевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---
# Цель работы

Цель данной лабораторной работы - освоение арифметческих инструкций языка ассемблера NASM.

# Задание

    1.Символьные и численные данные в NASM
    2.Выполнение арифметических операций в NASM
    3.Выполнение заданий для самостоятельной работы

# Выполнение лабораторной работы

## Символьные и численные данные в NASM

С помощью утилиты mkdir создаю директорию, в которой буду создавать файлы с программами для лабораторной работы №6 (рис. [-@fig:001]). Перехожу в созданный каталог с помощью утилиты cd.

<p align="center">![создание директории](image/Снимок экрана от 2023-11-16 13-49-11.png){#fig:001 width=70%}</p>


С помощью утилиты touch создаю файл lab6-1.asm (рис. [-@fig:002]).

<p align="center">![создания файла](image/Снимок экрана от 2023-11-16 13-49-23.png){#fig:002 width=70%}</p>

Копирую в текущий каталог файл in_out.asm с помощью утилиты cp, т.к. он будет использоваться в других программах (рис. [-@fig:003]). 

<p align="center">![создание копии файла](image/Снимок экрана от 2023-11-16 13-54-37.png){#fig:003 width=70%}</p>

Открываю созданный файл lab6-1.asm, вставляю в него программу вывода значения регистра eax (рис. [-@fig:004]). 

<p align="center">![редактирование файла](/image/Снимок экрана от 2023-11-18 00-01-06.png){#fig:004 width=70%}</p>

Создаю исполняемый файл программы и запускаю его (рис. [-@fig:005]). Вывод программы: символ j, потому что программа вывела символ, соответствующий по системе ASCII сумме двоичных кодов символов 4 и 6.

<p align="center">![запуск исполняемого файла](image/Снимок экрана от 2023-11-18 00-00-04.png){#fig:005 width=70%}</p>

Изменяю в тексте программы символы "6" и "4" на цифры 6 и 4 (рис. [-@fig:006]). 

<p align="center">![редактирование файла](image/Снимок экрана от 2023-11-18 00-01-06.png){#fig:006 width=70%}</p>


Создаю новый исполняемый файл программы и запускаю его (рис. [-@fig:007]). Теперь вывелся символ с кодом 10, это символ перевода строки, этот символ не отображается при выводе на экран.

<p align="center">![запуск иссполняемого файла](image/Снимок экрана от 2023-11-18 00-03-23.png){#fig:007 width=70%}</p>

Создаю новый файл lab6-2.asm с помощью утилиты touch (рис. [-@fig:008]).


Ввожу в файл текст другойпрограммы для вывода значения регистра eax (рис. [-@fig:009]). 

<p align="center">![редактирование файла](image/Снимок экрана от 2023-11-18 00-07-58.png){#fig:009 width=70%}</p>

Создаю и запускаю исполняемый файл lab6-2 (рис. [-@fig:010]). Теперь вывод число 106, потому что программа позволяет вывести именно число, а не символ, хотя все еще происходит именно сложение кодов символов "6" и "4" 

<p align="center">![запуск исполняемого файла](image/Снимок экрана от 2023-11-18 00-11-00.png){#fig:010 width=70%}</p>

Заменяю в тексте программы в файле lab6-2.asm символы "6" и "4" на числа 6 и 4 (рис. [-@fig:011]).

<p align="center">![редактирование файла ](image/Снимок экрана от 2023-11-18 00-12-03.png){#fig:011 width=70%}</p>

Создаю и запускаю новый исполняемый файл (рис. [-@fig:012]).. Теперь программа складывает не соответствующие символам коды в системе ASCII, а сами числа, поэтому вывод 10.

<p align="center">![запуск файла](image/Снимок экрана от 2023-11-18 00-14-34.png){#fig:012 width=70%}</p>

Заменяю в тексте программы функцию iprintLF на iprint (рис. [-@fig:013]).

<p align="center">![редактирование файла](image/Снимок экрана от 2023-11-18 00-12-03.png){#fig:013 width=70%}</p>

Создаю и запускаю новый исполняемый файл (рис. [-@fig:014]). Вывод не изменился, потому что символ переноса строки не отображался, когда программа исполнялась с функцией iprintLF, а iprint не добавляет к выводу символ переноса строки, в отличие от iprintLF.

<p align="center">![запуск файла](image/Снимок экрана от 2023-11-18 00-14-34.png){#fig:014 width=70%}</p>

Выполнение арифметических операций в NASM

Создаю файл lab6-3.asm с помощью утилиты touch (рис. [-@fig:015]).

<p align="center">![создание файлов](image/Снимок экрана от 2023-11-18 14-36-19.png){#fig:015 width=70%}</p>

Ввожу в созданный файл текст программы для вычисления значения выражения f(x) =
