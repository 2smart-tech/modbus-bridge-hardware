1. Winner sku662285 (Чёрный датчик с влагой и температурой):
    1. Распиновка
        - желтый   ----  "+" питание
        - черный   ----   "-" питание
        - красный  ----  "485-А"
        - зеленый  ----  "485-B"

    2. Запись Slave ID - пишем новый Slave ID функцией записи регистра (06) на адрес 0 на Slave ID = 0 (Broadcast)
    
    3. Получение данных - читаем 2 записи с адреса = 0 функцией 03 (Чтение регистра)


2. WellPro WP8025ADAM (Синяя коробка на 8 реле)
    1. Запись Slave ID - используется софт для конфигурирования устройств от вендора
    2. Получение данных - читаем 8 записей с адреса = 0 функцией 01 (Чтение коилов)
    3. Щелкание реле - записываем коил по адресу равному номеру порта


3. WellPro WP3084ADAM (Синяя коробка для измерения показателей вольтажа)
    1. Запись Slave ID - используется софт для конфигурирования устройств от вендора
    2. Получение данных - читаем 8 записей с адреса = 0 функцией 03 (Чтение регистров)

4. Noname TH10S-B (Датчик влажности и температуры (Зонтик))
    1. Распиновка
        - красный   ----  "+" питание
        - черный   ----   "-" питание
        - зеленый ----  "485-А"
        - белый     ----  "485-B"

    2. Запись Slave ID - пишем новый Slave ID функцией записи регистра (06) на адрес 0 на Slave ID = 0 (Broadcast)
    3. Получение данных - читаем 2 записи с адреса = 0 функцией 03 (Чтение регистра)

5. Noname T10S-B (Датчик температуры в термоусадке)
    1. Распиновка
        - красный     ----  "+" питание
        - черный      ----   "-" питание
        - желтый      ----  "485-А"
        - зеленый     ----  "485-B"

    2. Запись Slave ID - пишем новый Slave ID функцией записи регистра (06) на адрес 100, по умолчанию 1
    3. Получение данных - читаем 1 запись с адреса = 0 функцией 03 (Чтение регистра)

6. Noname PD3060E-6 (PT100)
     1. Настройка
        Для настройки необходимо сразу после включения питания, без чтения, отправить запрос 06 на регистр 16.
        Значением должно быть десятичное представление строки $ID A4 (без пробела), где вместо $ID идёт 16 ричное представление будущего slave id устройства.
        Для ID = 11 строка будет 0BA4, что в десятичной форме будет 2980.
        Запрос следует слать на актуальный slave id (не на броадкаст)
        Если устройство показывает значение, отличное от -100 на отключенных контактах, то отправляем значение -1000 на 18 регистр
    
    2. Получение данных - читаем 8 записей с адреса = 32 функцией 03 (Чтение регистров)

6. Noname RS485RB-1 / RS485RB-2 / RS485RB-4 / RS485RB-8 / RS485RB-16 / RS485RB-32 - блок реле
    1. Настройка - Slave ID выставляется путём перевода числа в двоичный формат с добавлением ведущего нуля
    2. Получение данных - читаем N записей с адреса = 1 функцией 03 (Чтение регистров), вместо N идёт количество портов
    3. Щелкание реле - записываем одиночный регистр по адресу равному номеру порта. Значение 512 - выключить, 256 - включить
    6 всегда 1
    6 это 1 модбас
    0 ат команды
    10 010101
    15 111101