---
## Front matter
title: "Laboratory work report №9


administration of local systems"


subtitle: "Использование протокола STP. Агрегирование каналов"
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

Изучить возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними.

## Выполнение работы

1. Откроем проект с названием `lab_PT-08.pkt` и сохраним под названием `lab_PT-09.pkt`. После чего откроем его для дальнейшего редактирования.

   ![Рис. 1.1. Открытие проекта lab_PT-09.pkt](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 120227.png)

2. Сформируем резервное соединение между коммутаторами `msk-donskaya-ddlesnukhin-sw-1` и `msk-donskaya-ddlesnukhin-sw-3`. Заменим соединение мужду коммутаторами на соединение `msk-donskaya-ddlesnukhin-sw-1 (gig0/2)`.

     ![Рис. 1.2. Формирование резервного соединения между коммутаторами.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 120755.png "Рис. 1.2. Формирование резервного соединения между коммутаторами.")

   3. Настроим порт на интерфейсе `msk-donskaya-ddlesnukhin-sw-3` как транковый.
       ![Рис. 1.3. Настройка порта в транковом режиме.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 120957.png)

   4. Соединение между коммутаторами сделаем через интерфейс `Fa0/23`.
  
   ![Рис. 1.4. Соединение через интерфейсы Fa0/23](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 121046.png))  
   ![Рис. 1.5. Активация транкового режима на `msk-donskaya-ismakhorin-sw-1`.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 121305.png)  
   ![Рис. 1.6. Активация транкового режима на `msk-donskaya-ismakhorin-sw-4`.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 121449.png)

   5. С оконечного устройства `dk-donskaya-1` пропингуем серверы `mail` и `web`. В режиме симуляции проследим движение пакетов ICMP и убедимся, что они проходят через коммутатор
   ![Рис. 1.7. Проверка командой ping.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 121945.png)  
   ![Рис. 1.8. Отслеживание пакетов ICMP для web.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 122145.png)  
   ![Рис. 1.9. Отслеживание пакетов ICMP для mail.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 122315.png)
6. Настроим коммутатор `msk-donskaya-ddlesnukhin-sw-2` как корневой коммутатор STP.
 ![Рис. 1.10. Состояние протокола STP.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 122429.png)

7. Проверим путь ICMP-пакетов от хоста `dk-donskaya-1` до серверов `mail` и `web` через разные коммутаторы.

	Настроим режим Portfast на интерфейсах, к которым подключены сервера.

   ![Рис. 1.12. Путь к web.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 122741.png)  
   ![Рис. 1.13. Путь к mail](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 125016.png)


   8. Изучим отказоустойчивость STP, запустив команду `ping -n 1000 mail.donskaya.rudn.ru`, и отключим интерфейс для проверки восстановления соединения.

    ![Рис. 1.16. Проверка отказоустойчивости STP.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 125329.png)  
    
9. Переключим коммутаторы в режим Rapid PVST+ и изучим его отказоустойчивость.

    ![Рис. 1.18. Режим Rapid PVST+.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 125507.png)  
    
    
10. Сформируем агрегированное соединение интерфейсов `Fa0/20 – Fa0/23` между коммутаторами

    ![Рис. 1.21. Агрегация интерфейсов.](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 130058.png)

    ![ауф](C:\Users\User\OneDrive\Рабочий стол\labs\lab09\screenshots\Снимок экрана 2025-04-12 130309.png)


    ## Вывод

В ходе выполнения лабораторной работы мы изучили возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними.

---

## Ответы на контрольные вопросы

1. **Какую информацию можно получить, воспользовавшись командой определения состояния протокола STP для VLAN?**
   - **VLAN:** Номер VLAN.
   - **STP:** Тип протокола.
   - **Root ID/Bridge ID:** Ближайший коммутатор/Текущий коммутатор.
   - **Priority:** Приоритет.
   - **Address:** MAC-адрес.
   - **Cost:** "Затраты" до этого коммутатора.
   - **Port:** Порт.
   - **Hello Time/Max Age/Forward Delay/Aging Time:** Время работы STP и свойства портов.

2. **Как узнать режим работы STP или Rapid PVST+?**
   - Команда: `sh ru`

3. **Для чего нужен режим Portfast?**
   - Позволяет сразу включать выделенные порты, поскольку они не участвуют во включении STP.

4. **Принцип работы агрегированного интерфейса:**
   - Увеличение пропускной способности за счёт объединения каналов. Перенаправление трафика при обрыве одного из каналов.

5. **Отличия LACP, PAgP и статического агрегирования:**
   - **LACP:** Общий стандарт IEEE.
   - **PAgP:** Локальный протокол Cisco.
   - **Статическое агрегирование:** Без обязательной настройки с обеих сторон.

6. **Как узнать состояние агрегированного канала EtherChannel?**
   - Команда: `show etherchannel`
