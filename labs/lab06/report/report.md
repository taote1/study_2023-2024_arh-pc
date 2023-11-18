---
## Front matter
title: "ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ № 6"
subtitle: "дисциплина:	Архитектура компьютера"
author: "Мантуров Татархан Бесланович"

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

Научиться писать и анализировать ассемблерный код с арифметическими операциями и понять синтаксис. Работа поможет развить навыки низкоуровневого программирования и понимания работы процессора.

# Задание

Написать несколько программ для вычислений.

# Выполнение лабораторной работы
## Порядок выполнения лабораторной работы

Создайте каталог для программ лабораторной работы № 6, перейдите в него и создайте файл lab6-1.asm
<p align="center">![Создаём каталог](image/photo1700324020.jpeg){#fig:001 width=70%}</p>

Рассмотрим примеры программ вывода символьных и численных значений. Программы будут выводить значения записанные в регистр eax
<p align="center">![заполняем программу](image/photo1700324419.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700324224.jpeg){#fig:001 width=70%}</p>

Изменим текст программы и вместо символов, запишем в регистры числа.
<p align="center">![подмена](image/photo1700315200.jpeg){#fig:001 width=70%}</p>
<p align="center">![резульат](image/photo1700324744.jpeg){#fig:001 width=70%}</p>

Преобразуем текст программы из Листинга 6.1 с использованием этих функций.
<p align="center">![заполняем](image/photo1700327103.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700324744.jpeg){#fig:001 width=70%}</p>

Изменим символы на числа
<p align="center">![подмена](image/photo1700327103.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700327448.jpeg){#fig:001 width=70%}</p>

В качестве примера выполнения арифметических операций в NASM приведем программу вычисления арифметического выражения f(x) = (5 * 2+ 3)/3
<p align="center">![пишем программу](image/photo1700315623.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700315774.jpeg){#fig:001 width=70%}</p>

Измените текст программы для вычисления выражения f(x) = (4 * 6 + 2)/5. Создайте исполняемый файл и проверьте его работу.
<p align="center">![меняем выражение](image/photo1700325744.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700326188.jpeg){#fig:001 width=70%}</p>

рассмотрим программу вычисления варианта задания по номеру студенческого билета
<p align="center">![пишем программу](image/photo1700328931.jpeg){#fig:001 width=70%}</p>
<p align="center">![результат](image/photo1700329020.jpeg){#fig:001 width=70%}</p>

## Ответы на вопросы
1. Строка "moveax.rem" и строка "call sprint" отвечают за вывод на экран сообщения 'Ваш вариант:'.
2. Эти инструкции используются для чтения строки с вводом данных от пользователя. Начальный адрес строки сохраняется в регистре есх, а количество символов в строке (максимальное количество символов, которое может быть считано) сохраняется в регистре edx. Затем вызывается процедура sread, которая выполняет чтение строки.
3. Инструкция "call atoi" используется для преобразования строки в целое число. Она принимает адрес строки в регистре еах и возвращает полученное число в регистре еaх.
Строка "xoredx.edx" обнуляет регистр. edx перед выполнением деления. Строка "movebx,20" загружает значение 20 в регистр ebx. Строка "divebx" выполняет деление регистра еах на значение регистра ebx с сохранением частного в регистре еах и остатка в регистре edx,
5. Остаток от деления записывается в регистр edx.
6. Инструкция "inc edx" используется для увеличения значения в регистре edx на
1. В данном случае, она увеличивает остаток от деления на 1.
1з
7. Строка "moy eax.edx" передает значение остатка от деления в регистр eax. 36 Строка "call iprintLF" вызывает процедуруiprintLF для вывода значения на экран вместе с переводом строки.

## Задание для самостоятельной работы

Написать программу вычисления выражения y = f(x). Программа должна выводить
выражение для вычисления, выводить запрос на ввод значения x, вычислять заданное выражение в зависимости от введенного x, выводить результат вычислений. Создайте исполняемый файл и проверьте его работу для значений x1 и x2 
<p align="center">![](image/photo1700329138.jpeg){#fig:001 width=70%}</p>
<p align="center">![](image/photo1700319695.jpeg){#fig:001 width=70%}</p>
# Выводы

В работе были изучены арифметические операции в языке ассемблера NASM.Был рассмотрен синтаксис и были написаны и проанализированы программы на ассемблере, которые используют арифметические операции для решения различных задач.
