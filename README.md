# Блог от Лизы

Блог на Django, серверная часть

## Запуск

Для запуска блога у вас уже должен быть установлен Python 3.

- Скачайте код
- Установите зависимости командой `pip install -r requirements.txt`
- Запустите сервер командой `python3 manage.py runserver`

После этого переходите по ссылке 127.0.0.1:8000, вы должны увидеть главную страницу.

## Документация

### Главная

Название страницы `index`

Страница по адресу [ссылка](127.0.0.1:8000). К шаблонизации в неё отдаётся 2 переменные: `most_popular_posts` и `fresh_posts`.
Обе переменные — это списки из **постов**. Каждый пост — это словарь такого вида:

#### Пост

Это словарь со следующими ключами:

* **title** — заголовок поста
* **text** — текст поста
* **author** — автор поста (строка с именем)
* **comments_amount** — количество комментариев под постом (число)
* **image_url** — ссылка на картинку поста
* **published_at** — Когда опубликован (Объект datetime)
* **slug** — ссылка на пост (само название)

Пример поста:
```
{
    'title': 'Are You Preparing Your Kids for the Real World?',
    'text': 'We baby our kids like infants; we coddle them like delicate crystal; ...',
    'author': 'Frank Sonnenberg',
    'comments_amount': 138,
    'image_url': 'image_are-you-preparing-your-kids-for-the-real-world.jpg',
    'published_at': datetime.datetime(2017, 6, 4, 2, 9, tzinfo=<UTC>),
    'slug': 'are-you-preparing-your-kids-for-the-real-world'
}
```

### Страница поста

Название страницы `post_detail`. Требует передать `slug` поста.

Пример страницы [ссылка](http://127.0.0.1:8000/post/5-qualities-of-great-leaders). К шаблонизации отдаются переменные `post` и `most_popular_posts`. Второе — список постов, такой же, как в разделе [про главную](#Главная).

`post` — это словарь, похожий на посты на главной, но с отличиями:

* **title** — заголовок поста
* **text** — текст поста
* **author** — автор поста (строка с именем)
* **comments** — **список комментариев**
* **likes_amount** — количество лайков на посте
* **image_url** — ссылка на картинку поста
* **published_at** — Когда опубликован (Объект datetime)
* **slug** — ссылка на пост (само название)

Каждый комментарий — это словарь вида:

* **text** — текст комментария
* **published_at** — Когда опубликован (Объект datetime)
* **author** — автор поста (строка с именем)

### Контакты

Название страницы `contacts`

Страница по адресу [ссылка](127.0.0.1:8000/contacts). К шаблонизации в неё отдаётся только переменная `html_map`. Это HTML-карта.

## Цели проекта

Код написан в учебных целях — это урок в курсе по Python и веб-разработке на сайте [Devman](https://dvmn.org).
