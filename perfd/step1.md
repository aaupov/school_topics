# Задание
Вручную запустить perf, увидеть выдачу. Написать скрипт для запуска record,
report. Первый коммит в репозиторий.

# План
## Perf - вручную
1. Установить linux perf
2. Запустить `perf record -a -- sleep 10`
3. Запустить `perf report`. Посмотреть на выдачу
## Github
5. Сделать форк linux-perfd/perfd на гитхабе.
## Git
6. Склонировать свой форк на компьютер.
## Perf - скрипт
4. Создать perfd.py
4. Написать код на python, который будет запускать perf record и perf report.
   Выдачу perf report (stdout) сохранять в буфер.
   Печатать буфер.
## Git
1. git add perfd.py
2. git commit -m "perfd.py: perf record/report"
3. git push
## Github
1. Создать Pull request
## Амир
1. Ревью pull request
2. Первый коммит в репозиторий linux-perfd
