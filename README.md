### Практические навыки работы с ZFS ###

1. Определение алгоритма с наилучшим сжатием

Список всех дисков, которые ксть на виртуальной машине:

```
lsblk
```

![files](img/1.png)

Создание пулов в режиме RAID 1:

zpool create otus1 mirror /dev/sdb /dev/sdc
zpool create otus2 mirror /dev/sdd /dev/sde
zpool create otus3 mirror /dev/sdf /dev/sdg
zpool create otus4 mirror /dev/sdh /dev/sdi


Созданные пулы:

```
zpool list
```

![files](img/2.png)


```
zpool status
```

![files](img/3.png)

Добавление разных алгоритмов сжатия в каждую файловую систему:
- Алгоритм lzjb: zfs set compression=lzjb otus1
- Алгоритм lz4: zfs set compression=lz4 otus2
- Алгоритм gzip: zfs set compression=gzip-9 otus3
- Алгоритм zle: zfs set compression=zle otus4

Методы сжатия файловых систем:
```
zfs get all | grep compression
```

![files](img/4.png)

Скачивание файлов во все пулы:

```
for i in {1..4}; do wget -P /otus$i https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done
```
![files](img/5.png)

Проверим, что файл был скачан во все пулы:
```
ls -l /otus*
```
![files](img/6.png)

Проверим, сколько места занимает один и тот же файл в разных пулах и
проверим степень сжатия файлов:

```
zfs list
```

![files](img/7.png)

```
zfs get all | grep compressratio | grep -v ref
```
![files](img/8.png)

#### Вывод

***Алгоритм gzip-9 самый эффективный по сжатию.***

2. Определение настроек пула

Скачиваем архив в домашний каталог:

```
wget -O archive.tar.gz --no-check-certificate 'https://drive.google.com/u/0/uc?id=1KRBNW33QWqbvbVHa3hLJivOAt60yukkg&e
xport=download'
```
![files](img/9.png)

Разархивируем его:
```
tar -xzvf archive.tar.gz
```
![files](img/10.png)

Проверка, возможно ли импортировать данный каталог в пул:
```
zpool import -d zpoolexport/
```

![files](img/11.png)

Импорт пула otus в ОС:

```
zpool import -d zpoolexport/ otus
```

Данный вывод показывает нам имя пула, тип raid и его состав. Сделаем импорт данного пула к нам в ОС:
```
zpool status
```
![files](img/12.png)


Уточнение параметров пула:
```
zfs get available otus;
zfs get recordsize otus;
zfs get compression otus;
zfs get checksum otus
```

3. Работа со снапшотом, поиск сообщения от преподавателя

Скачивание файла, указанного в задании:
```
wget -O otus_task2.file --no-check-certificate 'https://drive.google.com/u/0/uc?id=1gH8gCL9y7Nd5Ti3IRmplZPF1XjzxeRAG&e
xport=download'
```
![files](img/13.png)

Восстановим файловую систему из снапшота: 
```
zfs receive otus/test@today < otus_task2.file
```

Далее, ищем в каталоге /otus/test файл с именем “secret_message”:

![files](img/14.png)

```
find /otus/test -name "secret_message"
```

```
cat /otus/test/task1/file_mess/secret_message
```
![files](img/15.png)

```
https://github.com/sindresorhus/awesome
```

![files](img/16.png)


