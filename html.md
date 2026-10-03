# Шпаргалка: HTML

## Что такое HTML
**HTML** (HyperText Markup Language) — язык гипертекстовой разметки.  
Он **не программирует**, а описывает структуру веб-страницы: где заголовок, абзац, картинка, таблица или форма.  
Браузер читает HTML-теги и отображает страницу.

---

## Структура HTML-документа

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Заголовок вкладки</title>
</head>
<body>
    <!-- Видимое содержимое страницы -->
</body>
</html>
```

| Часть | Назначение |
|-------|------------|
| `<!DOCTYPE html>` | Говорит браузеру, что это HTML5 |
| `<html>` | Корневой элемент |
| `<head>` | Служебная информация (кодировка, заголовок вкладки, стили) |
| `<title>` | Название вкладки в браузере |
| `<body>` | Всё видимое содержимое |

---

## Основные теги текста

| Тег | Назначение | Пример |
|-----|------------|--------|
| `<h1>…<h6>` | Заголовки (6 уровней) | `<h1>Заголовок</h1>` |
| `<p>` | Абзац | `<p>Текст</p>` |
| `<strong>` | Важный текст (жирный) | `<strong>Важно!</strong>` |
| `<em>` | Акцент (курсив) | `<em>Выделение</em>` |
| `<br>` | Перенос строки | `Строка 1<br>Строка 2` |
| `<hr>` | Горизонтальная линия | `<hr>` |
| `<blockquote>` | Цитата | `<blockquote>Текст</blockquote>` |
| `<code>` | Код в строке | `<code>print()</code>` |
| `<pre>` | Сохраняет пробелы и переносы | `<pre>...</pre>` |

```html
<h1>Моя страница</h1>
<p>Это <strong>важный</strong> текст, а это <em>курсив</em>.</p>
<hr>
<p>Второй абзац.<br>И перенос строки.</p>
```

---

## Списки

| Тег | Назначение |
|-----|------------|
| `<ul>` | Маркированный список |
| `<ol>` | Нумерованный список |
| `<li>` | Элемент списка |

```html
<ul>
    <li>Информатика</li>
    <li>Математика</li>
</ul>

<ol>
    <li>Сделать уроки</li>
    <li>Погулять</li>
</ol>
```

**Вложенный список:**
```html
<ul>
    <li>Фрукты
        <ul>
            <li>Яблоки</li>
            <li>Бананы</li>
        </ul>
    </li>
    <li>Овощи
        <ul>
            <li>Морковь</li>
            <li>Картофель</li>
        </ul>
    </li>
</ul>
```

---

## Ссылки

```html
<a href="https://www.google.com">Перейти в Google</a>
<a href="page2.html">Другая страница</a>
<a href="#section1">Перейти к разделу</a>
<a href="https://ya.ru" target="_blank">Яндекс (новая вкладка)</a>
```

| Атрибут | Назначение |
|---------|------------|
| `href` | Адрес ссылки |
| `target="_blank"` | Открыть в новой вкладке |
| `title` | Всплывающая подсказка |

---

## Изображения

```html
<img src="cat.jpg" alt="Котик" width="300">
<img src="https://via.placeholder.com/150" alt="Заглушка">
```

| Атрибут | Назначение |
|---------|------------|
| `src` | Путь к картинке (файл или URL) |
| `alt` | Текст, если картинка не загрузилась |
| `width`, `height` | Размеры |

`<img>` — **одиночный** тег, закрывающий не нужен.

---

## Таблицы

```html
<table border="1">
    <caption>Расписание</caption>
    <tr>
        <th>№</th>
        <th>Предмет</th>
        <th>Кабинет</th>
    </tr>
    <tr>
        <td>1</td>
        <td>Математика</td>
        <td>201</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Информатика</td>
        <td>310</td>
    </tr>
</table>
```

| Тег | Назначение |
|-----|------------|
| `<table>` | Таблица |
| `<caption>` | Заголовок таблицы |
| `<tr>` | Строка |
| `<th>` | Заголовочная ячейка |
| `<td>` | Обычная ячейка |
| `colspan` | Объединить ячейки по горизонтали |
| `rowspan` | Объединить ячейки по вертикали |

---

## Формы

### Контейнер формы

```html
<form action="/submit" method="post">
    <!-- поля формы -->
</form>
```

| Атрибут | Назначение |
|---------|------------|
| `action` | Адрес, куда отправляются данные |
| `method` | `GET` — данные видны в адресной строке; `POST` — скрыты |

---

### `<input>` — универсальное поле

`<input>` — **одиночный** тег. Поведение зависит от `type`.

| Тип | Назначение | Пример |
|-----|------------|--------|
| `text` | Обычный текст | `<input type="text">` |
| `password` | Пароль | `<input type="password">` |
| `email` | Email | `<input type="email">` |
| `number` | Число | `<input type="number" min="1" max="100">` |
| `date` | Дата | `<input type="date">` |
| `checkbox` | Флажок | `<input type="checkbox">` |
| `radio` | Переключатель | `<input type="radio" name="gender">` |
| `file` | Загрузка файла | `<input type="file">` |
| `range` | Ползунок | `<input type="range" min="0" max="10">` |
| `color` | Выбор цвета | `<input type="color">` |
| `hidden` | Скрытое поле | `<input type="hidden" value="123">` |
| `submit` | Кнопка отправки | `<input type="submit" value="Отправить">` |

**Важные атрибуты:**
- `name` — имя поля (нужно для отправки данных).
- `value` — значение по умолчанию.
- `placeholder` — подсказка внутри поля.
- `required` — обязательное поле.
- `disabled` — отключённое поле.
- `readonly` — только для чтения.
- `maxlength` — максимальная длина.

```html
<input type="text" name="username" placeholder="Введите имя" required>
<input type="password" name="password" minlength="6" required>
<input type="email" name="email" placeholder="example@mail.ru">
```

---

### `<label>` — подпись к полю

Связывает текст с полем. Клик по подписи активирует поле.

```html
<label for="name">Имя:</label>
<input type="text" id="name" name="username">
```

Можно обернуть поле внутрь `<label>`:

```html
<label>
    Имя:
    <input type="text" name="username">
</label>
```

---

### `<textarea>` — многострочное поле

```html
<label>Сообщение:</label>
<textarea name="message" rows="5" cols="40" placeholder="Напишите здесь..."></textarea>
```

`<textarea>` — **парный** тег, закрывающий обязателен.

---

### `<select>` — выпадающий список

```html
<select name="grade">
    <option value="5">5 класс</option>
    <option value="6">6 класс</option>
    <option value="7">7 класс</option>
    <option value="8" selected>8 класс</option>
    <option value="9">9 класс</option>
</select>
```

Множественный выбор:

```html
<select name="fruits" multiple>
    <option>Яблоко</option>
    <option>Банан</option>
</select>
```

---

### `<button>` — кнопки

```html
<button type="submit">Отправить</button>
<button type="reset">Очистить</button>
<button type="button">Нажми меня</button>
```

| Тип | Действие |
|-----|----------|
| `submit` | Отправляет форму (по умолчанию) |
| `reset` | Очищает форму |
| `button` | Обычная кнопка (для JS) |

---

### `<fieldset>` и `<legend>` — группировка

```html
<fieldset>
    <legend>Личные данные</legend>
    <label>Имя: <input type="text" name="name"></label><br>
    <label>Email: <input type="email" name="email"></label>
</fieldset>
```

---

### Чекбоксы и радиокнопки

**Чекбоксы** — можно выбрать несколько:

```html
<label><input type="checkbox" name="hobby" value="sport"> Спорт</label>
<label><input type="checkbox" name="hobby" value="music"> Музыка</label>
```

**Радиокнопки** — только один вариант (одинаковый `name`):

```html
<label><input type="radio" name="gender" value="male"> Мужской</label>
<label><input type="radio" name="gender" value="female"> Женский</label>
```

---

## HTML5-валидация

Проверка данных без JavaScript.

| Атрибут | Назначение |
|---------|------------|
| `required` | Поле обязательно |
| `minlength` / `maxlength` | Длина текста |
| `min` / `max` | Границы чисел |
| `pattern` | Регулярное выражение |
| `type="email"`, `type="url"` | Проверка формата |

```html
<input type="text" name="login" required minlength="3" maxlength="20"
       pattern="[A-Za-z0-9]+" title="Только латинские буквы и цифры">
```

---

## Глобальные атрибуты

| Атрибут | Назначение |
|---------|------------|
| `id` | Уникальный идентификатор |
| `class` | Класс для CSS/JS |
| `style` | Встроенные стили |
| `title` | Всплывающая подсказка |
| `hidden` | Скрыть элемент |
| `lang` | Язык содержимого |

```html
<p id="intro" class="text" style="color: red;" title="Подсказка">Текст</p>
```

---

## Семантические теги (кратко)

| Тег | Назначение |
|-----|------------|
| `<header>` | Шапка страницы или раздела |
| `<nav>` | Навигация |
| `<main>` | Основное содержимое |
| `<section>` | Раздел |
| `<article>` | Статья |
| `<aside>` | Боковая панель |
| `<footer>` | Подвал |

---

## Типичные ошибки

1. Забыли `name` у поля — данные не отправятся.
2. Одинаковые `id` — ломает связь `<label for>`.
3. Разные `name` у радиокнопок — они не связаны.
4. Не закрыли `<textarea>` — он парный.
5. `required` без типа — работает, но лучше указывать тип.

---

## Главное запомнить

| Что нужно | Как сделать |
|-----------|-------------|
| Создать страницу | `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` |
| Заголовок | `<h1>…</h1>` |
| Абзац | `<p>…</p>` |
| Список | `<ul>` или `<ol>` + `<li>` |
| Ссылка | `<a href="...">…</a>` |
| Картинка | `<img src="..." alt="...">` |
| Таблица | `<table>`, `<tr>`, `<th>`, `<td>` |
| Форма | `<form action="..." method="...">` |
| Поле ввода | `<input type="...">` |
| Многострочный текст | `<textarea>...</textarea>` |
| Выпадающий список | `<select><option>...</option></select>` |
| Кнопка | `<button type="submit">...</button>` |
| Обязательное поле | `required` |
| Проверка формата | `pattern`, `type="email"` |

P. S. HTML — это скелет страницы. Чем аккуратнее теги, тем проще стилизовать и поддерживать сайт.
