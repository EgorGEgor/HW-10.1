# 10.1 Disaster recovery и Keepalived

### Задание 1
- Дана [схема](1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.
  ### *Решение:*
  #### Схема pkt: [hsrp_advanced-hw-1.pkt] (https://github.com/EgorGEgor/HW-10.1/blob/main/hsrp_advanced-hw-1.pkt)
<img width="959" alt="Задание 1 1" src="https://github.com/user-attachments/assets/f9199a20-aba9-4982-89ab-618ec3c580ad" />
<img width="959" alt="Задание 1 2" src="https://github.com/user-attachments/assets/945b4266-807a-45a0-9ae5-3d3becfaa268" />




### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html
### *Решение:*

#### Bash-скрипт: [check_server.sh] (https://github.com/EgorGEgor/HW-10.1/blob/main/check_server.sh)
#### Конфигурационный файл MASTER: [keepalived-11.conf] (https://github.com/EgorGEgor/HW-10.1/blob/main/keepalived-11.conf)
#### Конфигурационный файл BACKUP: [keepalived-22.conf] (https://github.com/EgorGEgor/HW-10.1/blob/main/keepalived-22.conf)

#### Демонстрация переезда плавающего ip на другой сервер в случае недоступности порта:
<img width="363" alt="Задание 2 4" src="https://github.com/user-attachments/assets/3e2b2931-1c78-434c-b258-2f5678f729b5" />
<img width="362" alt="Задание 2 5" src="https://github.com/user-attachments/assets/08d92fc9-a324-423f-8d4e-2642d6c05294" />

#### Демонстрация переезда плавающего ip на другой сервер в случае недоступности файла index.html:
<img width="363" alt="Задание 2 1" src="https://github.com/user-attachments/assets/6f7eef91-96dd-497f-8bb8-7af8c6eddce6" />
<img width="362" alt="Задание 2 2" src="https://github.com/user-attachments/assets/8ced4164-ce12-45ea-8919-24ffa16b4a69" />
<img width="365" alt="Задание 2 3" src="https://github.com/user-attachments/assets/1f110c4d-b551-46f3-8c25-b75190ed4928" />








