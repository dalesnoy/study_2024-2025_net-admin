---
## Front matter
title: "Laboratory work report №12


administration of local systems"


subtitle: "Настройка NAT."
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
Приобретение практических навыков по настройке доступа локальной сети к внешней сети посредством NAT.


# Выполнение работы
**Выполнение работы:**

Откроем проект с названием `lab_PT-11.pkt` и сохраним под названием `lab_PT-12.pkt.` После чего откроем его для дальнейшего редактирования


   ![Открытие проекта lab_PT-11.pkt](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 144747.png)

   
# **Настройка коммутатора и маршрутизатора**

**Настройка коммутатора и маршрутизатора:**
Для начала нам необходимо произвести первоначальную настройку маршрутизатора и коммутатора провайдера.

![Настройка маршрутизатора.](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 145130.png)

# Настройка коммутатора
![Настройка коммутатора.](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 145341.png)

# **Настройка интерфейсов:**

Теперь настроим **интерфейсы** маршрутизатора провайдера:

# Настройка интерфейсов маршрутизатора
![Настройка интерфейсов маршрутизатора](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 145549.png)

# Настройка интерфейсов коммутатора

![Настройка интерфейсов коммутатора](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 145829.png)

#
## Сеть Донская
**Сеть Донская**
Следующим шагом мы должны настроить интерфейсы маршрутизатора сети "Донская" для доступа к сети провайдера
   
![Настройка интерфейса в сети  "Донская".](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 150104.png)
# Настройка сети Донская
Настроим на маршрутизаторе сети «Донская» NAT с правилами, указанными в лабораторной работе

  
![Настройка пула адресов для NAT](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 150237.png)

# Настройка списка доступа для NAT

![Настройка списка доступа для NAT](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 150320.png)

# Настройка сети дисплейных классов

![Сеть дисплейных классов (имеют доступ только к сайтам, необходимым для учёбы (www.yandex.ru (192.0.2.11), stud.rudn.university (192.0.2.12)).](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 150913.png)

# Настройка сети кафедр
![Сеть кафедр (работает только с образовательными сайтами (esystem.pfur.ru (192.0.2.13))).](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 151320.png)

# Настройка сети администрации
![Сеть администрации (имеет возможность работать только с сайтом университета (www.rudn.ru (192.0.2.14))).](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 151603.png)


![Доступ для компьютера администратора (в сети для других пользователей компьютер администратора имеет полный доступ в Интернет. Другие не имеют доступа.).](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 151703.png)


# Настройка NAT
   
   ![**. **Настройка NAT (Port Address Translation и интерфейсов для NAT).](C:\Users\User\OneDrive\Рабочий стол\labs\lab12\screenshot\Снимок экрана 2025-05-02 151320.png)




# Вывод

**Вывод:** В ходе выполнения лабораторной работы мы приобрели практические навыки по настройке доступа локальной сети к внешней сети посредством NAT.




# Ответы на контрольные вопросы

**Ответы на контрольные вопросы:**

1.     В чём состоит основной принцип работы NAT (что даёт наличие NAT в сети организации)? - **NAT на устройстве позволяет ему соединять публичные и частные сети между собой с помощью только одного IP-адреса для группы.**
#
2.     В чём состоит принцип настройки NAT (на каком оборудовании и что нужно настроить для из локальной сети во внешнюю сеть через NAT)? - **Настроить интерфейсы на внутренних и внешних маршрутизаторах, наборы правил для преобразования IP.**
#
3.     Можно ли применить Cisco IOS NAT к субинтерфейсам? - **Да, поскольку они существуют в энергонезависимой памяти.**
#
4.     Что такое пулы IP NAT? - **Выделяемые для трансляции NAT IP.**
#
5.     Что такое статические преобразования NAT? - **Взаимно однозначное преобразование внутренних IP во внешние.**
