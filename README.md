

# 📘 Django Блог — Учебный проект

![Django](https://img.shields.io/badge/django-%23092E20?style=for-the-badge&logo=django&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/postgresql-%234169E1?style=for-the-badge&logo=postgresql&logoColor=white)

> Проект реализован во время обучения на джанго.

---

## ✅ Возможности

- 📄 Канонические URL-адреса для моделей
- 🔍 SEO-оптимизированные URL-адреса постов
- 📖 Постраничная разбивка списка постов
- 👤 Отправка постов по email через SMTP
- 💬 Комментирование постов через форму модели
- 🔐 Админ-панель Django
- 🗂️ Фикстуры: загрузка и выгрузка данных
- 🔍 Полный текстовый поиск через PostgreSQL
- 🧱 Поддержка миграций Django
- 🧪 Базовые тесты

---

## 🧰 Технологии

| Технология           | Версия/Использование                     |
|----------------------|------------------------------------------|
| Python               | 3.10+                                    |
| Django               | 5.2.3                                    |
| PostgreSQL           | Реляционная база данных                  |
| Django ORM           | Работа с моделью данных                  |
| Django Templates     | Генерация HTML                           |
| Django Forms         | Валидация и обработка форм               |
| Django Admin         | Интерфейс управления контентом          |
| Django Email         | Отправка по email                        |
| Markdown             | Поддержка форматирования в шаблонах     |
| PostgreSQL Full Text | Поиск по заголовкам и тексту статей      |

---

## 📁 Структура проекта

```
hhanqq-python-django-myblog/
├── README.md
└── main/
    ├── manage.py
    ├── mysite_data.json
    ├── .gitignore
    ├── blog/                 # Приложение блога
    │   ├── migrations/
    │   ├── static/
    │   ├── templates/
    │   ├── templatetags/
    │   ├── models.py
    │   ├── views.py
    │   ├── urls.py
    │   ├── forms.py
    │   └── admin.py
    └── main/                 # Настройки проекта
        ├── settings.py
        ├── urls.py
        └── wsgi.py
```

---

## 📝 Функционал

### Для пользователей:
- Просмотр списка опубликованных постов
- Чтение детальной страницы поста
- Добавление комментариев к постам
- Поиск постов по ключевым словам
- Отправка статьи другому человеку по email

### Для администраторов:
- Создание, редактирование и удаление постов
- Управление комментариями
- Просмотр логов изменений через админ-панель

---

## 📦 Модели

### `Post` — модель поста
- `title`: заголовок
- `slug`: уникальный идентификатор
- `author`: внешний ключ на пользователя
- `body`: текст поста
- `publish`, `created`, `updated`: даты
- `status`: черновик / опубликовано

### `Comment` — модель комментария
- `post`: связь с постом
- `name`, `email`: автор комментария
- `body`: текст комментария
- `created`, `updated`: время создания
- `active`: активность комментария

---

## 🌐 Роутинг (URLs)

| URL                         | Описание                          |
|----------------------------|-----------------------------------|
| `/blog/`                   | Список постов                     |
| `/blog/<year>/<month>/<day>/<slug>/` | Детализация поста       |
| `/blog/<id>/share/`        | Отправить пост по email           |
| `/blog/<id>/comment/`      | Оставить комментарий              |
| `/blog/search/`            | Поиск по постам                   |

---

## 🎨 Шаблоны (Templates)

Используются шаблоны Django:
- `base.html` — основной шаблон
- `post/list.html` — список постов
- `post/detail.html` — детальная страница
- `post/share.html` — форма отправки по email
- `post/comment.html` — форма комментария
- `post/search.html` — поиск постов

---

## 📬 Рассылка email

Реализована через SMTP-сервер Mail.ru:
- Использование `send_mail()`
- Настройки в `.env` или `settings.py`

---

## 🔍 Поиск

Реализован через **PostgreSQL Full-Text Search**:
- Поиск по заголовкам и телу постов
- Использование `SearchVector`

---

## 📦 Зависимости

```txt
Django==5.2.3
psycopg2-binary
python-decouple
markdown
```

