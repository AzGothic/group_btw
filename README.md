# GroupBWT test

##### Проблема:
Есть структура папок, где документы редактируются пользователями.\
Для каждого открытого документа в качестве резервной копии есть файл .bak (doc1.bak для doc1.doc), но довольно часто они остаются там после закрытия редактора документов.\
Во многих случаях документы также удаляются или перемещаются, и пустая папка не требуется, но они остаются там, потому что они содержат только ненужные файлы .bak.

##### Задание:
Реализуйте скрипт, который - начиная с корневой папки, заданной в качестве параметра, - очищает оставшиеся файлы .bak без соответствующего документа, а затем удаляет папку(опционально, если передан параметр), очищенную в процессе очистки.\
Скрипт должен запускается с консоли и принимает обязательный параметр “корневая папка” и опциональный параметр - удалять пустую папку или нет.

##### Решение:
За основу взята структура папок с одним уровнем вложенности
```
Корневая папка
    Папка с файлами
        Файлы
    Папка с файлами 2
        Файлы
    ...
```
Скрипт сделан с учетом ручного запуска, если нужен запуск в автоматическом режиме на регулярной основе, например, тем же кроном, то само собой как минимум вывод действий в консоль нужно убрать, ну либо заглушить в крон задаче...\
Мега структуры классов и прочего тут нету, т.к. код написан под конкретную задачу и ничего лишнего тут нету.

## Requirements
* PHP 7

## Installation
* Clone Git repository
* Run command for init directories structure for test script\
` > php init_dirs `

## Usage
* Run command for analyze directory\
` > php check_dirs --dir {directory_for_analyze_path_from_root_dir} [--rmempty] `\
--dir - required, path to needed folder for analyze from root path, default 'files'\
--rmempty - set up if you need to remove empty dirs\
Examples:\
` > php check_dirs --dir files ` - analyze 'files' folder without remove empty folders\
` > php check_dirs --dir files --rmempty ` - analyze 'files' folder and remove empty folders
* Run command for re-init directories structure for test script any time you need\
` > php init_dirs `
