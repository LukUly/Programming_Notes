# 📘 Шпаргалка: HTML — полный справочник тегов и атрибутов

> **Как пользоваться:** ищи поиском (Ctrl+F) по названию тега или по описанию на русском.
> Например: «заголовок», «ссылка», «картинка», «таблица», «форма».
> **Название каждого тега — это ссылка** на страницу справочника htmlbook.ru. Кликните по нему, чтобы открыть подробное описание с примерами и таблицами поддержки браузеров.

---

## 📖 Что такое HTML

**HTML** (HyperText Markup Language — язык гипертекстовой разметки) — язык, с помощью которого описывается структура веб-страницы.

HTML не программирует, а указывает браузеру, **что** находится на странице: заголовок, абзац, ссылка, картинка, таблица.

**Главная идея:** HTML отвечает за структуру, CSS — за оформление.

### Теги и атрибуты

**Тег** — это элемент языка разметки, обозначающий какую-то сущность: заголовок, список, абзац, изображение .

Теги бывают **парные** (контейнеры) и **одиночные** (пустые) .

```html
<!-- Парный тег -->
<p>Это абзац текста.</p>

<!-- Одиночный тег -->
<br>
<img src="cat.jpg" alt="Кот">
```

**Атрибуты** — это дополнительные настройки тегов, которые изменяют их свойства и поведение. Атрибуты записываются внутри открывающего тега .

```html
<a href="https://google.com" title="Поисковик">Ссылка</a>
```

---

## 🏗️ Структура HTML-документа

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [html](https://htmlbook.ru/html/html) | Корневой элемент документа | `<html>...</html>` | `<html lang="ru">...</html>` |
| [head](https://htmlbook.ru/html/head) | Метаданные документа (заголовок, кодировка, стили) | `<head>...</head>` | `<head><title>Моя страница</title></head>` |
| [title](https://htmlbook.ru/html/title) | Заголовок вкладки браузера | `<title>...</title>` | `<title>Главная</title>` |
| [body](https://htmlbook.ru/html/body) | Основное содержимое страницы | `<body>...</body>` | `<body><p>Текст</p></body>` |
| [meta](https://htmlbook.ru/html/meta) | Метаданные (кодировка, описание, viewport) | `<meta name="..." content="...">` | `<meta charset="utf-8">` |
| [link](https://htmlbook.ru/html/link) | Подключение внешних ресурсов (CSS, иконки) | `<link rel="stylesheet" href="...">` | `<link rel="stylesheet" href="style.css">` |
| [style](https://htmlbook.ru/html/style) | Внутренние стили CSS | `<style>...</style>` | `<style>body { color: red; }</style>` |
| [script](https://htmlbook.ru/html/script) | Подключение или вставка JavaScript | `<script>...</script>` | `<script src="app.js"></script>` |

**Пример полной структуры:**

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Моя страница</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Привет, мир!</h1>
    <p>Это моя первая страница.</p>
</body>
</html>
```

---

## 📝 Текстовые теги

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [h1](https://htmlbook.ru/html/h1) – [h6](https://htmlbook.ru/html/h6) | Заголовки от самого важного (h1) до самого малого (h6) | `<h1>...</h1>` | `<h1>Главный заголовок</h1>` |
| [p](https://htmlbook.ru/html/p) | Абзац текста | `<p>...</p>` | `<p>Это абзац.</p>` |
| [br](https://htmlbook.ru/html/br) | Перенос строки | `<br>` | `Строка 1<br>Строка 2` |
| [hr](https://htmlbook.ru/html/hr) | Горизонтальная линия (разделитель) | `<hr>` | `<hr>` |
| [strong](https://htmlbook.ru/html/strong) | Важный текст (обычно полужирный) | `<strong>...</strong>` | `<strong>Внимание!</strong>` |
| [b](https://htmlbook.ru/html/b) | Полужирный текст | `<b>...</b>` | `<b>Жирный</b>` |
| [em](https://htmlbook.ru/html/em) | Акцент (обычно курсив) | `<em>...</em>` | `<em>Важно</em>` |
| [i](https://htmlbook.ru/html/i) | Курсив | `<i>...</i>` | `<i>Курсив</i>` |
| [u](https://htmlbook.ru/html/u) | Подчёркнутый текст | `<u>...</u>` | `<u>Подчёркнутый</u>` |
| [s](https://htmlbook.ru/html/s) | Перечёркнутый текст | `<s>...</s>` | `<s>Старая цена</s>` |
| [del](https://htmlbook.ru/html/del) | Удалённый текст | `<del>...</del>` | `<del>1000₽</del>` |
| [ins](https://htmlbook.ru/html/ins) | Добавленный текст | `<ins>...</ins>` | `<ins>800₽</ins>` |
| [mark](https://htmlbook.ru/html/mark) | Выделенный текст | `<mark>...</mark>` | `<mark>Важное</mark>` |
| [small](https://htmlbook.ru/html/small) | Мелкий текст | `<small>...</small>` | `<small>Примечание</small>` |
| [sub](https://htmlbook.ru/html/sub) | Нижний индекс | `<sub>...</sub>` | `H<sub>2</sub>O` |
| [sup](https://htmlbook.ru/html/sup) | Верхний индекс | `<sup>...</sup>` | `E = mc<sup>2</sup>` |
| [abbr](https://htmlbook.ru/html/abbr) | Аббревиатура | `<abbr title="...">...</abbr>` | `<abbr title="HyperText Markup Language">HTML</abbr>` |
| [blockquote](https://htmlbook.ru/html/blockquote) | Длинная цитата (с отступом) | `<blockquote>...</blockquote>` | `<blockquote>Цитата</blockquote>` |
| [q](https://htmlbook.ru/html/q) | Короткая цитата (в кавычках) | `<q>...</q>` | `<q>Цитата</q>` |
| [cite](https://htmlbook.ru/html/cite) | Название произведения | `<cite>...</cite>` | `<cite>Война и мир</cite>` |
| [code](https://htmlbook.ru/html/code) | Фрагмент кода | `<code>...</code>` | `<code>console.log()</code>` |
| [pre](https://htmlbook.ru/html/pre) | Предформатированный текст (сохраняет пробелы) | `<pre>...</pre>` | `<pre>  отступ  </pre>` |
| [kbd](https://htmlbook.ru/html/kbd) | Ввод с клавиатуры | `<kbd>...</kbd>` | `<kbd>Ctrl+C</kbd>` |
| [samp](https://htmlbook.ru/html/samp) | Результат программы | `<samp>...</samp>` | `<samp>Ошибка</samp>` |
| [var](https://htmlbook.ru/html/var) | Переменная | `<var>...</var>` | `<var>x</var> = 5` |
| [time](https://htmlbook.ru/html/time) | Дата/время | `<time datetime="...">...</time>` | `<time datetime="2024-01-01">1 января</time>` |
| [wbr](https://htmlbook.ru/html/wbr) | Возможный перенос слова | `<wbr>` | `Оченьдлинное<wbr>слово` |

---

## 🔗 Ссылки и навигация

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [a](https://htmlbook.ru/html/a) | Гиперссылка | `<a href="...">...</a>` | `<a href="https://google.com">Google</a>` |
| [nav](https://htmlbook.ru/html/nav) | Навигационный блок | `<nav>...</nav>` | `<nav><a href="/">Главная</a></nav>` |

**Основные атрибуты ссылки:**

| Атрибут | Описание | Пример |
|---------|----------|--------|
| `href` | Адрес, куда ведёт ссылка | `<a href="https://google.com">` |
| `target` | Где открыть: `_self` (та же вкладка), `_blank` (новая вкладка) | `<a href="..." target="_blank">` |
| `title` | Всплывающая подсказка | `<a href="..." title="Подсказка">` |
| `download` | Скачать файл вместо перехода | `<a href="file.pdf" download>` |

---

## 🖼️ Изображения и мультимедиа

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [img](https://htmlbook.ru/html/img) | Изображение | `<img src="..." alt="...">` | `<img src="cat.jpg" alt="Кот">` |
| [figure](https://htmlbook.ru/html/figure) | Иллюстрация с подписью | `<figure>...</figure>` | `<figure><img src="..."><figcaption>Подпись</figcaption></figure>` |
| [figcaption](https://htmlbook.ru/html/figcaption) | Подпись к иллюстрации | `<figcaption>...</figcaption>` | `<figcaption>Рис. 1</figcaption>` |
| [picture](https://htmlbook.ru/html/picture) | Адаптивное изображение | `<picture>...</picture>` | `<picture><source srcset="..."><img src="..."></picture>` |
| [source](https://htmlbook.ru/html/source) | Источник для picture/audio/video | `<source src="..." type="...">` | `<source src="video.mp4" type="video/mp4">` |
| [audio](https://htmlbook.ru/html/audio) | Аудиоплеер | `<audio controls>...</audio>` | `<audio controls src="sound.mp3"></audio>` |
| [video](https://htmlbook.ru/html/video) | Видеоплеер | `<video controls>...</video>` | `<video controls src="movie.mp4"></video>` |
| [track](https://htmlbook.ru/html/track) | Субтитры для видео | `<track src="..." kind="subtitles">` | `<track src="subs.vtt" kind="subtitles">` |
| [canvas](https://htmlbook.ru/html/canvas) | Холст для рисования (JavaScript) | `<canvas>...</canvas>` | `<canvas id="myCanvas"></canvas>` |
| [svg](https://htmlbook.ru/html/svg) | Векторная графика | `<svg>...</svg>` | `<svg><circle r="10"/></svg>` |

**Основные атрибуты img:**

| Атрибут | Описание | Пример |
|---------|----------|--------|
| `src` | Путь к изображению | `src="cat.jpg"` |
| `alt` | Альтернативный текст (если картинка не загрузилась) | `alt="Рыжий кот"` |
| `width` | Ширина | `width="200"` |
| `height` | Высота | `height="150"` |
| `loading` | Отложенная загрузка (`lazy`) | `loading="lazy"` |

---

## 📋 Списки

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [ul](https://htmlbook.ru/html/ul) | Маркированный список | `<ul>...</ul>` | `<ul><li>Пункт</li></ul>` |
| [ol](https://htmlbook.ru/html/ol) | Нумерованный список | `<ol>...</ol>` | `<ol><li>Первый</li></ol>` |
| [li](https://htmlbook.ru/html/li) | Элемент списка | `<li>...</li>` | `<li>Пункт</li>` |
| [dl](https://htmlbook.ru/html/dl) | Список определений | `<dl>...</dl>` | `<dl><dt>Термин</dt><dd>Описание</dd></dl>` |
| [dt](https://htmlbook.ru/html/dt) | Термин в списке определений | `<dt>...</dt>` | `<dt>HTML</dt>` |
| [dd](https://htmlbook.ru/html/dd) | Описание термина | `<dd>...</dd>` | `<dd>Язык разметки</dd>` |

**Атрибуты списков:**

| Атрибут | Тег | Описание | Пример |
|---------|-----|----------|--------|
| `type` | `<ol>` | Тип нумерации: `1`, `A`, `a`, `I`, `i` | `<ol type="A">` |
| `start` | `<ol>` | Начальное число | `<ol start="5">` |
| `reversed` | `<ol>` | Обратный порядок | `<ol reversed>` |

---

## 📊 Таблицы

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [table](https://htmlbook.ru/html/table) | Таблица | `<table>...</table>` | `<table><tr><td>Ячейка</td></tr></table>` |
| [caption](https://htmlbook.ru/html/caption) | Заголовок таблицы | `<caption>...</caption>` | `<caption>Отчёт</caption>` |
| [thead](https://htmlbook.ru/html/thead) | Заголовочная часть | `<thead>...</thead>` | `<thead><tr><th>Имя</th></tr></thead>` |
| [tbody](https://htmlbook.ru/html/tbody) | Основная часть | `<tbody>...</tbody>` | `<tbody><tr><td>Данные</td></tr></tbody>` |
| [tfoot](https://htmlbook.ru/html/tfoot) | Нижняя часть (итоги) | `<tfoot>...</tfoot>` | `<tfoot><tr><td>Итого</td></tr></tfoot>` |
| [tr](https://htmlbook.ru/html/tr) | Строка таблицы | `<tr>...</tr>` | `<tr><td>Ячейка</td></tr>` |
| [th](https://htmlbook.ru/html/th) | Заголовочная ячейка | `<th>...</th>` | `<th>Имя</th>` |
| [td](https://htmlbook.ru/html/td) | Ячейка данных | `<td>...</td>` | `<td>Иван</td>` |
| [colgroup](https://htmlbook.ru/html/colgroup) | Группа столбцов | `<colgroup>...</colgroup>` | `<colgroup><col span="2"></colgroup>` |
| [col](https://htmlbook.ru/html/col) | Столбец | `<col>` | `<col style="background: #eee">` |

**Атрибуты ячеек:**

| Атрибут | Описание | Пример |
|---------|----------|--------|
| `colspan` | Объединение столбцов | `<td colspan="2">` |
| `rowspan` | Объединение строк | `<td rowspan="3">` |
| `scope` | Область заголовка (для th): `col`, `row` | `<th scope="col">` |

---

## 📦 Блочные и строчные контейнеры

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [div](https://htmlbook.ru/html/div) | Блочный контейнер (универсальный) | `<div>...</div>` | `<div class="card">...</div>` |
| [span](https://htmlbook.ru/html/span) | Строчный контейнер (универсальный) | `<span>...</span>` | `<span class="red">текст</span>` |
| [header](https://htmlbook.ru/html/header) | Шапка страницы или раздела | `<header>...</header>` | `<header><h1>Сайт</h1></header>` |
| [footer](https://htmlbook.ru/html/footer) | Подвал страницы или раздела | `<footer>...</footer>` | `<footer>© 2024</footer>` |
| [main](https://htmlbook.ru/html/main) | Основное содержимое | `<main>...</main>` | `<main><p>Контент</p></main>` |
| [section](https://htmlbook.ru/html/section) | Секция (тематический раздел) | `<section>...</section>` | `<section><h2>О нас</h2></section>` |
| [article](https://htmlbook.ru/html/article) | Независимая статья | `<article>...</article>` | `<article><h2>Новость</h2></article>` |
| [aside](https://htmlbook.ru/html/aside) | Боковая панель (доп. информация) | `<aside>...</aside>` | `<aside>Реклама</aside>` |
| [address](https://htmlbook.ru/html/address) | Контактная информация | `<address>...</address>` | `<address>Москва, ул. Ленина</address>` |
| [details](https://htmlbook.ru/html/details) | Раскрывающийся блок | `<details>...</details>` | `<details><summary>Подробнее</summary>Текст</details>` |
| [summary](https://htmlbook.ru/html/summary) | Заголовок для details | `<summary>...</summary>` | `<summary>Показать</summary>` |
| [dialog](https://htmlbook.ru/html/dialog) | Диалоговое окно | `<dialog>...</dialog>` | `<dialog open>Привет</dialog>` |

---

## 📝 Формы

| Тег | Описание | Синтаксис | Пример |
|-----|----------|-----------|--------|
| [form](https://htmlbook.ru/html/form) | Контейнер формы | `<form>...</form>` | `<form action="/submit" method="post">...</form>` |
| [input](https://htmlbook.ru/html/input) | Поле ввода | `<input type="...">` | `<input type="text" name="user">` |
| [textarea](https://htmlbook.ru/html/textarea) | Многострочное поле | `<textarea>...</textarea>` | `<textarea rows="5"></textarea>` |
| [button](https://htmlbook.ru/html/button) | Кнопка | `<button>...</button>` | `<button type="submit">Отправить</button>` |
| [select](https://htmlbook.ru/html/select) | Выпадающий список | `<select>...</select>` | `<select><option>1</option></select>` |
| [option](https://htmlbook.ru/html/option) | Пункт списка | `<option>...</option>` | `<option value="1">Первый</option>` |
| [optgroup](https://htmlbook.ru/html/optgroup) | Группа пунктов | `<optgroup>...</optgroup>` | `<optgroup label="Группа"><option>...</option></optgroup>` |
| [label](https://htmlbook.ru/html/label) | Подпись к полю | `<label>...</label>` | `<label for="name">Имя</label>` |
| [fieldset](https://htmlbook.ru/html/fieldset) | Группа полей | `<fieldset>...</fieldset>` | `<fieldset><legend>Данные</legend>...</fieldset>` |
| [legend](https://htmlbook.ru/html/legend) | Заголовок группы полей | `<legend>...</legend>` | `<legend>Личные данные</legend>` |
| [datalist](https://htmlbook.ru/html/datalist) | Список подсказок для input | `<datalist>...</datalist>` | `<datalist id="browsers"><option value="Chrome"></datalist>` |
| [output](https://htmlbook.ru/html/output) | Результат вычислений | `<output>...</output>` | `<output>42</output>` |
| [progress](https://htmlbook.ru/html/progress) | Индикатор прогресса | `<progress value="70" max="100">` | `<progress value="50" max="100"></progress>` |
| [meter](https://htmlbook.ru/html/meter) | Измеритель (шкала) | `<meter value="0.7">...</meter>` | `<meter value="7" max="10">7/10</meter>` |

### Типы input

| Тип | Описание | Пример |
|-----|----------|--------|
| `text` | Текстовое поле | `<input type="text">` |
| `password` | Поле пароля | `<input type="password">` |
| `email` | Email | `<input type="email">` |
| `number` | Число | `<input type="number" min="1" max="100">` |
| `tel` | Телефон | `<input type="tel">` |
| `url` | URL | `<input type="url">` |
| `date` | Дата | `<input type="date">` |
| `time` | Время | `<input type="time">` |
| `datetime-local` | Дата и время | `<input type="datetime-local">` |
| `month` | Месяц | `<input type="month">` |
| `week` | Неделя | `<input type="week">` |
| `color` | Выбор цвета | `<input type="color">` |
| `range` | Ползунок | `<input type="range" min="0" max="100">` |
| `file` | Загрузка файла | `<input type="file" accept="image/*">` |
| `checkbox` | Флажок | `<input type="checkbox" checked>` |
| `radio` | Радиокнопка | `<input type="radio" name="gender">` |
| `hidden` | Скрытое поле | `<input type="hidden" name="id" value="5">` |
| `submit` | Кнопка отправки | `<input type="submit" value="Отправить">` |
| `reset` | Кнопка сброса | `<input type="reset" value="Очистить">` |
| `button` | Кнопка | `<input type="button" value="Нажми">` |
| `image` | Кнопка-картинка | `<input type="image" src="btn.png">` |

---

## 🌐 Глобальные атрибуты

Глобальные атрибуты можно использовать с **любым** тегом .

| Атрибут | Описание | Пример |
|---------|----------|--------|
| `id` | Уникальный идентификатор элемента | `<div id="header">` |
| `class` | Класс для CSS и JavaScript | `<p class="warning">` |
| `style` | Встроенные CSS-стили | `<p style="color: red;">` |
| `title` | Всплывающая подсказка | `<a title="Подсказка">` |
| `lang` | Язык содержимого | `<html lang="ru">` |
| `dir` | Направление текста (`ltr`, `rtl`) | `<p dir="rtl">` |
| `hidden` | Скрыть элемент | `<div hidden>` |
| `tabindex` | Порядок перехода по Tab | `<input tabindex="1">` |
| `accesskey` | Горячая клавиша | `<a accesskey="h">` |
| `contenteditable` | Редактируемый контент | `<div contenteditable="true">` |
| `draggable` | Перетаскиваемый элемент | `<div draggable="true">` |
| `spellcheck` | Проверка орфографии | `<textarea spellcheck="true">` |
| `data-*` | Пользовательские данные | `<div data-user-id="5">` |

---

## 🎨 Специальные символы (HTML-сущности)

| Символ | Код | Описание |
|--------|-----|----------|
| `<` | `&lt;` | Меньше |
| `>` | `&gt;` | Больше |
| `&` | `&amp;` | Амперсанд |
| `"` | `&quot;` | Двойная кавычка |
| `'` | `&#39;` | Одинарная кавычка |
| ` ` | `&nbsp;` | Неразрывный пробел |
| `©` | `&copy;` | Копирайт |
| `®` | `&reg;` | Зарегистрированный знак |
| `€` | `&euro;` | Евро |
| `₽` | `&#8381;` | Рубль |

---

## ⚠️ Устаревшие теги (не использовать)

| Тег | Описание | Альтернатива |
|-----|----------|--------------|
| `<center>` | Центрирование | `text-align: center` в CSS |
| `<font>` | Шрифт и цвет | CSS: `font-family`, `color` |
| `<big>` | Крупный текст | CSS: `font-size` |
| `<strike>` | Перечёркнутый | `<s>` или `<del>` |
| `<u>` | Подчёркнутый | CSS: `text-decoration` |
| `<frame>`, `<frameset>` | Фреймы | `<iframe>` |
| `<marquee>` | Бегущая строка | CSS-анимации |
| `<nobr>` | Запрет переноса | `white-space: nowrap` |
| `<applet>` | Java-апплеты | `<object>` или `<embed>` |

---

## 💡 Полезные советы

1. **Всегда указывайте `alt`** для изображений — это важно для доступности.
2. **Используйте семантические теги** (`<header>`, `<nav>`, `<main>`, `<article>`) вместо `<div>` где возможно.
3. **Закрывайте теги правильно** — вложенные элементы закрываются в обратном порядке .
4. **Пишите теги строчными буквами** — это стандарт HTML5 .
5. **Указывайте `lang`** в `<html>` для правильной работы скринридеров.
6. **Не используйте таблицы для вёрстки** — только для табличных данных.
7. **Подключайте CSS через `<link>`** в `<head>`, а не через `style`-атрибуты.

---

## 🔗 Полезные ссылки

- [Справочник HTML на htmlbook.ru](https://htmlbook.ru/html)
- [MDN Web Docs — HTML](https://developer.mozilla.org/ru/docs/Web/HTML)
- [W3C HTML Specification](https://html.spec.whatwg.org/)

---

*Шпаргалка создана на основе справочника HTML от htmlbook.ru и MDN Web Docs. Все названия тегов — это ссылки на соответствующие страницы справочника.*
