---
## Front matter
title: "Laboratory work report №11


administration of local systems"


subtitle: "Настройка NAT. Планирование"
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
**Цель работы:**
Провести подготовительные мероприятия по подключению локальной сети организации к Интернету.

## **Выполнение работы**

 Откроем проект с названием `lab_PT-10.pkt` и сохраним под названием `lab_PT-11.pkt`. После чего откроем его для дальнейшего редактирования.

   ![Открытие проекта lab_PT-10.pkt](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 151234.png)

   
## **Изменение топологии**
На схеме нашего проекта разместим согласно заданию лаб. работы необходимое оборудование для сети провайдера и сети модельного Интернета. После чего соблюдая соглашение об именовании переименуем их.

![ Изменение топологии. Добавление оборудования.](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 154313.png)


## **Физическая область**
В **физической области** добавим здание провайдера и здание, имитирующее расположение серверов модельного интернета.
   
![ Добавление зданий.](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 160742.png)

Далее необходимо перенести из сети "Донская" оборудование провайдера и модельной сети Интернета в соответствующие здания.
  
![ Размещение оборудования в здании Internet](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 154910.png)



## Замена модулей на repeater 

На медиаконвертерах заменим имеющиеся модули на PT-REPEATERNM-1FFE и PT-REPEATER-NM-1CFE для подключения витой пары по технологии Fast Ethernet и оптоволокна соответственно


   
   ![Замена имеющихся модулей](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 155224.png)


## Ip-адреса

Пропишем IP-адреса серверам согласно таблице в лабораторной работе



   ![ Прописываем ip адреса.](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 155404.png)

## Dns сервер

После чего пропишем сведения о серверах на DNS-сервере сети «Донская»


   ![Проверка сведений](C:\Users\User\OneDrive\Рабочий стол\labs\lab11\screenshots\Снимок экрана 2025-05-01 155709.png)  


# Вывод

**Вывод:** В ходе выполнения лабораторной работы мы освоили настройку прав

доступа пользователей к ресурсам сети.


---

# Ответы на контрольные вопросы

**Ответы на контрольные вопросы:**

1 Как задать действие правила для конкретного протокола? – permit…

2 Как задать действие правила сразу для нескольких портов? - …

range…

3 Как узнать номер правила в списке прав доступа? – show access-lists

4 Каким образом можно изменить порядок применения правил в списке

контроля доступа? – ip access-list resequence…

