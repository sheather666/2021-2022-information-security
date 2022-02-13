---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе 1"
subtitle: "дисциплина: Информационная безопасность"
author: "Абдуллаев Сайидазизхон Шухратович, НПИбд-02-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
olyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX, Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: pdflatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \usepackage{amsmath}
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание

Установить на виртуальную машину VirtualBox операционную систему Linux, дистрибутив CentOs, а также настроить необходимые для работы сервисы.

# Ход работы

1. Запускаем VirtualBox. (Рис. -@fig:001).

![Запуск VirtualBox](image/report/1.png){ #fig:001 width=73% }

2. Проверяем в свойствах VirtualBox месторасположение каталога для виртуальных машин. (Рис. -@fig:002).

![Месторасположение каталога для виртуальных машин](image/report/2.png){ #fig:002 width=73% }

3. Создаем новую виртуальную машину и указываем необходимые параметры. (Рис. -@fig:003, -@fig:004).

![Выбор имени машины и типа ОС](image/report/3.png){ #fig:003 width=73% }

![Указание объема памяти](image/report/4.png){ #fig:004 width=73% }

4. Задаем конфигурацию жёсткого диска, а также его расположение и размер. (Рис. -@fig:005, -@fig:006, -@fig:007, -@fig:008).

![Создание нового виртуального жесткого диска](image/report/5.png){ #fig:005 width=73% }

![Указание типа файла](image/report/6.png){ #fig:006 width=73% }

![Указание формата хранения](image/report/7.png){ #fig:007 width=73% }

![Указание имени и размера файла](image/report/8.png){ #fig:008 width=73% }

5. Проверяем местоположение папки для снимков виртуальной машины Base. (Рис. -@fig:009).

!["Свойства" виртуальной машины Base](image/report/8.png){ #fig:009 width=73% }

6. Выбираем образ оптического диска в окне "Носители". (Рис. -@fig:010).

![Указание типа файла](image/report/10.png){ #fig:010 width=73% }

7. Запускаем виртуальную машину Base и проводим конфигурацию параметров будущей ОС в соответствии с требованиями. (Рис. -@fig:011, -@fig:012, -@fig:013, -@fig:014, -@fig:015, -@fig:016, -@fig:017). 

 ![Запуск виртуальной машины](image/report/11.png){ #fig:011 width=73% }

 ![Установка языка для интерфейса](image/report/12.png){ #fig:012 width=73% }

 ![Подключение сети](image/report/13.png){ #fig:013 width=73% }

 ![Установка даты и времени](image/report/14.png){ #fig:014 width=73% }

 ![Установка языка для раскладки клавиатуры](image/report/15.png){ #fig:015 width=73% }

 ![Выбор программ](image/report/16.png){ #fig:016 width=73% }

 ![Выбор устройства для установки ОС](image/report/17.png){ #fig:017 width=73% }

 8. Задаем пароль на root права и создаем пользователя с правами администратора. (Рис. -@fig:018, -@fig:019).

 ![Пароль на root права](image/report/18.png){ #fig:018 width=73% }

 ![Создание пользователя](image/report/19.png){ #fig:019 width=73% }

 9. Завершаем установку систему и перезагружаем ее. (Рис. -@fig:020).

![Завершение установки виртуальной машины](image/report/20.png){ #fig:020 width=73% }

10. Запускаем виртуальную машину Base и настраиваем её. (Рис. -@fig:021, -@fig:022).

![Запуск виртуальной машины](image/report/21.png){ #fig:021 width=73% }

![Информация о лицензии](image/report/22.png){ #fig:022 width=73% }

11. Подключаемся к виртуальной машине с помощью созданной учётной записи. (Рис. -@fig:023).

![Вход в учетную запись](image/report/23.png){ #fig:023 width=73% }

12. На виртуальной машине Base запускаем терминал и переходим под учетную
запись root с помощью команды su.(Рис. -@fig:024).

 ![Вход в учетную запись](image/report/24.png){ #fig:024 width=73% }

 13. С помощью команды yum update обновлем системные файлы и устанавливаем необходимые программы. (Рис. -@fig:025, -@fig:026).

 ![Обновление системных файлов](image/report/25.png){ #fig:025 width=73% }



14. Освобождаем «Base.dvi»,чтобы другие виртуальные машины могли использовать машину Base и её конфигурацию как базовую. (Рис. -@fig:027).

![Освобождение «Base.dvi»](image/report/27.png){ #fig:027 width=73% }

15. На основе виртуальной машины Base создаем машину Host2, выбрав в качестве диска существующий жёсткий диск. (Рис. -@fig:028, -@fig:029).

![Создание машины Host2](image/report/28.png){ #fig:028 width=73% }

![Выбор виртуального жесткого диска](image/report/29.png){ #fig:029 width=73% }

# Выводы

В результате выполнения данной работы были приобретены навыки установки операционной системы на виртуальную машину, а также настроены минимально необходимые для дальнейшей работы сервисы.