### Система мониторинга

#### Объекты мониторинга:

1.  Ядро сети
2.  Маршрутизатор ядра сети Mikrotik RB1100AHx4 172.24.0.1 (SNMP)
3.  Сервер АСИ 172.24.95.201 (node\_exporter)
4.  Сервер АСИ 172.24.95.202 (node\_exporter)
5.  Сервер АСИ 172.24.95.201 (IPMI)
6.  Сервер АСИ 172.24.95.202 (IPMI)
7.  Доступность и качество связи до судов (ping)
8.  Вышка Раскат
9.  Маршрутизатор Mikrotik RBD53GR 172.24.98.1 (SNMP)
10. Коммутатор Planet GS-5220-24P4XV 172.24.98.2 (SNMP)
11. ИБП Smart-UPS 5000 172.24.98.6 (SNMP)
12. Сетевое хранилище Synology NAS DS418 172.24.98.51 (SNMP)
13. Сервер ОСА 172.24.98.101 (node\_exporter)
14. Видеокарта NVIDIA GeForce RTX 3090 на сервере ОСА
    (nvidia-gpu-exporter)
15. Суда и ДПУ
    1.  Росморпорт
    2.  Маршрутизатор RB1100AHx4 192.168.120.1 (SNMP)
    3.  Маршрутизатор LtAP LTE kit 172.16.120.1 (SNMP)
    4.  Сервер АНС 192.168.120.201 (node\_exporter)
    5.  Сервер АНС-Клиент 192.168.120.202 (node\_exporter)
    6.  Сервер АНС 192.168.120.201 (S.M.A.R.T)
    7.  Сервер АНС-Клиент 192.168.120.202 (S.M.A.R.T)
    8.  Сервер АНС 192.168.120.201 (IPMI)
    9.  Сервер АНС-Клиент 192.168.120.202 (IPMI)
    10. Сервер ОСА 192.168.120.101 (prometheus)
    11. ИБП Smart-UPS SRT 3000 192.168.120.6 (SNMP)
    12. ИБП Smart-UPS SRT 3000 192.168.120.7 (SNMP)
    13. Пола Райс
    14. Сервер АНС-Клиент в офисе 192.168.131.202 (SNMP с ядра)
    15. Маршрутизатор RB1100AHx4 192.168.130.1 (SNMP)
    16. Сервер АНС 192.168.130.201 (node\_exporter)
    17. Сервер АНС-Клиент 192.168.130.202 (node\_exporter)
    18. Сервер АНС 192.168.130.201 (S.M.A.R.T)
    19. Сервер АНС-Клиент 192.168.130.202 (S.M.A.R.T)
    20. Сервер АНС 192.168.130.201 (IPMI)
    21. Сервер АНС-Клиент 192.168.130.202 (IPMI)
    22. ИБП Smart-UPS SRT 3000 192.168.130.6 (SNMP)
    23. ИБП Smart-UPS SRT 3000 192.168.130.7 (SNMP)
    24. Совкомфлот
    25. Маршрутизатор RB1100AHx4 192.168.140.1 (SNMP)
    26. Сервер АНС 192.168.140.201 (node\_exporter)
    27. Сервер АНС-Клиент 192.168.140.202 (node\_exporter)
    28. Сервер АНС 192.168.140.201 (S.M.A.R.T)
    29. Сервер АНС-Клиент 192.168.140.202 (S.M.A.R.T)
    30. Сервер АНС 192.168.140.201 (IPMI)
    31. Сервер АНС-Клиент 192.168.140.202 (IPMI)
    32. ИБП Smart-UPS SRT 3000 192.168.140.6 (SNMP)
    33. ИБП Smart-UPS SRT 3000 192.168.140.7 (SNMP)

#### Инфраструктура

1.  Репозиторий
2.  Адрес: https://gitlab.ops.steor.ru/bskf/anav-monitoring
3.  Ветки:
    -   core: Настройки мониторинга ядра сети + Gragana + ping
    -   shalanda: Настройки prometheus + snmp + ipmi + loki
    -   Anfisa: Настройки prometheus + snmp + ipmi + loki
    -   Ulianov: Настройки prometheus + snmp + ipmi + loki
    -   testing: Настройки prometheus + snmp + ipmi + loki
4.  Адреса установки
5.  core: 172.24.0.65
6.  shalanda: 192.168.120.8 (проверил возможность работы докера на
    Windows)
7.  Anfisa: 192.168.130.202
8.  Ulianov: 192.168.140.202

#### Интерфейс

1.  Доступ
2.  url: http://172.24.0.65:3000
3.  login:admin, password:бэсовский
4.  Папки дашбордов
5.  General: Устанавливаемые по умолчанию дашборбы
6.  anav: Дашборды ядра сети
    -   anav Nodes: мониторинг хостов Линукс, удаленные хосты собираются
        с помощью federation, если связи нет, данные с удаленных хостов
        не идут
    -   APC UPS (SNMP) Core: мониторинг бесперебойников по SNMP,
        удаленные - через federation
    -   IPMI Exporter: мониторинг серверов через IPMI
    -   Logs/App: сбор логов
    -   Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    -   Node Exporter Full: Подробный мониторинг Линукс хостов
    -   Ping Probes: выдаются пинги раз в 10 с, подсчитывается процент
        потерь, время ответа
    -   S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
7.  raskat: Дашборды РТП Раскат
    -   Node Exporter Full: Подробный мониторинг Линукс хостов, с ОСы
        данные берутся с местного Prometheus через federation
    -   Nut Status: мониторинг ИБП посредством NUT
    -   SNMP Stats: мониторинг интерфейсов по SNMP, используется для
        мониторинга свича
    -   Nvidia GPU Metrics: данные с видеокарты
    -   Synology NAS Details: данные с Synology по SNMP
8.  shalanda:
    -   IPMI Exporter: мониторинг серверов через IPMI
    -   Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP, на
        172.16.120.1 есть данные с LTE
    -   Node Exporter Full: Подробный мониторинг Линукс хостов
    -   S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    -   APC UPS (SNMP): мониторинг бесперебойников по SNMP
9.  anfisa:
    -   IPMI Exporter: мониторинг серверов через IPMI
    -   Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    -   Node Exporter Full: Подробный мониторинг Линукс хостов
    -   S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    -   APC UPS (SNMP): мониторинг бесперебойников по SNMP
10. ulianov:
    -   IPMI Exporter: мониторинг серверов через IPMI
    -   Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    -   Node Exporter Full: Подробный мониторинг Линукс хостов
    -   S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    -   APC UPS (SNMP): мониторинг бесперебойников по SNMP
11. enav:
    -   SSL/TLS Exporter: Срок истечения сертификатов

### Инсталляция

Система работает в Docker, необходимо, чтобы он был установлен в
системе, тестировалось с `Docker version 20.10.5+dfsg1`,
`Docker version 20.10.21` на `Debian 11.3`, `Ubuntu 20.04.4 LTS`,
`Windows 10`. Образа контейнеров тянутся с докерхаба, поэтому нужен
Интернет. Порядок установки:

1.  В системе должен быть установлен Докер
2.  Если есть GIT, должен быть доступ к репозиторию
    `https://gitlab.ops.steor.ru`, если доступа нет или нежелательно
    устанавливать GIT, то копируем со своего компьютера с помощью rsync
    `rsync -a ./* user@172.24.0.65:monitoring/dockprom/`, заранее
    перейдя в каталог репозитория и выбрав нужную ветку
3.  Клонируем репозиторий
    `git clone git@gitlab.ops.steor.ru:bskf/anav-monitoring.git`
4.  Выбираем нужную ветку
5.  `git checkout core` - ядро
6.  `git checkout shalanda` - Шаланда
7.  `git checkout anfisa` - Анфиса
8.  `git checkout ulianov` - Ульянов
9.  Тянем, собираем, запускаем `docker up -d`
10. На хосты с Linux устанавливаем node\_exporter, snmp, на оборудовании
    в сети должен быть настроен SNMP с соответствующим community, IPMI
    на серверах также должен быть доступен
