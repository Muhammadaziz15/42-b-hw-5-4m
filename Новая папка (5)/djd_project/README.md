# TaskFlow

Базовый проект на Django с интерфейсом на Bootstrap 5.

---

## Модели задач

- `Task.title` — название задачи (до 150 символов).
- `Task.description` — необязательное подробное описание.
- `Task.author` — внешний ключ на пользователя Django; при удалении пользователя его задачи удаляются.
- `Task.category` — необязательный внешний ключ на категорию; при удалении категории задача сохраняется без категории.
- `Task.created_at` — дата и время создания, заполняются автоматически.
- `Task.due_date` — необязательный срок выполнения.
- `Task.status` — статус «Новая», «В работе» или «Завершена»; по умолчанию «Новая».
- `Task.priority` — приоритет от 1 до 5; по умолчанию 3.
- `Category.name` — уникальное название категории, например «Учёба», «Работа» или «Личное».

Задачи отображаются от новых к старым и управляются через `/admin/`. В списке задач доступны фильтры по статусу и приоритету, поиск по названию и быстрое редактирование статуса и приоритета.

---

## Структура проекта

```text
django-project/
├── manage.py
├── requirements.txt
├── .gitignore
├── README.md
├── core/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── tasks/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   └── migrations/
│       └── __init__.py
├── templates/
│   ├── base.html
│   └── tasks/
│       └── task_list.html
└── static/
    └── css/
        └── style.css
```

---

## Инструкция по запуску (Windows PowerShell)

Выполняйте команды в терминале внутри папки `django-project`:

### 1. Создание виртуального окружения
```powershell
python -m venv venv
```

### 2. Активация виртуального окружения
```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Установка зависимостей
```powershell
pip install -r requirements.txt
```

### 4. Выполнение миграций
```powershell
python manage.py migrate
```

### 5. Создание суперпользователя
```powershell
python manage.py createsuperuser
```

### 6. Запуск сервера разработки
```powershell
python manage.py runserver
```

### 7. Доступ к проекту
- Панель управления: [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)
