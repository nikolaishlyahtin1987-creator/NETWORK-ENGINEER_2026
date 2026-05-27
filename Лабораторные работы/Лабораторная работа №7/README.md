# **Развертывание коммутируемой сети с резервными каналами**    
## **Топология**        
![alt text](image.png)        
## **Таблица адресации**      
![alt text](image-1.png)       

## **Цели**      
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 1. Создание сети и настройка основных параметров устройства**         
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 2. Выбор корневого моста**        
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 3. Наблюдение за процессом выбора протоколом STP порта, исходя из стоимости портов**       
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 4. Наблюдение за процессом выбора протоколом STP порта, исходя из приоритета портов**      

## **Часть 1: Создание сети и настройка основных параметров устройства**       
### **Шаг 1: Создайте сеть согласно топологии.**     
  ![alt text](image-2.png)       

### **Шаг 2:Выполните инициализацию и перезагрузку коммутаторов**     
#### Выполняем на каждом коммутаторе       
![alt text](image-3.png)      

### **Шаг 3: Настройте базовые параметры каждого коммутатора.**        
#### **Коммутатор S1**    
#### &nbsp;&nbsp;&nbsp;&nbsp;a.	Отключите поиск DNS   
![alt text](image-4.png) 

#### &nbsp;&nbsp;&nbsp;&nbsp;b.	Присвойте имена устройствам в соответствии с топологией.     
![alt text](image-5.png)      

#### &nbsp;&nbsp;&nbsp;&nbsp;c.	Назначьте class в качестве зашифрованного пароля доступа к привилегированному режиму.     
![alt text](image-6.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;d.	Назначьте cisco в качестве паролей консоли и VTY и активируйте вход для консоли и VTY каналов.      
![alt text](image-7.png)      

#### &nbsp;&nbsp;&nbsp;&nbsp;e.	Настройте logging synchronous для консольного канала.    
![alt text](image-8.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;f.	Настройте баннерное сообщение дня (MOTD) для предупреждения пользователей о запрете несанкционированного доступа.    
![alt text](image-9.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;g.	Задайте IP-адрес, указанный в таблице адресации для VLAN 1 на всех коммутаторах.     
![alt text](image-10.png)    

#### &nbsp;&nbsp;&nbsp;&nbsp;h.	Скопируйте текущую конфигурацию в файл загрузочной конфигурации.     
![alt text](image-11.png)    

#### ** Коммутатор S2**   
![alt text](image-12.png)    

![alt text](image-13.png)     

![alt text](image-14.png)     

![alt text](image-15.png)      

![alt text](image-16.png)     

![alt text](image-17.png)     

![alt text](image-18.png)     

![alt text](image-19.png)      

#### **Коммутатор S3**    
![alt text](image-20.png)     

![alt text](image-21.png)     

![alt text](image-22.png)     

![alt text](image-23.png)     

![alt text](image-24.png)     

![alt text](image-25.png)     

![alt text](image-26.png)     

![alt text](image-27.png)    


