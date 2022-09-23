---
wts:
  title: "12\_— Внедрение хранилища ключей Azure (5 мин)"
  module: 'Module 04: Describe general security and network security features'
---
# <a name="12---implement-azure-key-vault-5-min"></a>12 — Внедрение хранилища ключей Azure (5 мин)

В этом пошаговом руководстве мы создадим хранилище ключей Azure, а затем создадим в нем секрет пароля, получив безопасно хранимый и централизованно управляемый пароль для использования с приложениями.

# <a name="task-1-create-an-azure-key-vault"></a>Задача 1. Создание хранилища ключей Azure Key Vault 

1. Войдите на [портал Azure](https://portal.azure.com).

2. В колонке **Все службы** найдите и выберите элемент **Хранилища ключей**, а затем выберите **+ Добавить + Новый + Создать**.

3. Configure the key vault (replace <bpt id="p1">**</bpt>xxxx<ept id="p1">**</ept> in the name of the key vault with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | Параметр | Значение | 
    | --- | --- |
    | Подписка | **Использовать предоставленное по умолчанию** |
    | Группа ресурсов | **Создание группы ресурсов** |
    | Имя хранилища ключей | **keyvaulttestxxx** |
    | Location | **Восточная часть США** |
    | Ценовая категория | **Стандартный формат** |
    
    **Примечание.** Замените **xxxx**, чтобы найти уникальное имя.
4. Нажмите кнопку **Просмотр и создание**, а затем кнопку **Создать**. 

5. Once the new key vault is provisioned, click <bpt id="p1">**</bpt>Go to resource<ept id="p1">**</ept>. Or you can locate your new key vault by searching for it. 

6. Click on the key vault <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> tab and take note of the <bpt id="p2">**</bpt>Vault URI<ept id="p2">**</ept>. Applications that use your vault through the REST APIs will need this URI.

7. Take a moment to browse through some of the other key vault options. Under <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> review <bpt id="p2">**</bpt>Keys<ept id="p2">**</ept>, <bpt id="p3">**</bpt>Secrets<ept id="p3">**</ept>, <bpt id="p4">**</bpt>Certificates<ept id="p4">**</ept>, <bpt id="p5">**</bpt>Access Policies<ept id="p5">**</ept>, <bpt id="p6">**</bpt>Firewalls and virtual networks<ept id="p6">**</ept>.

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Your Azure account is the only one authorized to perform operations on this new vault. You can modify this if you wish in the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> and then the <bpt id="p2">**</bpt>Access policies<ept id="p2">**</ept> section.

# <a name="task-2-add-a-secret-to-the-key-vault"></a>Задача 2. Добавление секрета в хранилище ключей
        
В рамках этой задачи мы добавим пароль в хранилище ключей. 

1. В разделе **Параметры** выберите **Секреты**, а затем щелкните **+ Создать или импортировать**.

2. Configure the secret. Leave the other values at their defaults. Notice you can set an activation and expiration date. Notice you can also disable the secret.

    | Параметр | Значение | 
    | --- | --- |
    | Параметры отправки | **Вручную** |
    | Имя | **ExamplePassword** |
    | Значение | **hVFkk96** |

3. Нажмите кнопку **Создать**.

4. После успешного создания секрета щелкните элемент **ExamplePassword** и обратите внимание, что он имеет состояние **Включено**.

5. Select the secret you just created, note the the <bpt id="p1">**</bpt>Secret Identifier<ept id="p1">**</ept>. This is the url value that you can now use with applications. It provides a centrally managed and securely stored password. 

6. Нажмите кнопку **Показать значение секрета**, чтобы отобразить пароль, который вы указали ранее.


Настройте хранилище ключей (замените **xxxx** в имени хранилища ключей буквами и цифрами так, чтобы имя было глобально уникальным).

Для остальных параметров оставьте значения по умолчанию.
