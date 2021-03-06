# Цель
Из накопленных perf-файлов (которых много) собрать профиль для данного приложения (объектного файла). В perf-файле содержатся сэмплы для многих объектных файлов. perf2bolt достаёт из perf-файла сэмплы для одного объектного файла и сохраняет профиль в fdata-файл. merge-fdata объединяет несколько fdata-файлов.

# Задание
Подготовка профиля к использованию в BOLT:
- Конвертирование профиля: perf2bolt.
- Объединение профилей: merge-fdata.
# План
Установить BOLT: [инструкция](https://github.com/llvm/llvm-project/tree/main/bolt#manual-build).

В скрипте:
1. Задать функцию, которая для данного объектного файла подготовит .fdata файл
    для BOLT (`prepare_fdata(objfile)`)
    - Найти в БД все perf файлы, содержащие сэмплы с данным объектным файлом.
    - Для каждого perf файла вызвать perf2bolt:
        ```
        perf2bolt objfile -p perf_file -o perf_file.fdata
        ```
    - Объединить все полученные fdata файлы при помощи merge-fdata:
        ```
        merge-fdata perf_file1.fdata perf_file2.fdata ... > tmp_fdata
        ```
    - Удалить промежуточные fdata-файлы (perf_file{1..N}.fdata), оставить только последний (tmp_fdata).
        
2. Функция возвращает путь к tmp_fdata файлу.
