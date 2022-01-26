# Задание
Автоматический сервис. 
systemd: создать .service и .timer.
# План
## Сервис
1. Прочитать минимум про systemd service-файлы.
2. Составить perfd.service файл, который будет вызывать perfd.py.
3. Прочитать минимум про systemd timer-файлы.
4. Составить perfd.timer файл, который будет вызывать perfd.service каждые 15 минут.
## Запуск сервиса
2. systemctl start perfd.timer
