---
## Front matter
lang: ru-RU
title: "Лабораторная работа № 6"
subtitle: "Мандатное разграничение прав в Linux"
author: "Абдуллаев Сайидазизхон Шухратович"

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

## Цель работы

Развить навыки администрирования ОС Linux.Проверить работу SELinx на практике совместно с веб-сервером Apache..

# Ход работы

## Вход в систему, проверка режима и политики

![](image/pres/1.png){ #fig:001 width=100% }

## Проверка работы веб-сервера

![](image/pres/2.png){ #fig:002 width=100% }

## Состояние SELinux переключателей

![](image/pres/3.png){ #fig:003 width=100% }

## Создание html-файла

![](image/pres/4.png){ #fig:004 width=100% }

## Смена контекста файла

![](image/pres/5.png){ #fig:005 width=100% }

## Запуск веб-сервера Apache на прослушивание ТСР-порта 81

![](image/pres/6.png){ #fig:006 width=72% }

## Перезапуск веб-сервера, анализ log-файлов

![](image/pres/7.png){ #fig:007 width=100% }

## Вывод

- В результате выполнения данной работы была изучена технология  SELinux, а также проверена работа  SELinux с веб-сервером Apache.