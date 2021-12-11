# Задание
Автоматический сервис. Установка в систему.
systemd: создать .service и .timer.
# План
## Установка скрипта в систему
1. Создать минимальный Makefile, который будет копировать скрипт в /usr/local/bin:
```
install:
  cp perfd.py /usr/local/bin/perfd.py
```
2. make install
## Сервис
1. Прочитать минимум про systemd service-файлы.
2. Составить perfd.service файл, который будет вызывать /usr/local/bin/perfd.py
3. Прочитать минимум про systemd timer-файлы.
4. Составить perfd.timer файл, который будет вызывать perfd.service каждые 15 минут.
## Установка сервиса в систему
1. Добавить установку service и timer в систему в Makefile (`systemd: cp...`)
## Запуск сервиса
2. systemctl start perfd.timer
