### Система мониторинга

#### Объекты мониторинга:

1. Ядро сети
  - Маршрутизатор ядра сети Mikrotik RB1100AHx4 172.24.0.1 (SNMP)
  - Сервер АСИ 172.24.95.201 (node_exporter)
  - Сервер АСИ 172.24.95.202 (node_exporter)
  - Сервер АСИ 172.24.95.201 (IPMI)
  - Сервер АСИ 172.24.95.202 (IPMI)
  - Доступность и качество связи до судов (ping)
2. Вышка Раскат
  - Маршрутизатор Mikrotik RBD53GR 172.24.98.1 (SNMP)
  - Коммутатор Planet GS-5220-24P4XV 172.24.98.2 (SNMP)
  - ИБП Smart-UPS 5000 172.24.98.6 (SNMP) 
  - Сетевое хранилище Synology NAS DS418 172.24.98.51 (SNMP)
  - Сервер ОСА 172.24.98.101 (node_exporter)
  - Видеокарта NVIDIA GeForce RTX 3090 на сервере ОСА (nvidia-gpu-exporter)
3. Суда и ДПУ
    1. Росморпорт
      - Маршрутизатор RB1100AHx4 192.168.120.1 (SNMP)
      - Маршрутизатор LtAP LTE kit 172.16.120.1 (SNMP)
      - Сервер АНС 192.168.120.201 (node_exporter)
      - Сервер АНС-Клиент 192.168.120.202 (node_exporter)
      - Сервер АНС 192.168.120.201 (S.M.A.R.T)
      - Сервер АНС-Клиент 192.168.120.202 (S.M.A.R.T)
      - Сервер АНС 192.168.120.201 (IPMI)
      - Сервер АНС-Клиент 192.168.120.202 (IPMI)
      - Сервер ОСА 192.168.120.101 (prometheus)
      - ИБП Smart-UPS SRT 3000 192.168.120.6 (SNMP)
      - ИБП Smart-UPS SRT 3000 192.168.120.7 (SNMP)
    2. Пола Райс
      - Сервер АНС-Клиент в офисе 192.168.131.202 (SNMP с ядра)
      - Маршрутизатор RB1100AHx4 192.168.130.1 (SNMP)
      - Сервер АНС 192.168.130.201 (node_exporter)
      - Сервер АНС-Клиент 192.168.130.202 (node_exporter)
      - Сервер АНС 192.168.130.201 (S.M.A.R.T)
      - Сервер АНС-Клиент 192.168.130.202 (S.M.A.R.T)
      - Сервер АНС 192.168.130.201 (IPMI)
      - Сервер АНС-Клиент 192.168.130.202 (IPMI)
      - ИБП Smart-UPS SRT 3000 192.168.130.6 (SNMP)
      - ИБП Smart-UPS SRT 3000 192.168.130.7 (SNMP)
    3. Совкомфлот
      - Маршрутизатор RB1100AHx4 192.168.140.1 (SNMP)
      - Сервер АНС 192.168.140.201 (node_exporter)
      - Сервер АНС-Клиент 192.168.140.202 (node_exporter)
      - Сервер АНС 192.168.140.201 (S.M.A.R.T)
      - Сервер АНС-Клиент 192.168.140.202 (S.M.A.R.T)
      - Сервер АНС 192.168.140.201 (IPMI)
      - Сервер АНС-Клиент 192.168.140.202 (IPMI)
      - ИБП Smart-UPS SRT 3000 192.168.140.6 (SNMP)
      - ИБП Smart-UPS SRT 3000 192.168.140.7 (SNMP)

#### Инфраструктура

1. Репозиторий
  - Адрес: https://gitlab.ops.steor.ru/bskf/anav-monitoring
  - Ветки:
    - core: Настройки мониторинга ядра сети + Gragana + ping 
	- shalanda: Настройки prometheus + snmp + ipmi + loki
	- Anfisa: Настройки prometheus + snmp + ipmi + loki
	- Ulianov: Настройки prometheus + snmp + ipmi + loki
	- testing: Настройки prometheus + snmp + ipmi + loki
2. Адреса установки
  - core: 172.24.0.65
  - shalanda: 192.168.120.8 (проверил возможность работы докера на Windows)
  - Anfisa: 192.168.130.202
  - Ulianov: 192.168.140.202

#### Интерфейс

1. Доступ
  - url: http://172.24.0.65:3000
  - login:admin, password:бэсовский
2. Папки дашбордов
  - General: Устанавливаемые по умолчанию дашборбы
  - anav: Дашборды ядра сети
    - anav Nodes: мониторинг хостов Линукс, удаленные хосты собираются с помощью federation, если связи нет, данные с удаленных хостов не идут
    - APC UPS (SNMP) Core: мониторинг бесперебойников по SNMP, удаленные - через federation
    - IPMI Exporter: мониторинг серверов через IPMI
    - Logs/App: сбор логов 
    - Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    - Node Exporter Full: Подробный мониторинг Линукс хостов
    - Ping Probes: выдаются пинги раз в 10 с, подсчитывается процент потерь, время ответа
    - S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
  - raskat: Дашборды РТП Раскат
    - Node Exporter Full: Подробный мониторинг Линукс хостов, с ОСы данные берутся с местного Prometheus через federation
    - Nut Status: мониторинг ИБП посредством NUT
    - SNMP Stats: мониторинг интерфейсов по SNMP, используется для мониторинга свича
    - Nvidia GPU Metrics: данные с видеокарты
    - Synology NAS Details: данные с Synology по SNMP
  - shalanda:
    - IPMI Exporter: мониторинг серверов через IPMI
    - Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP, на 172.16.120.1 есть данные с LTE
    - Node Exporter Full: Подробный мониторинг Линукс хостов 
    - S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    - APC UPS (SNMP): мониторинг бесперебойников по SNMP
  - anfisa:
    - IPMI Exporter: мониторинг серверов через IPMI
    - Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    - Node Exporter Full: Подробный мониторинг Линукс хостов 
    - S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    - APC UPS (SNMP): мониторинг бесперебойников по SNMP
  - ulianov:
    - IPMI Exporter: мониторинг серверов через IPMI
    - Mikrotik Monitoring SNMP: мониторинг микротиков по SNMP
    - Node Exporter Full: Подробный мониторинг Линукс хостов 
    - S.M.A.R.T. monitoring core: мониторятся диски по S.M.A.R.T.
    - APC UPS (SNMP): мониторинг бесперебойников по SNMP
  - enav:
    - SSL/TLS Exporter: Срок истечения сертификатов
