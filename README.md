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

#### Мнфраструктура

1. Репозиторий
  - Адрес: https://gitlab.ops.steor.ru/bskf/anav-monitoring
  - Ветки:
    - core
	- shalanda
	- for_an
