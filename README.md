Теоретические вопросы:
1.	Что такое LACP? Это протокол, который позволяет объединять несколько физических портов в один логический канал (EtherChannel). Это делает сеть более надежной и увеличивает пропускную способность.
2.	Процесс формирования: Порты отправляют друг другу специальные кадры (LACPDU). Они обмениваются информацией (системный ID, ключ агрегации). Если параметры совпадают, порты объединяются в один логический интерфейс.
3.	Преимущества:
o	Стандартизация: Работает на оборудовании разных вендоров.
o	Отказоустойчивость: Если один кабель сломается, трафик пойдет по другому.
o	Балансировка нагрузки: Трафик распределяется между линками.
4.	Состояния портов:
o	Off: LACP выключен.
o	Active: Порт активно инициирует переговоры и отправляет LACPDU.
o	Passive: Порт ждет, пока другая сторона начнет переговоры (не отправляет LACPDU первым).
o	Bundle/Up: Порты успешно объединились в EtherChannel.

Практическая часть (Команды для Packet Tracer):
Ситуация А: Оборудование Cisco 2960 

SW1

enable
configure terminal
interface port-channel 1
 no shutdown
 exit
interface fastEthernet 0/1
 channel-group 1 mode active
 no shutdown
 exit
interface fastEthernet 0/2
 channel-group 1 mode active
 no shutdown
 exit
interface port-channel 1
 switchport trunk encapsulation dot1q
 switchport mode trunk
 exit
 
SW2 

enable
configure terminal
interface port-channel 1
 no shutdown
 exit
interface fastEthernet 0/1
 channel-group 1 mode active
 no shutdown
 exit
interface fastEthernet 0/2
 channel-group 1 mode active
 no shutdown
 exit
interface port-channel 1
 switchport trunk encapsulation dot1q
 switchport mode trunk
 exit
Диагностика:
show etherchannel summary — в строке напротив Port-channel 1 должно стоять SU (S - L2, U - в работе).



Ситуация Б: Оборудование Eltex MES2324

SW1

enable
configure terminal
interface aggregateport 1
 switchport mode trunk
 exit
interface fastEthernet 0/1
 port-group 1
 no shutdown
 exit
interface fastEthernet 0/2
 port-group 1
 no shutdown
 exit
 
SW2

enable
configure terminal
interface aggregateport 1
 switchport mode trunk
 exit
interface fastEthernet 0/1
 port-group 1
 no shutdown
 exit
interface fastEthernet 0/2
 port-group 1
 no shutdown
 exit
Диагностика:
show aggregateport summary — статус Up.



Задание 3. OSPF (Open Shortest Path First)
Теоретические вопросы:
1.	Что такое OSPF? Протокол динамической маршрутизации, который использует алгоритм Дейкстры для поиска самого короткого пути (по стоимости) к каждой сети.
2.	Выбор DR и BDR: На сетях с множественным доступом (Ethernet) выбирается главный маршрутизатор (DR) и резервный (BDR) для уменьшения количества обновлений. Выбирается тот, у кого выше приоритет (по умолчанию 1), а если приоритет равен — у кого Router ID (самый большой IP-адрес на Loopback или физическом интерфейсе) больше.
3.	Типы LSA (важно для ответа):
o	LSA Type 1 (Router LSA): О каждом маршрутизаторе и его интерфейсах (внутри своей зоны).
o	LSA Type 2 (Network LSA): О сегменте сети с DR (для широковещательных сетей).
o	LSA Type 3 (Summary LSA): О сетях из других зон (от ABR — пограничного маршрутизатора).
o	LSA Type 5 (External LSA): О внешних маршрутах (из других протоколов, например, RIP).
4.	Расчет стоимости (Cost): Формула: Cost = 10^8 / Пропускная способность (бит/сек). Чем выше скорость интерфейса, тем меньше стоимость. Можно задавать вручную командой ip ospf cost.

Практическая часть (Команды для Packet Tracer):
Ситуация А: Оборудование Cisco 2960 

SW1

enable
configure terminal
ip routing
router ospf 1
 router-id 1.1.1.1
 network 10.0.12.0 0.0.0.255 area 0
 network 10.0.13.0 0.0.0.255 area 0
 network 192.168.1.0 0.0.0.255 area 0
 end

SW2

enable
configure terminal
ip routing
router ospf 1
 router-id 2.2.2.2
 network 10.0.12.0 0.0.0.255 area 0
 network 10.0.23.0 0.0.0.255 area 0
 network 192.168.2.0 0.0.0.255 area 0
 end

SW3

enable
configure terminal
ip routing
router ospf 1
 router-id 3.3.3.3
 network 10.0.13.0 0.0.0.255 area 0
 network 10.0.23.0 0.0.0.255 area 0
 network 192.168.3.0 0.0.0.255 area 0
 end
Диагностика:
1.	show ip ospf neighbor — FULL/DR или FULL/BDR.
2.	show ip route — в списке должны быть буквы O (означает, что маршруты изучены по OSPF).


Ситуация Б: Оборудование Eltex MES2324

SW1

enable
configure terminal
ip routing
router ospf 1
 router-id 1.1.1.1
 network 10.0.12.0 255.255.255.0 area 0.0.0.0
 network 10.0.13.0 255.255.255.0 area 0.0.0.0
 network 192.168.1.0 255.255.255.0 area 0.0.0.0
 end
 
SW2


enable
configure terminal
ip routing
router ospf 1
 router-id 2.2.2.2
 network 10.0.12.0 255.255.255.0 area 0.0.0.0
 network 10.0.23.0 255.255.255.0 area 0.0.0.0
 network 192.168.2.0 255.255.255.0 area 0.0.0.0
 end
 
SW3

enable
configure terminal
ip routing
router ospf 1
 router-id 3.3.3.3
 network 10.0.13.0 255.255.255.0 area 0.0.0.0
 network 10.0.23.0 255.255.255.0 area 0.0.0.0
 network 192.168.3.0 255.255.255.0 area 0.0.0.0
 end
Диагностика:
show ip ospf neighbor — проверяем статус FULL.
show ip route — проверяем наличие сетей с пометкой O.
