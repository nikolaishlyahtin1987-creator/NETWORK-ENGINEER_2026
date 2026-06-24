# **Настройка DHCPv6**     
## **Топология**           
  ![alt text](image.png)      
## **Таблица адресации**     
  ![alt text](image-1.png)     
## **Задачи**    
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 1. Создание сети и настройка основных параметров устройства**      
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 2. Проверка назначения адреса SLAAC от R1**     
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 3. Настройка и проверка сервера DHCPv6 без гражданства на R1**      
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 4. Настройка и проверка состояния DHCPv6 сервера на R1**  
### &nbsp;&nbsp;&nbsp;&nbsp;**Часть 5. Настройка и проверка DHCPv6 Relay на R2**     
## **Часть 1. Создание сети и настройка основных параметров устройства**     
### **Шаг 1. Создайте сеть согласно топологии.**   
  ![alt text](image-2.png)  
### **Шаг 2. Настройте базовые параметры каждого коммутатора.**    
#### &nbsp;&nbsp;&nbsp;&nbsp;a.	Присвойте коммутатору имя устройства.      
 ![alt text](image-3.png)     

 ![alt text](image-4.png)      

#### &nbsp;&nbsp;&nbsp;&nbsp;b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.     
![alt text](image-5.png)     

![alt text](image-6.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;c.	Назначьте **class** в качестве зашифрованного пароля привилегированного режима EXEC.    
![alt text](image-7.png)      

![alt text](image-8.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;d.	Назначьте **cisco** в качестве пароля консоли и включите вход в систему по паролю.      
![alt text](image-9.png)      

![alt text](image-11.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;e.	Назначьте **cisco** в качестве пароля VTY и включите вход в систему по паролю.      
![alt text](image-12.png)     

![alt text](image-13.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;f.	Зашифруйте открытые пароли.   
![alt text](image-14.png)     

![alt text](image-15.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.     
![alt text](image-16.png)       

![alt text](image-17.png)     

#### &nbsp;&nbsp;&nbsp;&nbsp;h.	Отключите все неиспользуемые порты.     
#### Для S1:
![alt text](image-18.png)    
![alt text](image-19.png)     
![alt text](image-20.png)     

#### Для S2:
![alt text](image-21.png)     
![alt text](image-22.png)    
![alt text](image-23.png)    
![alt text](image-24.png)    

#### &nbsp;&nbsp;&nbsp;&nbsp;i.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.    
![alt text](image-25.png)    

![alt text](image-26.png)     




