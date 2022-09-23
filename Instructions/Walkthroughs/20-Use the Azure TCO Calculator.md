---
wts:
  title: "20\_— Использование калькулятора совокупной стоимости владения Azure (10 мин)"
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="20---use-the-azure-tco-calculator-10-min"></a>20 — Использование калькулятора совокупной стоимости владения Azure (10 мин)


В этом пошаговом руководстве вы воспользуетесь калькулятором совокупной стоимости владения для создания отчета о сравнении затрат для локальной среды.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: This walkthrough provides example definitions of on-premises infrastructure and workloads for a typical datacenter. To create a TCO Calculator report, use the example definitions or provide details of your <bpt id="p1">*</bpt>actual<ept id="p1">*</ept> on-premises infrastructure and workloads.

# <a name="task-1-configure-the-tco-calculator"></a>Задача 1. Настройка калькулятора совокупной стоимости владения

В рамках этой задачи мы добавим в калькулятор информацию об инфраструктуре. 

1. В браузере перейдите на страницу [калькулятора совокупной стоимости владения](https://azure.microsoft.com/en-us/pricing/tco/calculator/).

2. Чтобы добавить сведения о локальной серверной инфраструктуре, щелкните **+ Добавление рабочей нагрузки сервера** в области **Определение рабочих нагрузок**.

    | Настройки | Значение |
    | -- | -- |
    | Имя | **Серверы: виртуальные машины Windows** |
    | Рабочая нагрузка | **Сервер Windows/Linux** |
    | Среда | **Виртуальные машины** |
    | Операционная система | **Windows** |  
    | Виртуальные машины | **50** |
    | Виртуализация | **Hyper-V** |
    | Ядра | **8**|
    | ОЗУ (ГБ) | **16** |
    | Оптимизация по | **ЦП** |
    | Windows Server 2008/2008 R2 | **Выключено** |

3. Выберите **+ Добавление рабочей нагрузки сервера**, чтобы создать строку для нового определения рабочих нагрузок сервера. 

    | Настройки | Значение |
    | -- | -- |
    | Имя | **Серверы: виртуальные машины Linux** |
    | Рабочая нагрузка | **Сервер Windows/Linux** |
    | Среда | **Виртуальные машины** |
    | Операционная система | **Linux** |  
    | Виртуальные машины | **50** |
    | Виртуализация | **VMware** |
    | Ядра | **8**|
    | ОЗУ (ГБ) | **16** |
    | Оптимизация по | **ЦП** |
    | Windows Server 2008/2008 R2 | **Выключено** |

4. В области **Хранилище** нажмите кнопку **Добавление хранилища**.

    | Настройки | Значение |
    | -- | -- |
    | Имя | **Хранилище сервера** |
    | Тип хранилища | **Локальный диск/SAN** |
    | Тип диска | **HDD** |
    | Capacity | **60 ТБ** |  
    | Backup | **120 ТБ** |
    | Архив | **0 TБ** |

5. В области **Работа в сети** добавьте пропускную способность. 

    | Настройки | Значение |
    | -- | -- |
    | Исходящая пропускная способность | 15 ТБ|

6. Щелкните **Далее**.

7. Изучите варианты и внесите необходимые изменения. 

    | Настройки | Значение |
    | -- | -- |
    | Валюта | **Евро** |

8. Щелкните **Далее**.

# <a name="task-2-review-the-results-and-save-a-copy"></a>Задача 2. Просмотр результатов и сохранение копии

В этой задаче мы рассмотрим рекомендации по экономии средств и скачаем отчет. 

1. Ознакомьтесь с рекомендациями и визуализациями по экономии средств Azure.

    | Настройки | Значение |
    | -- | -- |
    | Временной интервал| **3 года** |
    | Регион | **Северная Европа** |

2. Чтобы изменить предоставленную вами информацию, перейдите в конец страницы и нажмите кнопку **Назад**. 

3. Чтобы сохранить или распечатать копию отчета в формате PDF, нажмите кнопку **Скачать**.

    ![Screenshot of the report pane of the tco calculator in Azure. The highlighted and completed input fields indicates how set the tco calculator timeframe to three years and the region to north europe. A graph shows the cost of on-premises infrastructure and workloads off-set against the reduced cost of using Azure.](../images/2001.png)

Congratulations! You have used the TCO Calculator to generate a cost comparison report for an on-premises environment.
