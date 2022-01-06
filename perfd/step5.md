# Задание
Конвертирование профиля. Для всех perf файлов: perf2bolt. merge-fdata.
# План
1. Задать функцию, которая для данного объектного файла подготовит .fdata файл
    для BOLT (`prepare_fdata(objfile)`)
    - Найти в БД все perf файлы, содержащие сэмплы с данным объектным файлом.
    - Для каждого perf.suffix файла вызвать perf2bolt:
        `perf2bolt objfile -p perf.suffix -o perf.suffix.fdata`
    - Объединить все полученные fdata файлы при помощи merge-fdata:
        `merge-fdata perf.suffix1.fdata1 perf.suffix2.fdata ... -o objname.fdata`
2. Функция возвращает путь к fdata файлу.
