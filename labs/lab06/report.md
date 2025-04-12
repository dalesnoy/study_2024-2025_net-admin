---
## Front matter
title: "Laboratory work report №6


administration of local systems"


subtitle: "Статическая маршрутизация VLAN"
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

Настроить статическую маршрутизацию VLAN в сети.

# Выполнение лабораторной работы

Для начала, откроем проект с названием lab05.pkt и сохраним его под названием lab06.pkt. После чего открываем его для дальнейшего редактирования.


![Открываем проект lab06](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 191114.png){ #fig:001 }

# Подключение маршрутизатора cisco2811 

В логической области проекта разместим маршрутизатор cisco 2811, подключим его к порту 24 коммутатора , msk-donskaya-ddlesnukhin-sw-1.

![Подключение маршрутизатора cisco2811](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 191256.png)


# Конфигурация маршрутизатора

Используя последовательность команд, приведенных в документации по первоначальной настройке маршрутизатора, сконфигурируем его, задава имя, пароль, настроим удаленное подключение.

![Конфигурация маршрутизатора](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 191929.png)

# Настройка порта коммутатора

Теперь настроим порт 24 коммутатора msk-donskaya-ddlesnukhin-sw-1 как trunk порт.


![Настройка порта коммутатора](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 192206.png)




# Изменение имени маршрутизатора

Изменим на схеме наименование маршрутизатора Cisco 2811


![Изменение имени маршрутизатора](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 192251.png)


# Настройка виртуальных интерфейсов

На интерфейсе f0/0 муршрутизатора msk-donskaya-ddlesnukhin-gw-1 настроим виртуальные интерфейсы, соответствующие номерам VLAN.

![Настройка виртуальных интерфейсов](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 192933.png)


# Проверка доступности оконченных устройств

![Проверка доступности оконченных устройств](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab06\screenshots\Снимок экрана 2025-03-21 194249.png)



# Вывод

**Вывод** В ходе выполнения лабораторной работы мы научились настраивать статическую маршрутизацию VLAN в сети.

# Ответы на контрольные вопросы 
**Ответы на контрольные вопросы**
1 Охарактеризуйте стандарт IEEE 802.1Q - открытый стандарт,
который описывает процедуру тегирования трафика для передачи
информации о принадлежности к VLAN по сетям стандарта IEEE
802.3 Ethernet.

2 Опишите формат кадра IEEE 802.1Q - добавляет 32-битное поле

между MAC-адресом источника и полями EtherType исходного

кадра. В соответствии с 802.1Q минимальный размер кадра

остается 64 байта, но мост может увеличить минимальный размер

кадра с 64 до 68 байтов при передаче IEEE 802.1Q.
