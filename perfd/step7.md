# Задание
Подмена оптимизированных файлов при помощи символических ссылок.
    Сброс количества сэмплов.
# План
БД:
1. Добавить таблицу в схему БД для оптимизированных объектных файлов (optimized).
2. Добавить таблицу в схему БД для черного списка (blacklist).

Добавить дополнительные фильтры для применения оптимизации:
1. Не оптимизировать уже оптимизированные файлы.
2. Не оптимизировать файлы из черного списка.

После оптимизации:
1. Проверить оптимизированный файл: [проверка](check.md).
2. Если проверка неуспешна:
    - добавить файл в таблицу blacklist.
    - пропустить замену файла.
4. Если проверка успешна:
    - сохранить исходный objfile как objfile.bak: `cp objfile objfile.bak`
    - создать символическую ссылку outfile -> objfile: `ln -sf outfile objfile`
    - Добавить оптимизированный файл в таблицу optimized.


8. Удостовериться, что для оптимизированных и пропущенных файлов perf файлы все еще накапливаются, но
    оптимизация не повторяется.
