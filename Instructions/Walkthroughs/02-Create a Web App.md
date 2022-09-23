---
wts:
  title: "02\_— Создание веб-приложения (10 мин)"
  module: Module 02 - Core Azure Services (Workloads)
---
# <a name="02---create-a-web-app-10-min"></a>02 — Создание веб-приложения (10 мин)

In this walkthrough, we will create a web app that runs a Docker container. The Docker container contains a Welcome message. 

Azure App Service are actually a collection of four services, all of which are built to help you host and run web applications. The four services (Web Apps, Mobile Apps, API Apps, and Logic Apps) look different, but in the end they all operate in very similar ways. Web Apps are the most commonly used of the four services, and this is the service that we will be using in this lab.

# <a name="task-1-create-a-web-app"></a>Задача 1. Создание веб-приложения 

В рамках этой задачи вы создадите веб-приложение службы приложений Azure. 

1. Войдите на [портал Azure](http://portal.azure.com/). 

2. В колонке **Все службы** найдите и выберите элемент **Службы приложений**, а затем щелкните **+ Добавить, + Создать, + Новый**.

3. On the <bpt id="p1">**</bpt>Basics<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>Web App<ept id="p2">**</ept> blade, specify the following settings (replace <bpt id="p3">**</bpt>xxxx<ept id="p3">**</ept> in the name of the web app with letters and digits such that the name is globally unique). Leave the defaults for everything else, including the App Service Plan. 

    | Параметр | Значение |
    | -- | -- |
    | Подписка | **Использовать предоставленное по умолчанию** |
    | Группа ресурсов | **Создание группы ресурсов**|
    | Название | **myDockerWebAppxxxx** |
    | Опубликовать | **Контейнер Docker** |
    | Операционная система | **Linux** |
    | Регион | **Восточная часть США** |
    
    **Примечание**. Не забудьте заменить символы **xxxx**, чтобы имя веб-приложения было уникальным.

4. Щелкните **Далее > Docker** и настройте сведения о контейнере.  

    | Параметр | Значение |
    | -- | -- |
    | Параметры | **Один контейнер** |
    | Источник образа | **Docker Hub** |
    | Тип доступа | **Public** |
    | Образ и тег | **mcr.microsoft.com/azuredocs/aci-helloworld** |
    
 **Примечание**. Команда запуска является необязательной и не требуется в данном упражнении.

5. Нажмите кнопку **Просмотр и создание**, а затем кнопку **Создать**. 

# <a name="task-2-test-the-web-app"></a>Задача 2. Тестирование веб-приложения

В рамках этой задачи вы протестируете веб-приложение.

1. Дождитесь развертывания веб-приложения.

2. В области **Уведомления** щелкните **Перейти к ресурсу**. 

3. В этом пошаговом руководстве мы создадим веб-приложение, выполняющее контейнер Docker.

    ![Этот контейнер содержит приветственное сообщение.](../images/0801.png)

4. In a new browser window, paste the URl and press enter. The Welcome to Azure Container Instances! welcome message will be displayed.

    ![Снимок экрана: страница приветствия Экземпляров контейнеров Azure.](../images/0802.png)

5. Служба приложений Azure фактически представляет собой набор из четырех служб, каждая из которых упрощает размещение и выполнение веб-приложений. 

Эти четыре службы (веб-приложения, мобильные приложения, приложения API и Logic Apps) выглядят по-разному, однако в работе довольно похожи друг на друга.

Поздравляем! Вы успешно создали службу приложений Azure!
