---
# Front matter
lang: ru-RU
title: "Лабораторная работа № 5"
subtitle: "Дискреционное разграничение прав в Linux. Исследование влияния дополнительных атрибутов"
author: "Абдуллаев Сайидазизхон Шухратович"

# Formatting
toc-title: "Содержание"
toc: true
toc_depth: 2
lof: true
lot: true
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10
  - \interlinepenalty=0
  - \hyphenpenalty=50
  - \exhyphenpenalty=50
  - \binoppenalty=700
  - \relpenalty=500
  - \clubpenalty=150
  - \widowpenalty=150
  - \displaywidowpenalty=50
  - \brokenpenalty=100
  - \predisplaypenalty=10000
  - \postdisplaypenalty=0
  - \floatingpenalty = 20000
  - \raggedbottom
  - \usepackage{float}
  - \floatplacement{figure}{H}

---

# Цель работы

Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Задание

Закрепить дискреционное разграничение прав в Linux с дополнительными атрибутами.

# Теоретическое введение

В Linux, как и в любой многопользовательской системе, абсолютно естественным образом возникает задача разграничения доступа субъектов — пользователей к объектам — файлам дерева каталогов. Один из подходов к разграничению доступа — так называемый дискреционный - предполагает назначение владельцев объектов, которые по собственному усмотрению определяют права доступа субъектов (других пользователей) к объектам (файлам), которыми владеют. Дискреционные механизмы разграничения доступа используются для разграничения прав доступа процессов как обычных пользователей, так и для ограничения прав системных программ в (например, служб операционной системы), которые работают от лица псевдопользовательских учетных записей. Чтобы получить доступ к файлам в Linux, используются разрешения. Эти разрешения назначаются трем объектам: файлу, группе и другому объекту. Для управления правами используется команда chmod. При использовании chmod в относительном режиме вы работаете с тремя индикаторами, чтобы указать, что вы хотите сделать. Сначала вы указываете, для кого вы хотите изменить разрешения. Для этого вы можете выбрать между пользователем (u), группой (g) и другими (o). Затем вы

используете оператор для добавления или удаления разрешений из текущего режима или устанавливаете их абсолютно. В конце вы используете r(read), w(write) и x(execute), чтобы указать, какие разрешения вы хотите установить.При использовании chmod вы можете устанавливать разрешения для пользователя (user), группы (group) и других (other).Помимо основных разрешений, о которых вы только что прочитали, в Linux также есть набор расширенных разрешений. Это не те разрешения, которые вы устанавливаете по умолчанию, но иногда они предоставляют полезное дополнение.

# Ход работы

1. Готовим систему и входим из-под пользователя guest. Пишем программу simpleid.c. Компилируем программу, запускаем, видим вывод uid и gid пользователя, сравниваем вывод с id (все совпадает). (Рис. 1, 2).

![Листинг simpleid.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/1.png){ #fig:001 width=73% }



![Запуск и сверка simpleid.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/2.png){ #fig:002 width=73% }

2. Усложняем программу и запускаем её. (Рис. 3, 4).

![Листинг simpleid2.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/4.png){ #fig:003 width=73% }



![Запуск simpleid2.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/5.png){ #fig:004 width=73% }

3. Из-под суперпользователя меняем владельца и добавляем SetUID бит на файл. Проверяем правильность и запускаем программу еще раз. еuid возвращает id владельца, а real_uid возвращает uid запускающего пользователя.(Рис. 5).

![Смена владельца и добавление SetUID бита, запуск и сверка simpleid2.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/7.png){ #fig:005 width=73% }

4. Теперь добавим на файл SetGID бит с проделаем все то же самое. (Рис. 6, 7).

![Добавление SetGID бита](C:/Users/yokai/Desktop/infobez/lab5/image/report/10.png){ #fig:006 width=73% }



 ![Запуск simpleid2.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/11.png){ #fig:007 width=73% } 

5. Пишем программу readfile.c. (Рис. 8).

 ![Листинг readfile.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/12.png){ #fig:008 width=73% }

6. Компилируем программу. (Рис. 9).

![Компиляция](C:/Users/yokai/Desktop/infobez/lab5/image/report/13.png){ #fig:009 width=73% }

7. Меняем владельца у файла readfile.c и запрещаем чтение всем, кроме суперпользователя. Проверяем, что guest не может читать. Меняем владельца у программы readfile и добавляем SetUID бит на неё. (Рис. 10, 11, 12).

![Смена владельца readfile.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/14.png){ #fig:010 width=73% }

![Проверка на cat из-под guest’a](C:/Users/yokai/Desktop/infobez/lab5/image/report/15.png){ #fig:011 width=73% }

![Смена владельца readfile.c](C:/Users/yokai/Desktop/infobez/lab5/image/report/16.png){ #fig:012 width=73% }

8. Проверяем, может ли программа readfile прочитать файл readfile.c и файл /etc/shadow. Да, может. Хотя сам пользователь вручную не мог. Всё дело в том, что при вызове программы права пользователя повышаются SetUID битом до прав владельца, который может читать файлы (суперпользователь в нашем случае). (Рис. 13, 14).

   ![Чтение readfile.c программой readfile](C:/Users/yokai/Desktop/infobez/lab5/image/report/17.png){ #fig:013 width=73% }

   ![Чтение /etc/shadow программой readfile](C:/Users/yokai/Desktop/infobez/lab5/image/report/18.png){ #fig:014 width=73% }

   9. Проверяем Sticky бит. Для этого создаем файл, которому даем rw права для others и пишем туда слово test. Теперь пробуем выполнить дозапись в файл, перезапись файла и его удаление. Всё, кроме удаления, прошло успешно. (Рис. 15, 16).

      ![Создание файла, правка прав файла](C:/Users/yokai/Desktop/infobez/lab5/image/report/19.png){ #fig:015 width=73% }

      ![Проверка прав, тестирование, и попытка удаления](C:/Users/yokai/Desktop/infobez/lab5/image/report/22.png){ #fig:016 width=73% }

      10. Повышаем права до суперпользователя и удаляем Sticky-бит с папки /tmp. Повторяем наши тесты. Теперь прошли все команды, включая удаление файла. Таким образом, пользователь, не являющийся владельцем файла, смог его удалить, так как Sticky-бит не был настроен. Возвращаем Sticky-бит на папку /tmp. (Рис. 17, 18).

          ![Удаление Sticky-бита и повторное тестирование](C:/Users/yokai/Desktop/infobez/lab5/image/report/25.png){ #fig:017 width=73% }

          ![Возвращение Sticky-бита](C:/Users/yokai/Desktop/infobez/lab5/image/report/26.png){ #fig:018 width=73% }



# Выводы

В результате выполнения данной работы были практические навыков работы в консоли с расширенными атрибутами файлов.