# Схема виртуальной сети
![image](https://github.com/user-attachments/assets/baff420f-0b87-4a03-a098-ee33eef1fbfd)

# Настройка VXLAN 

**1. Создаем Bridge - на обоих роутерах Mikrotik**

![image](https://github.com/user-attachments/assets/636f2832-a4fc-469b-8f1a-4f8bd119470b)
---------------------------------------------------------------------------------------------------

**2. Создаем и настраиваем интерфейсы VXLAN на обоих роутерах Mikrotik**
- Создаем интерфейсы **Interfaces** → **VXLAN**
  
|CHR-1|CHR-2|
|-|--------|
|![image](https://github.com/user-attachments/assets/4b151d60-b89e-43bc-b498-ca5fee16b1fc)|![image](https://github.com/user-attachments/assets/0ca562c8-c3c7-4892-a638-d4afaae18fa1)|

- Добавляем порты в Bridge. Вкладка **Bridge→Ports**

|CHR-1|CHR-2|
|-|--------|
|![image](https://github.com/user-attachments/assets/8ab29a53-a7bb-416e-a6c4-ac6b92f41af4)|![image](https://github.com/user-attachments/assets/2ff851f3-4f52-46f6-a605-7935f8c77f98)|

---------------------------------------------------------------------------------------------------
  
**3. Настройка VTEP**
- Необходимо задать IP адрес для порта через который будет осуществляться VXLAN соединение  **IP** → **Addresses**
- Затем во вкладке **Interfaces** → **VXLAN** настроить **VTEP**
  
|CHR-1|CHR-2|
|-|--------|
|![image](https://github.com/user-attachments/assets/5f99e3a7-f88d-45d6-872a-dac69418edb8)|![image](https://github.com/user-attachments/assets/34d0065f-9fc8-4e6f-9f67-6affdf188491)|

# Настройка L2TP
**1. CHR-1 Server**
- Создаем профиль. Вкладка **PPP** → **Profiles**

|Generals|Protocols|
|-|--------|
|![image](https://github.com/user-attachments/assets/888dc4a5-58cd-4000-9599-e33c73872714)|![image](https://github.com/user-attachments/assets/23571be2-3b0d-4df4-bfb3-d192034b53ac)|


- Создаем пользователя. Вкладка **PPP** → **Secrets**

![image](https://github.com/user-attachments/assets/6f86fef6-0a5e-4b63-a4ab-353583c0ee1a)

- Включаем L2TP-сервер. Вкладка **PPP** → **Interfaces** → **L2TP Server**
  
![image](https://github.com/user-attachments/assets/ea5aa878-ab73-4682-ac6c-0a23602b1633)

**2. CHR-2 Client**
- Создаем L2TP/IPsec клиента. Вкладка **PPP** → **Interfaces**
  
![image](https://github.com/user-attachments/assets/0a1ef261-6dbf-4c55-aff1-a1116970f732)

# Тестирование пропускной способности сети
![image](https://github.com/user-attachments/assets/494bb425-aa3e-4dae-b234-8dae3072d893)







