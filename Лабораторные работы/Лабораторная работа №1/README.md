# **Лабораторная работа №1. Базовая настройка коммутатора**
## **Задачи:**
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 1. Проверка конфигурации коммутатора по умолчанию**
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 2. Создание сети и настройка основных параметров устройства**
* Настройте базовые параметры коммутатора
* Настройте IP-адрес для ПК
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 3. Проверка сетевых подключений**
* Отобразите конфигурацию устройства
* Протестируйте сквозное соединение, отправив эхо-запрос
* Протестируйте возможности удаленного управления с помощью Telnet

### **Часть 1. Создание сети и проверка настроек коммутатора по умолчанию**
#### **Шаг 1. Создайте сеть согласно топологии**
&nbsp;&nbsp;&nbsp;&nbsp;а. Подсоедините консольный кабель, как показано в топологии              
![Подключение консольного кабеля](image.png)

&nbsp;&nbsp;&nbsp;&nbsp;b. Установите консольное подключение к коммутатору с компьютера PC-A с помощью программы эмуляции терминала
![alt text](image-1.png)


#### **Вопросы:**
1. *Почему нужно использовать консольное подключение для первоначальной настройки коммутатора?*    
Консоль обеспечивает прямой доступ к интерфейсу конфигурации коммутатора независимо от состояния сети.
2. *Почему нельзя подключиться к коммутатору через Telnet или SSH?*   
Необходимо настроить на коммутаторе IP-адресацию.     

#### **Шаг 2. Проверка настроек коммутатора по умолчанию**     
а. Вводим команду **enable**, чтобы войти в привилегированный режим.    
![alt text](image-3.png)    
Вводим команду **show rinning-config**, чтобы убедиться, что на коммутаторе находится пустой файл конфигурации.   

б. Изучаем текущий файл работающей конфигурации    
&nbsp;&nbsp;&nbsp;&nbsp;- *Сколько интерфейсов FastEthernet имеется на коммутаторе 2960?*    
Ответ: 24 интерфейса.   
&nbsp;&nbsp;&nbsp;&nbsp;- *Сколько интерфейсов Gigabit Ethernet имеется на коммутаторе 2960?*    
Ответ: 2 интерфейса.     
&nbsp;&nbsp;&nbsp;&nbsp;- *Каков диапазон значений, отображаемых в vty-линиях?*   
Ответ: 0-15           

с. Изучите файл загрузочной конфигурации (startup configuration), который содержится в энергонезависимом ОЗУ (NVRAM).       
![alt text](image-4.png)     
&nbsp;&nbsp;&nbsp;&nbsp;- *Почему появляется это сообщение?*   
Ответ: потому что никто еще не записывал конфигурацию.

d.	Изучите характеристики SVI для VLAN 1.    
&nbsp;&nbsp;&nbsp;&nbsp; - *Назначен ли IP-адрес сети VLAN 1?*      
Ответ: нет, не назначен.    
&nbsp;&nbsp;&nbsp;&nbsp;- *Какой MAC-адрес имеет SVI?*     
Ответ: MAC-адрес виртуального интерфейса коммутатора (SVI) может быть разным и зависит от конкретной конфигурации.    
В данном случае MAC-адрес 0060.2fld.8612
![alt text](image-5.png)   
&nbsp;&nbsp;&nbsp;&nbsp;- *Данный интерфейс включен?*    
Ответ: этот интерфейс выключен.   
![alt text](image-6.png)     

e. Изучите IP-свойства интерфейса SVI сети VLAN 1.    
&nbsp;&nbsp;&nbsp;&nbsp;- *Какие выходные данные вы видите?*    
![alt text](image-7.png)        
в VLAN 1 не назначен порт, который находится в рабочем состоянии     

f. Подсоедините кабель Ethernet компьютера PC-A к порту 6 на коммутаторе и изучите IP-свойства интерфейса SVI сети VLAN 1. Дождитесь согласования параметров скорости и дуплекса между коммутатором и ПК.    
![alt text](image-8.png)      
![  ](image-9.png)   

g. Изучите сведения о версии ОС Cisco IOS на коммутаторе.  
&nbsp;&nbsp;&nbsp;&nbsp;- *Под управлением какой версии ОС Cisco IOS работает коммутатор?*    
![ ](image-10.png)     
&nbsp;&nbsp;&nbsp;&nbsp;- *Как называется файл образа системы?*      
![alt text](image-11.png)    

h. Изучите свойства по умолчанию интерфейса FastEthernet, который используется компьютером PC-A.      
![alt text](image-12.png)   

&nbsp;&nbsp;&nbsp;&nbsp;-*Интерфейс включен или выключен?*       
&nbsp;&nbsp;&nbsp;&nbsp; Интерфейс включен.   
&nbsp;&nbsp;&nbsp;&nbsp;- *Что нужно сделать, чтобы включить интерфейс?*    
&nbsp;&nbsp;&nbsp;&nbsp; Нужно выполнить команду **no shutdown**    
&nbsp;&nbsp;&nbsp;&nbsp; -*Какой MAC-адрес у интерфейса?*    
![alt text](image-13.png)     
&nbsp;&nbsp;&nbsp;&nbsp;-*Какие настройки скорости и дуплекса заданы в интерфейсе?*     
![alt text](image-14.png)        

i. Изучите флеш-память     
&nbsp;&nbsp;&nbsp;&nbsp;Выполните команду show **flash** или **dir flash**     
![alt text](image-15.png)      
&nbsp;&nbsp;&nbsp;&nbsp;-*Какое имя присвоено образу Cisco IOS?*    
![alt text](image-16.png)      

### **Часть 2. Настройка базовых параметров сетевых устройств**     

#### **Шаг 1. Настройка основных параметров коммутатора**      
a. В режиме глобальной конфигурации настройте базовые параметры конфигурации     
![alt text](image-17.png)      

b.	Назначьте IP-адрес интерфейсу SVI на коммутаторе.      
![alt text](image-18.png)       

c. Доступ через порт консоли также следует ограничить  с помощью пароля.     
![alt text](image-19.png)      

d.	Настройте каналы виртуального соединения для удаленного управления (vty), чтобы коммутатор разрешил доступ через Telnet.      
![alt text](image-20.png)      

&nbsp;&nbsp;&nbsp;&nbsp;-* Для чего нужна команда login?*     
&nbsp;&nbsp;&nbsp;&nbsp; Она включает проверку пароля для доступа к этой линии. Без этой команды коммутатор не будет требовать пароль, даже если он задан командой **password**.  

### **Шаг 2. Настройка IP-адреса на компьютере PC-A.**    
![alt text](image-21.png)      

### **Часть 3. Проверка сетевых подключений**  
#### **Шаг 1. Отображение конфигурации коммутатора**    
а. Конфигурация приведена ниже.   
  S1#show run      
Building configuration...      

Current configuration : 1294 bytes    
!    
version 15.0      
no service timestamps log datetime msec      
no service timestamps debug datetime msec       
service password-encryption     
!      
hostname S1     
!      
enable secret 5     $1$mERr$9cTjUIEqNGurQiFU.ZeCi1     
!      
!      
!     
no ip domain-lookup      
!        
!       
!        
spanning-tree mode pvst      
spanning-tree extend system-id     
!     
interface FastEthernet0/1      
!     
interface FastEthernet0/2      
!      
interface FastEthernet0/3      
!      
interface FastEthernet0/4      
!      
interface FastEthernet0/5      
!      
interface FastEthernet0/6      
!       
interface FastEthernet0/7       
!        
interface FastEthernet0/8       
!         
interface FastEthernet0/9       
!        
interface FastEthernet0/10       
!       
interface FastEthernet0/11      
!       
interface FastEthernet0/12      
!       
interface FastEthernet0/13     
!       
interface FastEthernet0/14      
!      
interface FastEthernet0/15       
!      
interface FastEthernet0/16       
!       
interface FastEthernet0/17      
!      
interface FastEthernet0/18     
!      
interface FastEthernet0/19      
!      
interface FastEthernet0/20      
!      
interface FastEthernet0/21      
!      
interface FastEthernet0/22      
!       
interface FastEthernet0/23     
!       
interface FastEthernet0/24      
!      
interface GigabitEthernet0/1      
!      
interface GigabitEthernet0/2      
!       
interface Vlan1       
 ip address 192.168.1.2 255.255.255.0           
!        
banner motd ^CUnauthorized access is strictly prohibited.^C        
!       
!      
!      
line con 0      
 password 7 0822455D0A16     
 login      
!       
line vty 0 4       
 password 7 0822455D0A16       
 login      
 transport input telnet      
line vty 5 15     
 login      
!      
!       
!      
!      
end      

b. Проверить параметры VLAN 1.    
![alt text](image-22.png)      

&nbsp;&nbsp;&nbsp;&nbsp;-*Какова полоса пропускания этого интерфейса?*   
&nbsp;&nbsp;&nbsp;&nbsp; 100000 Кбит/с   

#### **Шаг 2. Протестируйте сквозное соединение, отправив эхо-запрос**     
a. В командной строке компьютера PC-A с помощью утилиты ping проверьте связь сначала с адресом PC-A.    
![alt text](image-23.png)        

b. Из командной строки компьютера PC-A отправьте эхо-запрос на административный адрес интерфейса SVI коммутатора S1.      
![alt text](image-24.png)       

#### **Шаг 3. Проверьте удаленное управление коммутатором S1.**    
a.Откройте Tera Term или другую программу для эмуляции терминала с поддержкой Telnet.     
![alt text](image-29.png)         

b.	Выберите сервер Telnet и укажите адрес управления SVI для подключения к S1.  Пароль: **cisco**    
![alt text](image-28.png)       

c.	После ввода пароля **cisco** вы окажетесь в командной строке пользовательского режима. Для перехода в исполнительский режим EXEC введите команду **enable** и используйте секретный пароль **class**.      
![alt text](image-30.png)     

d.	Сохраните конфигурацию.    
![alt text](image-31.png)       

e.	Чтобы завершить сеанс Telnet, введите exit.       
![alt text](image-32.png)      

## 	**Вопросы для повторения**      
1.	*Зачем необходимо настраивать пароль VTY для коммутатора?*       
Настройка пароля VTY для коммутатора Cisco необходима для ограничения доступа к устройству по протоколу Telnet.        

2.	*Что нужно сделать, чтобы пароли не отправлялись в незашифрованном виде?*   
Чтобы пароли в устройствах Cisco не отправлялись в незашифрованном виде, нужно активировать функцию шифрования паролей 

