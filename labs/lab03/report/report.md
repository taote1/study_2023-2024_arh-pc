---
## Front matter
title: "Отчёт по лабораторной работе №3"
subtitle: "Дисциплина: Архитектура компьютеров"
author: "Мантуров Татархан"

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
lot: true # List of tables
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
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью работы является освоение процедуры оформления отчетов с помощью легковесного
языка разметки Markdown.


# Задание

1. Установка необходимого ПО
2. Заполнение отчета по выполнению лабораторной работы №3 с помощью языка разметки Markdown
3. Выполнение заданий для самостоятельной работы


# Теоретическое введение

Markdown - легковесный язык разметки, созданный с целью обозначения форматирования в простом тексте, 
с максимальным сохранением его читаемости. Markdown поддерживает как встраивание фрагментов кода в 
предложение, так и их размещение между предложениями в виде отдельных огражденных блоков. Огражденные блоки
кода — это простой способ выделить синтаксис для фрагментов кода. Внутритекстовые формулы делаются аналогично 
формулам LaTeX. В Markdown вставить изображение в документ можно с помощью непосредственного указания адреса 
изображения

# Выполнение лабораторной работы

Установка необходимого ПО 
   
  Установка TexLive
  
  Скачиваю TexLive с официального сайта и распаковываю архив ![texlive](image/msg902554170-969197.jpg)
  
Перехожу в папку lab03 ![папка lab03](image/msg902554170-969203.jpg)

Провожу компиляцию шаблона с использованием Makefile. Для этого ввожу команду make ![make](image/photo1697266823.jpeg)


Удалите полученный файлы с использованием Makefile. Для этого введите команду make clean ![make clean](image/photo1697276134.jpeg)

Откройте файл report.md c помощью любого текстового редактора, например gedit ![gedit](image/photo1697276269.jpeg)

Загружаю файлы на Github ![make](image/photo1697276499.jpeg)
# Выводы

В ходе лабораторной работы я освоила процедуры оформления отчетов с помощью легковесного языка разметки Markdown

# Список литературы{.unnumbered}
1. Архитектура ЭВМ
::: {#refs}
:::
