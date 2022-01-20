---
wts:
    title: '21 — расчет составных соглашений об уровне обслуживания (SLA) (5 мин)'
    module: 'Модуль 06. Описание соглашений об управлении затратами и уровне обслуживания Azure'
---
# 21 — Расчет составных соглашений об уровне обслуживания (SLA) (5 мин)

В этом пошаговом руководстве мы определим соглашение об уровне обслуживания (SLA) для обеспечения доступности служб Azure, а затем рассчитаем ожидаемую доступность приложения на базе составного SLA.

Наш пример приложения состоит из следующих служб Azure. Здесь мы не будем вдаваться в подробности конфигурации и архитектуры, так как хотим рассмотреть лишь общий пример.

+ **Сервис приложений**: для размещения приложения.
+ **Azure AD B2C**: для проверки подлинности при входе пользователей и управления профилями.
+ **Шлюз приложений**: для управления доступом к приложениям и масштабированием. 
+ **База данных SQL Azure**: для хранения данных приложения. 

# Задача 1. Определите процентные значения времени работы нашего приложения по соглашению об уровне обслуживания.

1. В браузере перейдите на страницу со [сводкой SLA для служб Azure](https://azure.microsoft.com/ru-ru/support/legal/sla/summary/).

2. Найдите значение времени безотказной работы по SLA **99,95 %** для **Службы приложений**. Щелкните **Просмотреть все подробные данные**, а затем разверните пункт **Сведения Соглашения об уровне обслуживания**. Обратите внимание на значения **Процент времени работоспособности за месяц** и **Компенсация за обслуживание**.

3. Вернитесь на веб-страницу SLA, найдите службу **Azure Active Directory B2C** и определите значение времени безотказной работы по SLA, равное **99,9 %**. 

4. Найдите значение времени безотказной работы по SLA **99,95 %** для **Шлюза приложений**. 

5. База данных SQL Azure использует уровни "Премиум", но не настроена для избыточных развертываний между зонами. Найдите значение времени безотказной работы по SLA **99,99 %** для **Базы данных SQL Azure**. 

    **Примечание**. Существуют разные значения времени безотказной работы для разных конфигураций и развертываний Базы данных SQL Azure. Важно, чтобы вы четко представляли требуемые значения времени безотказной работы при планировании развертывания и настройки и оценке затрат на них. Небольшие изменения времени безотказной работы могут повлиять на стоимость обслуживания, а также усложнить настройку. К другим службам на веб-странице сводки по SLA для Azure, которые могут заинтересовать вас, относятся **Виртуальные машины**, **Учетные записи хранения** и **Cosmos DB**.

# Задача 2. Расчет процента времени безотказной работы приложения по составному SLA

1. Если какая-либо из служб, составляющих наше приложение, недоступна, пользователи не смогут войти в это приложение и работать с ним. Таким образом, общее время безотказной работы нашего приложения состоит из следующего:

    **% времени безотказной работы Службы приложений** X **% времени безотказной работы Azure AD B2C** X **% времени безотказной работы Шлюза приложений Azure** X **% времени безотказной работы Базы данных SQL Azure** = **Общий % времени безотказной работы**

    что в процентном выражении выглядит следующим образом:

    **99,95 %** X **99,9 %** X **99,95 %** X **99,99 %** = **99,79 %**

    Это ожидаемая доступность нашего приложения на основе SLA с учетом текущих служб и архитектуры.

Поздравляем! Вы определили время безотказной работы на основе SLA для каждой службы в нашем примере приложения и рассчитали ожидаемую доступность приложения на основе составного SLA.