# SAP Автоматизация / SAP Automation

### Предупреждение
Этот скрипт предоставляется «как есть» без какой-либо гарантии. Используйте на свой страх и риск.  

### Disclaimer
This script is provided as-is and without any warranty. Use at your own risk.

---

## О проекте / About the Project  
Проект вдохновлён [SAPLOGON_VBS](https://github.com/AkshayNalange/SAPLOGON_VBS ) и расширяет его функционал, добавляя:  
- **Управление подключениями к SAP** (хранение данных, автоматический вход).  
- **Поддержку пользовательских скриптов** (создание, редактирование, запуск).  
- **Интерфейс с графической оболочкой (HTA)** для удобства работы.  

Inspired by [SAPLOGON_VBS](https://github.com/AkshayNalange/SAPLOGON_VBS ), this project adds:  
- **SAP connection management** (data storage, auto-login).  
- **Custom script support** (creation, editing, execution).  
- **Graphical HTA interface** for user convenience.

---

## Функционал / Features  
### Основные возможности:  
1. **Сохранение данных подключения**  
   - Название системы, описание, код сервиса (например, `PRD`), мандант (3 цифры), логин/пароль.  
   - Поддержка автоматического входа (`Auto-Login`).  

2. **Подключение к SAP**  
   - Запуск через `OpenConnection(system, false)` с передачей данных из формы.  
   - Автоматическое заполнение полей ввода (мандант, логин, пароль).  

3. **Управление скриптами**  
   - Создание/редактирование пользовательских скриптов для автоматизации задач в SAP.  
   - Запуск скриптов через SAP GUI Scripting Engine.  

4. **Хранение данных**  
   - Сохранение данных в CSV-файлы (`data.csv` для подключений, `user_scripts.csv` для скриптов).  

### Key Features:  
1. **Connection Data Storage**  
   - System name, description, service code (e.g., `PRD`), mandate (3 digits), login/password.  
   - Auto-login option.  

2. **SAP Connection**  
   - Launch via `OpenConnection(system, false)` with form data.  
   - Automatic field population (mandate, login, password).  

3. **Script Management**  
   - Create/edit custom scripts for SAP task automation.  
   - Run scripts via SAP GUI Scripting Engine.  

4. **Data Storage**  
   - Data saved in CSV files (`data.csv` for connections, `user_scripts.csv` for scripts).  

---

## Подробности подключения / Connection Details  
### `OpenConnection(system, false)`  
- **Параметры / Parameters**:  
  - `system`: Код сервиса SAP (например, `PRD`, `DEV`). Должен совпадать с записью в SAP Logon.  
  - `false`: Флаг, указывающий, создавать ли новое соединение (если `false`, всегда открывается новое).  

- **Дополнительные данные / Additional Data Required**:  
  ```javascript
  session.findById("wnd[0]/usr/txtRSYST-MANDT").text = client; // Мандант (3 цифры)  
  session.findById("wnd[0]/usr/txtRSYST-BNAME").text = username; // Логин  
  session.findById("wnd[0]/usr/pwdRSYST-BCODE").text = password; // Пароль  

  ```

---

### Требования
- **Windows** (только для HTA и ActiveX).  
- **SAP GUI для Windows** с включённым Scripting Engine.  
- **Включить ActiveX** в настройках безопасности. 

### Requirements
- **Windows** (HTA and ActiveX only).  
- **SAP GUI for Windows** with enabled Scripting Engine.  
- **ActiveX enabled** in security settings.  


---
### Примечания  
- Для работы требуется включить поддержку ActiveX в настройках безопасности Windows.  
- Все данные хранятся локально в CSV-файлах.  

### Notes  
- **ActiveX must be enabled** in Windows security settings for operation.  
- All data is stored locally in CSV files.  

---

### Участие в проекте
Если вы обнаружили ошибки или хотите предложить улучшения, откройте issue или отправьте pull request.  
###Contributing  
If you find any issues or have suggestions for improvement, feel free to open an issue or submit a pull request.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)  ![Sap logon - Windows 10](https://img.shields.io/badge/Sap%20Logon%20730-brightgreen)  ![Windows 10](https://img.shields.io/badge/Windows%2010-blue)
