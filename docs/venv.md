# **Туториал: Настройка виртуального окружения и установка зависимостей на Windows, Linux и macOS**

## **1. Установка и активация виртуальной среды**

### **1.1 Установка модуля для работы с виртуальными окружениями**
Перед созданием виртуального окружения убедитесь, что модуль установлен.

#### **Для Linux:**
```bash
sudo apt install -y python3-venv
```

#### **Для macOS (если `python3-venv` отсутствует):**
```bash
brew install python3
```
`venv` идет в комплекте с Python 3.3+, так что дополнительная установка обычно не требуется.

#### **Для Windows:**
Python 3.3+ уже включает модуль `venv`, но если используете `virtualenv`, установите его:
```powershell
pip install virtualenv
```

---

### **1.2 Создание виртуального окружения**
Выберите один из вариантов:

#### **Для Python 3.11 (Linux/macOS/Windows):**
```bash
virtualenv .venv -p python3.11
```

#### **Для стандартного `venv`:**
```bash
python3 -m venv .venv
```

---

### **1.3 Активация виртуального окружения**

#### **На Windows (PowerShell / CMD):**
```powershell
.venv\Scripts\activate
```

#### **На Linux / macOS (Bash/Zsh):**
```bash
source .venv/bin/activate
```

> 💡 **Для MacBook с чипами M1/M2**: Если возникают ошибки, попробуйте:  
> ```bash
> python3 -m venv .venv --without-pip
> source .venv/bin/activate
> curl https://bootstrap.pypa.io/get-pip.py | python
> ```

После активации виртуального окружения ваш терминал изменится, и в начале строки появится `(venv)`, указывая, что среда активирована.

---

### **1.4 Решение ошибки "Activate.ps1 не имеет цифровой подписи" (Windows)**
Если при активации среды появляется ошибка:
```
Activate.ps1 не имеет цифровой подписи. Вы не можете запустить этот скрипт в текущей системе.
```
Необходимо разрешить выполнение скриптов:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
```
Подтвердите изменение, нажав **"Y"**.

---

## **2. Выбор интерпретатора Python**
Если используете **VS Code**, выберите интерпретатор вручную:
1. Открыть **Command Palette** (`Ctrl + Shift + P`).
2. Ввести `Python: Select Interpreter`.
3. Выбрать интерпретатор, находящийся внутри `.venv`.

---

## **3. Обновление pip и установка пакетов**

### **3.1 Обновление pip**
Перед установкой пакетов рекомендуется обновить `pip`:
```bash
python -m pip install --upgrade pip
```

---

### **3.2 Установка отдельных пакетов**
```bash
pip install matplotlib
```

---

### **3.3 Установка нескольких пакетов сразу**
```bash
pip install numpy scipy matplotlib ipython scikit-learn pandas
```

---

### **3.4 Установка пакетов из `requirements.txt`**
Если у вас есть файл `requirements.txt`, выполните:
```bash
pip install -r requirements.txt
```

---

## **4. Деактивация виртуального окружения**
Когда закончите работу, отключите виртуальное окружение:
```bash
deactivate
```

---

## **5. Дополнительные команды для управления окружением**
- **Проверка установленных пакетов в окружении:**
  ```bash
  pip list
  ```
- **Сохранение текущих зависимостей в файл `requirements.txt`:**
  ```bash
  pip freeze > requirements.txt
  ```
- **Удаление виртуального окружения:**
  ```bash
  rm -rf .venv  # Linux/macOS
  rmdir /s /q .venv  # Windows (CMD)
  ```

---

### **6. Специальные инструкции для macOS (Apple Silicon M1/M2)**
Если у вас MacBook с чипом **M1/M2**, некоторые пакеты могут требовать дополнительных шагов.

#### **6.1 Обновление Homebrew и установка зависимостей**
```bash
brew update
brew install python3
brew install openblas
```

#### **6.2 Установка пакетов с поддержкой Apple Silicon**
Иногда `pip install` может использовать старые колеса (`wheels`), не оптимизированные для ARM64. Решение:
```bash
pip install --no-binary :all: numpy scipy pandas
```

---

Теперь ваше виртуальное окружение настроено, и вы можете работать с проектом! 🚀