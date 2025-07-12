# 🏢 MainLabBD - База данных управления предприятием

![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoft%20sql%20server&logoColor=white)
![SSIS](https://img.shields.io/badge/SSIS-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91?style=for-the-badge&logo=visual%20studio&logoColor=white)
![JSON](https://img.shields.io/badge/json-5E5C5C?style=for-the-badge&logo=json&logoColor=white)
![XML](https://img.shields.io/badge/XML-FF6600?style=for-the-badge&logo=xml&logoColor=white)

> 🎯 Комплексная система управления данными предприятия с использованием SQL Server Integration Services (SSIS)

## 📋 Описание проекта

**MainLabBD** - это лабораторный проект базы данных для управления предприятием, включающий в себя:

- 👥 **Управление сотрудниками** - полная информация о персонале
- 🏢 **Структура отделов** - иерархия и организационная структура  
- 📊 **Управление проектами** - отслеживание и координация проектов
- ✅ **Система задач** - планирование и контроль выполнения

### ✨ Ключевые возможности

- 🔄 **ETL-операции** с использованием SSIS пакетов
- 📁 **Мультиформатные данные** (JSON, XML, SQL, Excel)
- 🔗 **Связанные сущности** с нормализованной структурой
- 📈 **Аналитические возможности** и отчетность

## 🏗️ Архитектура проекта

```
MainLabBD/
├── 📄 MainLabBD.sln           # Solution file
├── 📦 MainLabBD.dtproj        # SSIS Project
├── 🔧 Package.dtsx            # ETL Package
├── 🗄️ MainLabBD.database      # Database Schema
├── 📊 Data Files/
│   ├── 👥 Employees.xml       # Данные сотрудников
│   ├── 🏢 Departments.json    # Информация об отделах
│   ├── ✅ Tasks.sql           # SQL-скрипт с задачами
│   └── 📋 Projects.xlsx       # Данные проектов
└── ⚙️ Project.params          # Параметры проекта
```

## 🗂️ Структура данных

### 👥 Сотрудники (Employees)
```xml
<record>
    <FullName>Имя Фамилия</FullName>
    <Username>username</Username>
    <Password>encrypted_password</Password>
    <HireDate>YYYY/MM/DD</HireDate>
    <DepartmentID>ID отдела</DepartmentID>
    <ProjectID>ID проекта</ProjectID>
    <TaskID>ID задачи</TaskID>
</record>
```

### 🏢 Отделы (Departments)
```json
{
    "DepartmentName": "Название отдела",
    "EmployeCount": 50,
    "DirectorID": 123
}
```

### ✅ Задачи (Tasks)
```sql
TaskName TEXT,
ProjectID INT,
Status VARCHAR(11),  -- 'Done', 'In_Progress'
Difficulty VARCHAR(6) -- 'easy', 'medium', 'hard', 'expert'
```

## 🚀 Установка и настройка

### 📋 Предварительные требования

- ![SQL Server](https://img.shields.io/badge/SQL%20Server-2019+-blue) SQL Server 2019 или выше
- ![Visual Studio](https://img.shields.io/badge/Visual%20Studio-2019+-purple) Visual Studio с поддержкой SSIS
- ![SSDT](https://img.shields.io/badge/SSDT-Latest-green) SQL Server Data Tools (SSDT)

### ⚡ Быстрый старт

1. **Клонирование репозитория**
   ```bash
   git clone https://github.com/Kwameldx666/MainLabBD.git
   cd MainLabBD
   ```

2. **Открытие проекта**
   ```bash
   # Откройте MainLabBD.sln в Visual Studio
   ```

3. **Настройка подключения к базе данных**
   - Откройте `Project.params`
   - Настройте строку подключения
   - Обновите параметры сервера

4. **Развертывание пакета SSIS**
   - Щелкните правой кнопкой на проект
   - Выберите "Deploy" → "Deploy Project"
   - Следуйте мастеру развертывания

## 📊 Статистика данных

| 📈 Метрика | 📊 Значение |
|------------|-------------|
| 👥 Сотрудники | 1000+ записей |
| 🏢 Отделы | 10 подразделений |
| 📋 Проекты | 100 активных проектов |
| ✅ Задачи | Различной сложности |

### 🏢 Распределение по отделам

- 🛒 **Sales** - 31 сотрудник
- 📢 **Marketing** - 54 сотрудника  
- 💰 **Finance** - 58 сотрудников
- 👥 **HR** - 57 сотрудников
- 💻 **IT** - 66 сотрудников
- ⚙️ **Operations** - 71 сотрудник
- 📞 **Customer Service** - 87 сотрудников
- 🔬 **Research** - 98 сотрудников
- ⚖️ **Legal** - 27 сотрудников
- 🏛️ **Administration** - 44 сотрудника

## 💡 Использование

### 🔄 Запуск ETL-процесса

```sql
-- Выполнение SSIS пакета
EXEC [SSISDB].[catalog].[start_execution] @execution_id
```

### 📊 Примеры запросов

```sql
-- Получить сотрудников по отделам
SELECT d.DepartmentName, COUNT(e.EmployeeID) as EmployeeCount
FROM Departments d
LEFT JOIN Employees e ON d.DepartmentID = e.DepartmentID
GROUP BY d.DepartmentName

-- Статус выполнения задач
SELECT Status, COUNT(*) as TaskCount
FROM Tasks
GROUP BY Status
```

## 🛠️ Технологии

| Технология | Описание | Версия |
|------------|----------|--------|
| 🗄️ **SQL Server** | Основная СУБД | 2019+ |
| 📦 **SSIS** | Integration Services | Latest |
| 🎨 **Visual Studio** | IDE для разработки | 2019+ |
| 📄 **JSON/XML** | Форматы данных | - |
| 📊 **Excel** | Источник данных | .xlsx |

## 🤝 Участие в разработке

Мы приветствуем ваш вклад в развитие проекта! 

### 📝 Как внести изменения

1. 🍴 Сделайте Fork репозитория
2. 🌿 Создайте ветку для новой функции (`git checkout -b feature/AmazingFeature`)
3. 💾 Зафиксируйте изменения (`git commit -m 'Add some AmazingFeature'`)
4. 📤 Отправьте изменения (`git push origin feature/AmazingFeature`)
5. 🔄 Создайте Pull Request

### 📋 Руководства по стилю

- Используйте meaningful имена для переменных и таблиц
- Документируйте сложные SQL-запросы
- Следуйте conventions SSIS для именования пакетов
- Добавляйте комментарии на русском языке

## 📚 Документация

- 📖 [Руководство по SSIS](https://docs.microsoft.com/en-us/sql/integration-services/)
- 🔧 [SQL Server Documentation](https://docs.microsoft.com/en-us/sql/)
- 💡 [Best Practices для ETL](https://www.sqlshack.com/ssis-best-practices/)

## 📝 Лицензия

Этот проект распространяется под лицензией MIT. Подробности см. в файле [LICENSE](LICENSE).

## 👨‍💻 Автор

**Kwameldx666**
- 🐙 GitHub: [@Kwameldx666](https://github.com/Kwameldx666)
- 📧 Email: [contact@example.com](mailto:contact@example.com)

## 🙏 Благодарности

- Спасибо всем участникам проекта
- Сообщество SQL Server за отличную документацию
- Microsoft за предоставление инструментов SSIS

---

<div align="center">

### 🌟 Если проект оказался полезным, поставьте звезду! ⭐

**[⬆ Вернуться к началу](#-mainlabbd---база-данных-управления-предприятием)**

</div>