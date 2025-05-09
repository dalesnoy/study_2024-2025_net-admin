---
## Front matter
title: "Laboratory work report №7


administration of local systems"


subtitle: "Учёт физических параметров сети"
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

Получить навыки работы с физической рабочей областью Packet Tracer, а также учесть физические параметры сети.

# Выполнение лабораторной работы

Для начала, откроем проект с названием lab06.pkt и сохраним его под названием lab07.pkt. После чего открываем его для дальнейшего редактирования.


![Открываем проект lab07](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 224318.png){ #fig:001 }

# Перейдем в физическую область 

В физической рабочей области присвоим название городу - Moscow

![Присвоение названия городу](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 224415.png)


# Новые здания

Щелкнув на изображение города, мы видим здание. Присвоим ему название Donskaya и создадим еще одно под названием Pavlovskaya.

![Добавление нового здания](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 224816.png "Добавление нового здания")

Щёлкнув на изображение здания Donskaya, переместим изображение, обозначающее серверное помещение, в него

# Переместим серверное помещение

Нам необходимо переместить серверное помещение внутрь здания


![Перемещение серверного здания](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 224908.png)




# Серверные стойки

Щелкнув на изображение серверной, мы видим отображение серверных стоек. Переместим коммутатор msk-pavlovskaya-ddlesnukhin-sw-1 и два оконченных устройства dk-pavlovskaya-1 и other-pavlovkaya-1 на территорию Pavlovskaya.


![Перемещение коммутатора и оконченных устройств](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 225811.png)


# 


![Перемещение оконченных устройств](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 225953.png)



# Проверка работоспособности
Вернувшись в логическую рабочую область, пропингуем с коммутатора donskaya коммутатор pavlovkaya и убедимся в работоспособности

![Убедимся в работоспособности](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 230339.png)


# Разрешение на учёт физических характеристик среды передачи

Далее в меню “Options”, “Preferences” во вкладке “Interface” активируем разрешение на учёт физических характеристик среды передачи



![Активируем разрешение](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 230421.png)


# Размещение двух территорий

Теперь в физической рабочей области Packet Tracer разместим две территории на расстоянии более 100 м друг от друга

![Размещение двух территорий](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 233642.png)


# Убедимся в работоспособности

Вернувшись в логическую рабочую область, пропингуем с коммутатора donskaya коммутатор pavlovkaya и убедимся в работоспособности
![Ping Pavlovskaya](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 230609.png)


# Изменение логической области

Далее удалим соединение между коммутаторами и добавим два повторителя. Заменим модули на PT-REPEATERNM-1FFE и PT-REPEATER-NM-1CFE

![Логическая область](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 230909.png)

# Изменение модулей

![Изменение модулей](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 230955.png)

Теперь переместим msk-pavlovskaya-ddlesnukhin-mc-1 на территорию Pavlovskata.

#
![Перемещение](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 231830.png)


# Убедимся в работоспособности

Вернувшись в логическую рабочую область, пропингуем с коммутатора donskaya коммутатор pavlovkaya и убедимся в работоспособности

![Убедимся в работоспособности](C:\Users\User\OneDrive\Рабочий стол\Администрирование локальных систем\lab07\screenshots\Снимок экрана 2025-03-29 231956.png)


# Вывод

В ходе выполнения лабораторной работы мы получили навыки работы с физической рабочей областью Packet Tracer, а также научились учитывать физические параметры сети.


# Ответы на контрольные вопросы 
1.     Перечислите возможные среды передачи данных. На какие характеристики среды передачи данных следует обращать внимание при планировании сети? - **Коаксиал, витая пара, оптоволокно, беспроводные. Допустимое расстояние, скорость передачи, реальные физические факторы для беспроводных сетей.**

2.     Перечислите категории витой пары. Чем они отличаются? Какая категория в каких условиях может применяться? - **Существует несколько категорий кабеля «витая пара», которые нумеруются от 1 до 8 и определяют эффективный пропускаемый частотный диапазон Категории отличаются диапазоном частот, строением кабелей, скоростью передачи. Применяются в зависимости от требуемой скорости передачи/века.**

3.     В чем отличие одномодового и многомодового оптоволокна? Какой тип кабеля в каких условиях может применяться? - **В количестве проходящих лучей. Одномодовые — дороже, многомодовые — охватывают меньшее расстояние.**

4.     Какие разъёмы встречаются на патчах оптоволокна? Чем они отличаются? - **SC — высокая скорость и плотность коммутации, ненадежный корпус. ST — меньшая плотность коммутации, надежный корпус. FC — большая сложность коммутации.**

