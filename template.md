# Спецификация требований к программному обеспечению
## Проект "GyGym"

Версия 0.1  
Подготовлен Фурсой И. И.  
КубГУ ФКТиПМ 36/1  
26.03.2021  

Таблица контента
=================
* [Лист регистраций изменений](#лист-регистраций-изменений)
* 1 [Вступление](#1-вступление)
  * 1.1 [Цель документа](#11-цель-документа)
  * 1.2 [Назначение ПО](#12-назначение-по)
  * 1.3 [Определения, акронимы и сокращения](#13-определения-акронимы-и-сокращения)
  * 1.4 [Использованные источники](#14-использованные-источники)
  * 1.5 [Обзор документа](#15-обзор-документа)
* 2 [Обзор продукта](#2-обзор-продукта)
  * 2.1 [Перспектива продукта](#21-перспектива-продукта)
  * 2.2 [Функции продукта](#22-функции-продукта)
  * 2.3 [Ограничения продукта](#23-ограничения-продукта)
  * 2.4 [Характеристики пользователя](#24-характеристики-пользователя)
  * 2.5 [Предположения и зависимости](#25-предположения-и-зависимости)
  * 2.6 [Распределение требований](#26-распределение-требований)
* 3 [Требования](#3-требования)
  * 3.1 [Внешние интерфейсы](#31-внешние-интерфейсы)
    * 3.1.1 [Интерфейсы пользователя](#311-интерфейсы-пользователя)
    * 3.1.2 [Аппаратные интерфейсы](#312-аппаратные-интерфейсы)
    * 3.1.3 [Программные интерфейсы](#313-программные-интерфейсы)
  * 3.2 [Функциональные](#32-функциональные)
  * 3.3 [Качество обслуживания](#33-качество-обслуживания)
    * 3.3.1 [Производительность](#331-производительность)
    * 3.3.2 [Безопасность](#332-безопасность)
    * 3.3.3 [Надежность](#333-надежность)
    * 3.3.4 [Доступность](#334-доступность)
  * 3.4 [Гибкость](#34-гибкость)
  * 3.5 [Дизайн и реализация](#35-дизайн-и-реализация)
    * 3.5.1 [Инсталяция](#351-инсталяция)
    * 3.5.2 [Дистрибуция](#352-дистрибуция)
    * 3.5.3 [Ремонтопригодность](#353-ремонтопригодность)
    * 3.5.4 [Возможность повторного использования](#354-возможность-повторного-использования)
    * 3.5.5 [Портативность](#355-портативность)
    * 3.5.6 [Расходы](#356-расходы)
    * 3.5.7 [Сроки выполнения](#357-сроки-выполнения)
    * 3.5.8 [Доказательство концепции](#358-доказательство-концепции)
* 4 [Верификация](#4-верификация)
* 5 [Приложения](#5-приложения)

## Лист регистраций изменений
| Название | Дата    | Причина             | Версия    |
| -------- | ------- | ------------------- | --------- |
|          |         |                     |           |
|          |         |                     |           |
|          |         |                     |           |

## 1. Вступление

### 1.1 Цель документа
Целью данного документа является описание информационной системы "GyGym" для её разработчиков.

### 1.2 Назначение ПО
Назначение информационной системы "GyGym": автоматизация бизнес-процессов фитнес-клуба.
Содержание продукта: клиент-серверное веб-приложение. 

### 1.3 Определения, акронимы и сокращения
- ПО: программное обеспечение
- ЯП: язык программирования
- ОС: операционная система
- Информационная система: система, предназначенная для хранения, поиска и обработки информации, и соответствующие организационные ресурсы (человеческие, технические, финансовые и т. д.), которые обеспечивают и распространяют информацию

### 1.4 Использованные источники
- [Законодательство Российской Федерации](#)
- [Стандарт IEEE 29148-2011](#)
- [Внутренний регламент компании](#)

### 1.5 Обзор документа
Далее в документе идет общий обзор продукта, затем располагается блок с описанием требований к информационной системе, а после - описание механизма верификации разработанной системы и список приложений к документу, содержащий те или иные материалы, использованные при анализе и проектировании системы в целом.

## 2. Обзор продукта

### 2.1 Перспектива продукта
Информационная система является новым автономным продуктом, который призван обеспечить автоматизацию внутренних бизнес-процессов компании, путем взаимодействия как со стандартными уже используемым ранее в работе ПО (Microsoft Excel 2013, Microsoft Word 2010 и т. п.), так и с физическим оборудованием (принтерами, сканерами и т.п.).

### 2.2 Функции продукта
* Основные функции:
  * Организация подсистемы идентификации, аутентификации и авторизации пользователей, которая служит для контроля доступа пользователей приложения к тем или иным данным и функциям.
  * Организация подсистемы управления, которая служит для реализации функций директора, выполняет обслуживание функционала, продемонстрированного в прототипе интерфейса директора.
  * Организация подсистемы администрирования, которая служит для реализации функций администратора, выполняет обслуживание функционала, продемонстрированного в прототипе интерфейса администратора.
  * Организация подсистемы бухгалтерии, которая служит для реализации функций бухгалтера, выполняет обслуживание функционала, продемонстрированного в прототипе интерфейса бухгалтера.
  * Организация подсистемы менеджмента, которая служит для реализации функций менеджера, выполняет обслуживание функционала, продемонстрированного в прототипе интерфейса менеджера.

### 2.3 Ограничения продукта
- Поддержка стандартного пакета Microsoft Office
- Возможность работы с принтерами Asus SX-2013
- Возможность администрирования базы данных системным адмнистратором сети
- Реализация интуитивно понятного интерфейса согласно составленным макетам приложения
- Использование ЯП Python 3 и Javascript в купе с архитектурным паттерном MVC

### 2.4 Характеристики пользователя
Минимальные требования для пользователя системы: базовая компьютерная грамотность и владение пакетом Microsoft Excel на начальном уровне.

* Классы пользователей
  - Директор: владелец бизнеса
  - Администратор: администратор того или иного фитнес-центра
  - Бухгалтер: бухгалтер компании
  - Менедежер: сотрудник по работе с менеджментом процессов компании

Каждый класс пользователь использует свой интерфейс взаимодействия с программой.

### 2.5 Предположения и зависимости
* Стандартный пакет Microsoft Office
* Принтеры и сканеры фирмы ASUS
* ОС Macintosh

### 2.6 Распределение требований
Требования выполняются согласно порядку, указанному в [таблице 1](#)

## 3. Требования
> This section specifies the software product's requirements. Specify all of the software requirements to a level of detail sufficient to enable designers to design a software system to satisfy those requirements, and to enable testers to test that the software system satisfies those requirements.

> The specific requirements should:
* Be uniquely identifiable.
* State the subject of the requirement (e.g., system, software, etc.) and what shall be done.
* Optionally state the conditions and constraints, if any.
* Describe every input (stimulus) into the software system, every output (response) from the software system, and all functions performed by the software system in response to an input or in support of an output.
* Be verifiable (e.g., the requirement realization can be proven to the customer's satisfaction)
* Conform to agreed upon syntax, keywords, and terms.

### 3.1 Внешние интерфейсы
> This subsection defines all the inputs into and outputs requirements of the software system. Each interface defined may include the following content:
* Name of item
* Source of input or destination of output
* Valid range, accuracy, and/or tolerance
* Units of measure
* Timing
* Relationships to other inputs/outputs
* Screen formats/organization
* Window formats/organization
* Data formats
* Command formats
* End messages

#### 3.1.1 Интерфейсы пользователя
Define the software components for which a user interface is needed. Describe the logical characteristics of each interface between the software product and the users. This may include sample screen images, any GUI standards or product family style guides that are to be followed, screen layout constraints, standard buttons and functions (e.g., help) that will appear on every screen, keyboard shortcuts, error message display standards, and so on. Details of the user interface design should be documented in a separate user interface specification.

Could be further divided into Usability and Convenience requirements.

#### 3.1.2 Аппаратные интерфейсы
Describe the logical and physical characteristics of each interface between the software product and the hardware components of the system. This may include the supported device types, the nature of the data and control interactions between the software and the hardware, and communication protocols to be used.

#### 3.1.3 Программные интерфейсы
Describe the connections between this product and other specific software components (name and version), including databases, operating systems, tools, libraries, and integrated commercial components. Identify the data items or messages coming into the system and going out and describe the purpose of each. Describe the services needed and the nature of communications. Refer to documents that describe detailed application programming interface protocols. Identify data that will be shared across software components. If the data sharing mechanism must be implemented in a specific way (for example, use of a global data area in a multitasking operating system), specify this as an implementation constraint.

### 3.2 Функциональные
> This section specifies the requirements of functional effects that the software-to-be is to have on its environment.

### 3.3 Качество обслуживания
> This section states additional, quality-related property requirements that the functional effects of the software should present.

#### 3.3.1 Производительность
If there are performance requirements for the product under various circumstances, state them here and explain their rationale, to help the developers understand the intent and make suitable design choices. Specify the timing relationships for real time systems. Make such requirements as specific as possible. You may need to state performance requirements for individual functional requirements or features.

#### 3.3.2 Безопасность
Specify any requirements regarding security or privacy issues surrounding use of the product or protection of the data used or created by the product. Define any user identity authentication requirements. Refer to any external policies or regulations containing security issues that affect the product. Define any security or privacy certifications that must be satisfied.

#### 3.3.3 Надежность
Specify the factors required to establish the required reliability of the software system at time of delivery.

#### 3.3.4 Доступность
Specify the factors required to guarantee a defined availability level for the entire system such as checkpoint, recovery, and restart.

### 3.4 Гибкость
Specify the requirements derived from existing standards or regulations, including:  
* Report format
* Data naming
* Accounting procedures
* Audit tracing

For example, this could specify the requirement for software to trace processing activity. Such traces are needed for some applications to meet minimum regulatory or financial standards. An audit trace requirement may, for example, state that all changes to a payroll database shall be recorded in a trace file with before and after values.

### 3.5 Дизайн и реализация

#### 3.5.1 Инсталяция
Constraints to ensure that the software-to-be will run smoothly on the target implementation platform.

#### 3.5.2 Дистрибуция
Constraints on software components to fit the geographically distributed structure of the host organization, the distribution of data to be processed, or the distribution of devices to be controlled.

#### 3.5.3 Ремонтопригодность
Specify attributes of software that relate to the ease of maintenance of the software itself. These may include requirements for certain modularity, interfaces, or complexity limitation. Requirements should not be placed here just because they are thought to be good design practices.

#### 3.5.4 Возможность повторного использования
<!-- TODO: come up with a description -->

#### 3.5.5 Портативность
Specify attributes of software that relate to the ease of porting the software to other host machines and/or operating systems.

#### 3.5.6 Расходы
Specify monetary cost of the software product.

#### 3.5.7 Сроки выполнения
Specify schedule for delivery of the software product.

#### 3.5.8 Доказательство концепции
<!-- TODO: come up with a description -->

## 4. Верификация
> This section provides the verification approaches and methods planned to qualify the software. The information items for verification are recommended to be given in a parallel manner with the requirement items in Section 3. The purpose of the verification process is to provide objective evidence that a system or system element fulfills its specified requirements and characteristics.

<!-- TODO: give more guidance, similar to section 3 -->
<!-- ieee 15288:2015 -->

## 5. Приложения
