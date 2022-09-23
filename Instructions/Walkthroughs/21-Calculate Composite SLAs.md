---
wts:
  title: "21\_— Расчет составных соглашений об уровне обслуживания (SLA) (5 мин)"
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="21---calculate-composite-slas-5-min"></a>21 — Расчет составных соглашений об уровне обслуживания (SLA) (5 мин)

В этом пошаговом руководстве мы определим соглашение об уровне обслуживания (SLA) для обеспечения доступности служб Azure, а затем рассчитаем ожидаемую доступность приложения на базе составного SLA.

Our example application consists of these Azure services. We will not go in to deep architectural configuration and considerations, the intention here is to give an high level example.

+ **Служба приложений**: для размещения приложения.
+ **Azure AD B2C**: для проверки подлинности при входе пользователей и управления профилями.
+ **Шлюз приложений**: для управления доступом к приложениям и масштабированием. 
+ **База данных SQL Azure**: для хранения данных приложения. 

# <a name="task-1-determine-the-sla-uptime-percentage-values-for-our-application"></a>Задача 1. Определите процентные значения времени работы нашего приложения по соглашению об уровне обслуживания.

1. В браузере перейдите на страницу со [сводкой SLA для служб Azure](https://azure.microsoft.com/en-us/support/legal/sla/summary/).

2. Locate the <bpt id="p1">**</bpt>App Service<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.95%<ept id="p2">**</ept>. Click <bpt id="p1">**</bpt>View full details<ept id="p1">**</ept>, and then expand <bpt id="p2">**</bpt>SLA details<ept id="p2">**</ept>. Notice the <bpt id="p1">**</bpt>Monthly uptime percentages<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Service Credits<ept id="p2">**</ept>.

3. Вернитесь на веб-страницу SLA, найдите службу **Azure Active Directory B2C** и определите значение времени безотказной работы по SLA, равное **99,9 %** . 

4. Найдите значение времени безотказной работы по SLA **99,95 %** для **Шлюза приложений**. 

5. The Azure SQL database uses Premium tiers but is not configured for Zone Redundant Deployments. Locate the <bpt id="p1">**</bpt>Azure SQL Database<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.99%<ept id="p2">**</ept>. 

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: There are different uptime values for different configurations and deployments of Azure SQL Database. It is important you are clear on your required uptime values, when planning and costing your deployment and configuration. Small changes in uptime can have impact on service costs as well as potentially increase complexity in configuration. Some other services that may be of interest on the Azure SLA summary web page would include <bpt id="p1">**</bpt>Virtual Machines<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Storage Accounts<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Cosmos DB<ept id="p3">**</ept>.

# <a name="task-2-calculate-the-application-composite-sla-percentage-uptime"></a>Задача 2. Расчет процента времени безотказной работы приложения по составному SLA

1. Наш пример приложения состоит из следующих служб Azure.

    **% времени безотказной работы Службы приложений** X **% времени безотказной работы Azure AD B2C** X **% времени безотказной работы Шлюза приложений Azure** X **% времени безотказной работы Базы данных SQL Azure** =  **= Общий % времени безотказной работы**

    что в процентном выражении выглядит следующим образом:

    **99.95%** X **99.9%** X **99.95%** X **99.99%**  = **99.79%**

    Это ожидаемая доступность нашего приложения на основе SLA с учетом текущих служб и архитектуры.

Здесь мы не будем вдаваться в подробности конфигурации и архитектуры, так как хотим рассмотреть лишь общий пример.
