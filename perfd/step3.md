# Задание
Формирование записей: sqlite. Сохранение perf файлов. Обновление количества
    сэмплов при повторных запусках.

# План
## Файлы
1. Формирование уникального имени файла для perf файлов при помощи [tempfile.mktemp](https://docs.python.org/3/library/tempfile.html#tempfile.mktemp).
2. Сохранение perf файлов под уникальными именами: подставить имя в perf record.
3. Обновить вызов perf script для использования текущего perf файла.
## Записи в БД
1. Установить в Ubuntu пакет sqlite.
2. Установить python module [sql30](https://github.com/gitvipin/sql30).
4. Задание схемы базы данных при помощи sql30:
    - Схема: имя perf файла, имя объектного файла, количество сэмплов (для данного объектного файла в данном perf файле).
    - [Пример](https://github.com/gitvipin/sql30/#:~:text=reviews%27%0A%20%20%20%20PKEY%20%3D%20%27rid%27-,DB_SCHEMA,-%3D%20%7B%0A%20%20%20%20%20%20%20%20%27db_name%27%3A%20%27./reviews.db)
4. Добавление записей, собранных в текущем запуске:
   `db.write()`
5. После записи не забыть `db.commit()`   
5. Проверить записи в БД: `db.read()`
