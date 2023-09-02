Урок 3. YARN & MR

Есть большая таблица по имени

create external table hive_db.citation_data
(
oci string,
citing string,
cited string,
creation string,
timespan string,
journal_sc string,
author_sc string
)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.OpenCSVSerde'
location '/test_datasets/citation'

Её размер можно узнать вот так :
hdfs dfs -du -h -s /test_datasets/citation

Что вам нужно сделать
1. Создать таблицы в форматах PARQUET/ORC/AVRO c компрессией и без оной. (Выберите
один вариант, например ORC с компрессией)
2. Заполнить данными из большой таблицы hive_db.citation_data
3. Посмотреть на получившийся размер данных
4. Посчитать count некоторых колонок в разных форматах хранения.
5. Посчитать агрегаты по одной и нескольким колонкам в разных форматах.
6. Сделать выводы о эффективности хранения и компресии.
