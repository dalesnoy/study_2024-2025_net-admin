---
## Front matter
title: "Laboratory work report №10


administration of local systems"


subtitle: "Настройка списков управления доступом (ACL)"
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

## Цель работы

Освоить настройку прав доступа пользователей к ресурсам сети.

## Выполнение работы

1. Откроем проект с названием `lab_PT-09.pkt` и сохраним под названием `lab_PT-10.pkt`. После чего откроем его для дальнейшего редактирования.

   ![Рис. 1.1. Открытие проекта lab_PT-10.pkt](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 181518.png)
# Изменение топологии

2. В рабочей области проекта подключите ноутбук администратора с именем admin к сети к `other-donskaya-1` с тем, чтобы разрешить ему потом любые действия, связанные с управлением сетью. Для этого подсоедините ноутбук к порту 24 коммутатора `msk-donskaya-sw-4` и присвойте ему статический адрес `10.128.6.200`, указав в качестве gateway-адреса `10.128.6.1` и адреса DNS-сервера `10.128.0.5`
![Рис. 1.2. Формирование резервного соединения между коммутаторами.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 181441.png "Подсоединение ноутбука к порту 24 коммутатора msk-donskaya-sw-4 и изменение названия.")
# Статический адрес


   3. Указываем статический адрес `10.128.6.200` и gateway адрес `10.128.6.1
![Рис. 1.3. Настройка ноутбука admin.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 182704.png)

   4. После чего мы пропингуем. Права доступа пользователей сети будем настраивать на маршрутизаторе msk- donskaya-gw-1, поскольку именно через него проходит весь трафик сети. Ограничения можно накладывать как на входящий (in), так и на исходящий (out) трафик. По отношению к маршрутизатору накладываемые ограничения будут касаться в основном исходящего трафика. Различают стандартные (standard) и расширенные (extended) списки контроля доступа (Access Control List, ACL). Стандартные ACL проверяют только адрес источника трафика, расширенные — адрес как источника, так и получателя, тип протокола и TCP/UDP порты.

   ![Рис. 1.4. Проверяем настройку адресов ноутбука admin](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 182822.png)

#
   ## Настройка web-сервера

Далее настроим доступ к web-серверу по порту tcp 80 Здесь :

1. Создадим список контроля доступа с названием servers-out (так как предполагается ограничить доступ в конкретные подсети и по

отношению к маршрутизатору это будет исходящий трафик)

2. Укажем (в качестве комментария-напоминания remark web), что ограничения предназначены для работы с web-сервером;

3. Дадим разрешение доступа (permit) по протоколу TCP всем (any) пользователям сети (host) на доступ к web-серверу, имеющему адрес
10.128.0.2, через порт 80

   
   ![Рис. 1.5. Настройка доступа к web-серверу по порту tcp 80.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 183238.png)

# 
К интерфейсу f0/0.3 подключаем список прав доступа serversout и применяем к исходящему трафику (out). При этом команда ping будет демонстрировать недоступность web-сервера как по имени, так и по ip-адресу web-сервера)


   ![Рис. 1.6. Подключение списка прав доступа serversout`.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 183422.png)


#

   5. Проверка демонстрации недоступности web-сервера при использовании команды ping по ip-адресу web-сервера.


   ![Рис. 1.7. Проверка командой ping.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 183728.png)  

#

   ![Рис. 1.8. Отслеживание пакетов ICMP для web.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 183728.png)  

#
Добавляем дополнительный доступ для администратора по протоколам Telnet и FTP:

   ![Рис. 1.9. Добавляем дополнительный доступ для администратора по протоколам Telnet и FTP.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 184132.png)

#


   ![Рис.1.9](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 184253.png)
#

![Рис. 2](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 184405.png)


# Настройка доступа к серверам

Настроим доступ к файловому, почтовому и web серверу. Здесь:

1. В списке контроля доступа servers-out укажем (в качестве комментария-напоминания remark file), что следующие ограничения

предназначены для работы с file-сервером;

2. Всем узлам внутренней сети (10.128.0.0) разрешим доступ по

протоколу SMB (работает через порт 445 протокола TCP) к каталогам общего пользования;

3. Любым узлам разрешим доступ к file-серверу по протоколу FTP. Запись 0.0.255.255 — обратная маска (wildcard mask).

#

 ![Рис. 1.10. Доступ к серверам .](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 185322.png)


#

Разрешим icmp-запросы. Здесь:

Демонстрируем явное управление порядком размещения правил — правило разрешения для icmp-запросов добавляется в начало списка

контроля доступа.

Номера строк правил в списке контроля доступа можно посмотреть с помощью команды show access −lists (Рис. 1.17):


   ![Рис. 1.12. ](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 185456.png)  

#

   
   ![Рис. 1.13. Настройка доступа для сети Other .](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 185656.png)

#


   8. Настроим доступ администратора к сети сетевого оборудования.

  ![Рис. 1.16. Настройка доступа](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 190022.png)  

#
    
10. Проверим корректность установленных правил доступа, попытавшись

получить доступ по различным протоколам с разных устройств сети к подсети

серверов и подсети сетевого оборудования


![Рис. 1.18. Проверка.](C:\Users\User\OneDrive\Рабочий стол\labs\lab10\screenshots\Снимок экрана 2025-04-17 190202.png)  

#

 ## Вывод

В ходе выполнения лабораторной работы мы освоили настройку прав

доступа пользователей к ресурсам сети.


#

## Ответы на контрольные вопросы

1 Как задать действие правила для конкретного протокола? – permit…

2 Как задать действие правила сразу для нескольких портов? - …

range…

3 Как узнать номер правила в списке прав доступа? – show access-lists

4 Каким образом можно изменить порядок применения правил в списке

контроля доступа? – ip access-list resequence…

