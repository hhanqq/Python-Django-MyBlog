

# 📘 Django Блог — Учебный проект

![Django](https://img.shields.io/badge/django-%23092E20?style=for-the-badge&logo=django&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/postgresql-%234169E1?style=for-the-badge&logo=postgresql&logoColor=white)

> Это учебное веб-приложение "Блог", написанное с использованием **Python** и фреймворка **Django**, с поддержкой публикации статей, добавления комментариев, поиска постов и отправки статей по email.

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

---

## 🚀 Как запустить проект

1. 📥 Клонируйте репозиторий:
   ```bash
   git clone https://github.com/ваше-имя/hhanqq-python-django-myblog.git
   cd hhanqq-python-django-myblog
   ```

2. ⚙️ Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. 📄 Настройте `.env` файл:
   ```
   DB_NAME=your_db_name
   DB_USER=your_db_user
   DB_PASSWORD=your_password
   DB_HOST=localhost
   EMAIL_HOST_USER=youremail@mail.ru
   EMAIL_HOST_PASSWORD=your_email_password
   DEFAULT_FROM_EMAIL=youremail@mail.ru
   ```

4. 🔄 Примените миграции:
   ```bash
   python manage.py migrate
   ```

5. 🔐 Создайте суперпользователя:
   ```bash
   python manage.py createsuperuser
   ```

6. ▶️ Запустите сервер:
   ```bash
   python manage.py runserver
   ```

7. 🌐 Перейдите по ссылке: [http://127.0.0.1:8000/blog/](http://127.0.0.1:8000/blog/)

---

## 📜 Лицензия

MIT License — см. [LICENSE](LICENSE) для подробностей.

---

## 📩 Поддержка

Если у вас есть вопросы или идеи, вы можете создать issue в репозитории или написать мне в [Telegram](https://t.me/ваше_имя).

---

Хочешь, я также создам:

- [ ] Бейджики GitHub (например, build status, license, version)
- [ ] Лого/баннер для README
- [ ] Скриншоты интерфейса

Напиши, если хочешь продолжить оформление! 😊
