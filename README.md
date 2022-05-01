# 5.1. Введение в виртуализацию. Типы и функции гипервизоров. Обзор рынка вендоров и областей применения.

## Решение 1.
 Полная виртуализация отличается от паравиртуализации, потому что при полной виртуализации немодифицированная ОС работает полностью изолированно. С другой стороны, при паравиртуализации виртуальная машина не изолирует ОС полностью, а модифицирует ее, чтобы сделать ее совместимой с определенными API.
 Виртуализация на уровне ОС позволяет виртуализировать физические серверы на уровне ядра операционной системы. Слой виртуализации ОС обеспечивает изоляцию и безопасность ресурсов между различными контейнерами. Слой виртуализации делает каждый контейнер похожим на физический сервер. каждый контейнер обслуживает приложения в нем и рабочую нагрузку.
 В аппаратной виртуализации базовый слой - гипервизор. Этот слой загружает на сервер и обеспечивает взаимодействие между аппаратным обеспечением сервера и виртуальными машинами. Чтобы предоставить ресурсы виртуальным машинам, обеспечивает их виртуализация на сервере. Виртуальные машины запускают свою собственную копию операционной системы и приложений на виртуализированном оборудовании. 
 ## Решение 2.
 Высоконагруженная база данных, чувствительная к отказу- я бы выбрал физические сервера, так как не хотел, чтоб если произойдет отказ оборудования, я потерял все данные. Легко настроить резервирования. Восстановления данных с дисках с помощью различных утилит возможна. А востановить виртуальную машину и потом достать от туда данные значительно усложняет процесс.
 Различные web-приложения - я бы выбрал виртуализация уровня ОС.А именно докер. Докер запущенный не с root правами, самый удачный выбор. 
Windows системы для использования бухгалтерским отделом - так как речь идёт о Windows, то только использования Hyper-V а значит только аппаратной виртуализации обеспечивающая создание изолированных программных окружений для использования в качестве виртуальных машин - паравиртуализация.
Системы, выполняющие высокопроизводительные расчеты на GPU - паравиртуализация, таким образом мы получаем доступ к нашей видеокарте из разных систем, и можем запускать расчеты значительно в большем кол-ве. 

## Решение 3.
1 сценарий: Hyper-V неограниченного количества гостевых операционных систем делают выбор привлекательным для тех, кому нужна тесная интеграция с экосистемой MS Windows и знакомый интерфейс.
2 сценарий: я бы использовал XEN во первых он open source, во вторых поддерживает установку и Linux систем, так и Windows. Очень зрелый и готовый продукт. универсальный гипервизор.
3 сценарий: Так как речь итдёт о Windows, то можно использовать Hyper-V либо VirtaulBox. Второй бесплатный, открытй простой в обращении. 
4 сценарий: OpenNebula отлично подойдет, так как я знаком с системами Debian Ubuntu остановлю выбор на данном программном обеспечении, которое может быть использовано для создания инфракстутур облачных сервисов

## Решение 4.
Современному бизнесу ежедневно приходится иметь дело с различными приложениями, будь то сервер CRM, корпоративный каталог (Active Directory) или сервер базы данных и т.д. В 8 из 10 случаев, серверный ландшафт имеет свойства гетерогенной среды. 
Основные проблемы:
- сложность модернизации гетерогенной среды
- сложность обеспечения требуемых параметров сервиса на оборудовании
- сложность и трудозатратность обеспечения стандартов ИБ и их согласованности на нескольких сотнях единиц серверов и сетевого оборудования
- сложности в оперативности создания новых узлов ИТ ифраструктуры в интересах бизнеса, заказчика.
Для минимализации, это использование однотипных операционных систем, одного и того е семейства. Уменьшение кол-ва иных ОС, по возможности. Для большого кол-ва виртуальных машин различных ОС необходимо большее кол-во инженеров с различными навыками. Я бы сделал отдельные серверы для семейства Windows и Unix систем. да я бы использовал, но в случае невозможности перенести ПО на Unix семейство. К примеру не все программы работают на Linux.