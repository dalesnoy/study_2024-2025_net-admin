---
## Front matter
title: "Laboratory work report №5


administration of local systems"


subtitle: "Конфигурирование VLAN"
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

Получить основные навыки по настройке VLAN на коммутаторах сети.

# Выполнение лабораторной работы

Для начала, откроем проект с названием lab04.pkt и сохраним его под названием lab05.pkt. После чего открываем его для дальнейшего редактирования.


![Открываем проект lab05](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 195928.png){ #fig:001 }

# Настройка Trunk-портов 

Используя приведенную в лабораторной работе последовательность команд из примера по конфигурации Trunk-порта на интерфейсе g0/1 коммутатора msk-donskaya-sw-1, настроим Trunk-порты на соответствующих интерфейсах.

![Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 200318.png)

# Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-2


![Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-2](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 201810.png "Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-2")


# Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-3

![Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-3](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 202052.png)

# Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-4
![Настройка Trunk-портов на коммутаторе msk-donskaya-ddlesnukhin-sw-4](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 202206.png)

# Настройка Trunk-портов на коммутаторе msk-pavlovskaya-ddlesnukhin-sw-1
![Настройка Trunk-портов на коммутаторе msk-pavlovskaya-ddlesnukhin-sw-1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 202345.png)


# Настройка коммутатора msk-donskaya-ddlesnukhin-sw-1 как vtp - сервер

![Настройка коммутатора msk-pavlovskaya-sw-1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 202638.png)


# Теперь настроим остальные коммутаторы как VTP - клиенты и на интерфейсах укажем принадлежность

![1](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 202857.png)

# 2

![2](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 203059.png)

# 3

![3](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 203332.png)

# 4
![4](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 203332.png)

# 5

![5](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 203527.png)

# Изменение IP - адреса

Затем требуется указать статические IP-адреса на оконечных устройствах

![Ip - адрес file](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 203803.png)

# Изменение Ip - адреса web

![Ip - адрес web](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 204004.png "Ip - адрес web")

# Изменение Ip - адреса mail
![Ip - адрес mail](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 204034.png)

# Проверка доступности устройств

После указания статических IP-адресов на оконечных устройствах проверим с помощью команды ping доступность устройств, принадлежащих одному VLAN, и недоступность устройств, принадлежащих разным VLAN

![Проверка на доступность](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab05\screenshots\Снимок экрана 2025-03-13 204529.png)



# Вывод
В ходе выполнения лабораторной работы мы получили основные навыки по настройке VLAN на коммутаторах сети.





