---
wts:
  title: "04\_— Создание виртуальной сети (20 мин)"
  module: Module 02 - Core Azure Services (Workloads)
---
# <a name="04---create-a-virtual-network-20-min"></a>04 — Создание виртуальной сети (20 мин)

В этом пошаговом руководстве мы создадим виртуальную сеть, развернем в ней две виртуальные машины, а затем настроим их, чтобы разрешить одной из виртуальных машин проверить связь с другой внутри этой виртуальной сети.

# <a name="task-1-create-a-virtual-network"></a>Задача 1. Создание виртуальной сети 

В рамках этой задачи мы создадим виртуальную сеть. 

Примечание. Перед началом лабораторной работы отключите в виртуальной машине как общедоступный, так и частный брандмауэр, открыв раздел "Пуск" > "Параметры" > "Сеть и Интернет" и найдя брандмауэр Windows.

1. Войдите на портал Azure по адресу <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>.

2. В колонке **Все службы** найдите и выберите элемент **Виртуальные сети**, а затем щелкните **+ Добавить, + Создать, + Новый**. 

3. На вкладке **Основные** укажите следующие сведения (для остальных параметров оставьте значения по умолчанию):

    | Параметр | Значение | 
    | --- | --- |
    | Подписка | **Оставьте предоставленные значения по умолчанию** |
    | Группа ресурсов | **Создание группы ресурсов** |
    | Название | **vnet1** |
    | Регион | **Восточная часть США (США)** |
    
   
4. Click the <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept> button. Ensure the validation passes. Then hit create to deploy the resource.


# <a name="task-2-create-two-virtual-machines"></a>Задача 2. Создание двух виртуальных машин

В рамках этой задачи мы создадим в виртуальной сети две виртуальных машины. 

1. В колонке **Все службы** найдите и выберите элемент **Виртуальные машины**, а затем щелкните **+ Добавить, + Создать, + Новый** и выберите в раскрывающемся списке **Виртуальная машина**. 

2. На вкладке **Основные** укажите следующие сведения (для остальных параметров оставьте значения по умолчанию):

   | Параметр | Значение | 
   | --- | --- |
   | Подписка | **Использовать предоставленное по умолчанию** |
   | Группа ресурсов |  **Выберите значение по умолчанию в раскрывающемся списке** |
   | Имя виртуальной машины | **vm1**|
   | Регион | **Восточная часть США (США)** |
   | Image | **Windows Server 2019 Datacenter, пок. 2** |
   | Имя пользователя| **azureuser** |
   | Пароль| **Pa$$w0rd1234** |
   | Общедоступные входящие порты| Выберите **Разрешить выбранные порты**.  |
   | Выбранные входящие порты| **RDP (3389)** |
   

3. Select the <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> tab. Make sure the virtual machine is placed in the <bpt id="p2">**</bpt>vnet1<ept id="p2">**</ept> virtual network. Review the default settings, but do not make any other changes. 

4. Click <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept>. After the Validation passes, click <bpt id="p1">**</bpt>Create<ept id="p1">**</ept>. Deployment times can vary but it can generally take between three to six minutes to deploy.

5. Следя за развертыванием, перейдите к следующему шагу. 

6. Create a second virtual machine by repeating steps <bpt id="p1">**</bpt>2 to 4<ept id="p1">**</ept> above. Make sure you use a different virtual machine name, that the virtual machine is in the same virtual network, and is using a new public IP address:

    | Параметр | Значение |
    | --- | --- |
    | Группа ресурсов | **Выберите значение по умолчанию в раскрывающемся списке (как для задач 1-3 и 2-2)** |
    | Имя виртуальной машины |  **vm2** |
    | Виртуальная сеть | **vnet1** |
    | Общедоступный IP-адрес | **vm2-ip** |

7. Подождите, пока обе виртуальные машины не будут развернуты, а их состояние будет определено как *выполняется*.

# <a name="task-3-test-the-connection"></a>Задача 3. Тестирование подключения 

In this task, we will try to test whether the virtual machines can communicate (ping) each other. If not we will install a rule to allow an ICMP connection. Usually ICMP connections are automatically blocked.

1. From the <bpt id="p1">**</bpt>All resources<ept id="p1">**</ept> blade, search for <bpt id="p2">**</bpt>vm1<ept id="p2">**</ept>, open its <bpt id="p3">**</bpt>Overview<ept id="p3">**</ept> blade, and make sure its <bpt id="p4">**</bpt>Status<ept id="p4">**</ept> is <bpt id="p5">**</bpt>Running<ept id="p5">**</ept>. You may need to <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> the page.

2. В колонке **Обзор** выберите **Подключить**, а затем выберите **RDP** в раскрывающемся списке.

    **Примечание**. Приведенные ниже указания помогут вам подключиться к виртуальной машине с компьютера под управлением Windows. 

3. В колонке **Подключить с RDP** оставьте параметры по умолчанию для подключения по IP-адресу через порт 3389 и щелкните элемент **Скачать RDP-файл**.

4. Откройте загруженный RDP-файл (находится в нижней левой области вашей ВМ) и щелкните **Подключить** после вывода соответствующего приглашения. 

5. В окне **Безопасность Windows** введите имя пользователя **azureuser** и пароль **Pa$$w0rd1234**, а затем нажмите кнопку **ОК**.

6. You may receive a certificate warning during the sign-in process. Click <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to create the connection and connect to your deployed VM. You should connect successfully. Close the Windows Server and Dashboard windows that pop up. You should see a Blue Windows background. You are now in your virtual machine.

7. На **обеих** созданных виртуальных машинах подключитесь по протоколу RDP и отключите общедоступный и частный брандмауэр, открыв меню "Пуск" > "Параметры" > "Сеть и Интернет" и найдя брандмауэр Windows.

8. Откройте PowerShell на виртуальной машине, нажав кнопку **Пуск**, и в поле поиска введите **PowerShell**, щелкните правой кнопкой мыши элемент **Windows PowerShell**, чтобы выполнить **Запуск от имени администратора**

9. В Powershell попытайтесь проверить связь для vm2, введя:

   ```PowerShell
   ping vm2
   ```

 10. You should be successful. You have pinged VM2 from VM1.


<bpt id="p1">**</bpt>Congratulations!<ept id="p1">**</ept> You have configured and deployed two virtual machines in a virtual network, and then you were able to connect them.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click <bpt id="p1">**</bpt>Delete resource group<ept id="p1">**</ept>. Verify the name of the resource group and then click <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>. Monitor the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> to see how the delete is proceeding.
