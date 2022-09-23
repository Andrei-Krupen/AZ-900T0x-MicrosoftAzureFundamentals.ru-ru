---
wts:
  title: "14\_— Управление доступом с помощью RBAC (5 мин)"
  module: 'Module 05: Describe identity, governance, privacy, and compliance features'
---
# <a name="14---manage-access-with-rbac-5-min"></a>14 — Управление доступом с помощью RBAC (5 мин)

В этом пошаговом руководстве мы назначим ресурсам роли с разрешениями и просмотрим журналы.

# <a name="task-1-view-and-assign-roles"></a>Задача 1. Просмотр и назначение ролей

В рамках этой задачи мы назначим роль участника виртуальных машин. 

1. Войдите на [портал Azure](https://portal.azure.com).

2. В колонке **Все службы** найдите и выберите элемент **Группы ресурсов**, а затем выберите **+ Добавить + Новый + Создать**.

3. Create a new resource group. Click <bpt id="p1">**</bpt>Create<ept id="p1">**</ept> when you are finished. 

    | Параметр | Значение |
    | -- | -- |
    | Подписка | **Используйте предоставленные значения по умолчанию** |
    | Группа ресурсов | **myRGRBAC** |
    | Регион | **Восточная часть США (США)** |
   

4. Нажмите кнопку **Просмотр и создание**, а затем кнопку **Создать**.

5. **Обновите** страницу группы ресурсов и щелкните запись, представляющую только что созданную группу ресурсов.

6. Click on the <bpt id="p1">**</bpt>Access control (IAM)<ept id="p1">**</ept> blade, and then switch to the <bpt id="p2">**</bpt>Roles<ept id="p2">**</ept> tab. Scroll through the large number of roles definitions that are available. Use the Informational icons to get an idea of each role's permissions. Notice there is also information on the number of users and groups that are assigned to each role.
7. 
![Изображение](https://user-images.githubusercontent.com/89808319/144266949-f19d91ab-31d6-4c8b-af36-c00035925cf0.png)

7. Switch to the <bpt id="p1">**</bpt>Role assignments<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>myRGRBAC - Access control (IAM)<ept id="p2">**</ept> blade, click <bpt id="p3">**</bpt>+ Add<ept id="p3">**</ept> and then click <bpt id="p4">**</bpt>Add role assignment<ept id="p4">**</ept>. Search for the Virtual Machine Contributor role and select. Switch to the "Members" tab and Assign access to: User, group, or service principal. Then click + Select members and type in your name to the popup search function and hit 'select.' Then hit 'Review and Assign'

    
    ![Изображение](https://user-images.githubusercontent.com/89808319/144266255-3a0f8574-9358-4c21-8f95-3503747e77c8.png)

 

    **Примечание**. Роль участника виртуальных машин позволяет вам управлять виртуальными машинами, но не позволяет получить доступ к их операционной системе или управлять виртуальной сетью и учетной записью хранения, к которым они подключены.

  

8. **Обновите** страницу назначения ролей и убедитесь, что теперь вы указаны как «Участник виртуальных машин». 

    **Примечание**. Это назначение фактически не дает вам никаких дополнительных привилегий, так как ваша учетная запись уже имеет роль «Владелец», которая включает в себя все привилегии, связанные с ролью «Участник».

# <a name="task-2-monitor-role-assignments-and-remove-a-role"></a>Задача 2. Отслеживание назначений ролей и удаление роли

В рамках этой задачи мы просмотрим журнал действий, чтобы проверить назначение ролей, а затем удалим роль. 

1. В колонке группы ресурсов myRGRBAC щелкните **Журнал действий**.

2. Щелкните **Добавить фильтр**, выберите **Операция**, а затем **Создать назначение роли**.

    ![Снимок экрана: страницы журнала действий с настроенным фильтром.](../images/1503.png)

3. Убедитесь, что в журнале действий отображается ваше назначение ролей. 

    **Примечание**. Можете ли вы разобраться, как удалить свою роль?

Congratulations! You created a resource group, assigned an access role to it and viewed activity logs. 

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click <bpt id="p1">**</bpt>Delete resource group<ept id="p1">**</ept>. Verify the name of the resource group and then click <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>. Monitor the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> to see how the delete is proceeding.

