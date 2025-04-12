---
## Front matter
title: "Laboratory work report №4


administration of local systems"


subtitle: "Первоначальное конфигурирование сети"
author: "Выполнил: Леснухин Даниил Дмитриевич, 


НПИбд-02-22, 1132221553"

## Generic otions
lang: ru-RU


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
mainfont: "Times New Roman"
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

Провести подготовительную работу по первоначальной настройке коммутаторов сети.


# Задание 

Требуется сделать первоначальную настройку коммутаторов сети, представленной на схеме L1 (см. рис. 3.1 из раздела 3.3). Под первоначальной настройкой понимается указание имени устройства, его IP-адреса, настройка доступа по паролю к виртуальным терминалам и консоли, настройка удалённого доступа к устройству по ssh. При выполнении работы необходимо учитывать соглашение об именовании (см. раздел 2.5).



 
# Выполнение лабораторной работы

В логической рабочей области Packet Tracer разместим коммутаторы и оконченные устройства согласно схеме сети L1. Рис.1


![Размещенная топология](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 002040.png){ #fig:001 }

# Таблица IP
![Таблица IP](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 004207.png)




# Настройка коммутаторов
 
Используя типовую конфигурацию коммутатора, настроем все, изменяя название устройства и его IP-адрес. Рис.3, Рис. 4, Рис. 5, Рис. 6, Рис. 7

![Настройка коммутатора msk-pavlovskaya-sw-1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 003232.png)

# msk-donskaya-sw-3

![Настройка коммутатора msk-donskaya-sw-1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 003651.png)

# msk-donskaya-sw-4

![Настройка коммутатора msk-donskaya-sw-4](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 004047.png)


# msk-donskaya-sw-2


![Настройка коммутатора msk-donskaya-sw-2](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 004656.png)

# msk-donskaya-sw-1

![Настройка коммутатора msk-donskaya-sw-3](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab04\screenshots4\Снимок экрана 2025-03-09 005055.png)






# Вывод
 В ходе выполнения лабораторной работы мы провели подготовительную работу по первоначальной настройке коммутаторов сети.


