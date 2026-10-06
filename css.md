# Шпаргалка: CSS

## Что такое CSS

**CSS** (Cascading Style Sheets — каскадные таблицы стилей) — язык описания внешнего вида HTML-документа.  
CSS не программирует, а указывает браузеру, **как** отображать элементы: цвет, шрифт, отступы, рамки, расположение.

**Главная идея:** HTML отвечает за структуру, CSS — за оформление.

---

## Способы подключения CSS

| Способ | Как выглядит | Когда использовать |
|--------|--------------|-------------------|
| **Встроенный** (inline) | `<p style="color: red;">Текст</p>` | Быстро, но плохо для больших проектов |
| **Внутренний** (internal) | `<style> p { color: blue; } </style>` в `<head>` | Для одной страницы |
| **Внешний** (external) | `<link rel="stylesheet" href="style.css">` | Лучший вариант: один файл для всех страниц |

```html
<!-- Внешний CSS -->
<link rel="stylesheet" href="style.css">
```

---

## Синтаксис CSS

```css
селектор {
    свойство: значение;
    свойство: значение;
}
```

Пример:

```css
h1 {
    color: darkblue;
    text-align: center;
}
```

---

## Основные селекторы

| Селектор | Пример | Что выбирает |
|----------|--------|--------------|
| Тег | `p { ... }` | Все `<p>` |
| Класс | `.warning { ... }` | Все элементы с `class="warning"` |
| Идентификатор | `#header { ... }` | Элемент с `id="header"` |
| Группа | `h1, h2 { ... }` | Все `<h1>` и `<h2>` |
| Потомок | `div p { ... }` | Все `<p>` внутри `<div>` |
| Дочерний | `div > p { ... }` | Только прямые дети `<p>` внутри `<div>` |
| Псевдокласс | `a:hover { ... }` | Ссылка при наведении |
| Псевдоэлемент | `p::first-line { ... }` | Первая строка абзаца |
| Атрибут | `input[type="text"] { ... }` | Поля с типом `text` |

**Пример HTML:**

```html
<p class="warning">Осторожно!</p>
<p id="intro">Введение</p>
<a href="#">Ссылка</a>
```

**Пример CSS:**

```css
.warning {
    color: red;
    font-weight: bold;
}

#intro {
    font-size: 20px;
    font-style: italic;
}

a:hover {
    color: orange;
    text-decoration: none;
}
```

---

## Каскад и специфичность (кратко)

Когда несколько правил конфликтуют, побеждает более **специфичное**:

1. `!important` — наивысший приоритет (использовать осторожно).
2. Inline-стили (`style="..."`).
3. `id` (`#header`).
4. Классы, атрибуты, псевдоклассы (`.warning`, `:hover`).
5. Теги (`p`, `h1`).

Позже объявленное правило побеждает при равной специфичности.

---

## Цвет и текст

### Цвет

| Формат | Пример | Описание |
|--------|--------|----------|
| Имя | `red`, `blue` | Простые цвета |
| HEX | `#ff0000` | 16-ричный |
| RGB | `rgb(255, 0, 0)` | Красный, зелёный, синий |
| RGBA | `rgba(255, 0, 0, 0.5)` | С прозрачностью |
| HSL | `hsl(0, 100%, 50%)` | Тон, насыщенность, светлота |

### Свойства текста

| Свойство | Значения | Пример |
|----------|----------|--------|
| `color` | цвет | `color: #333;` |
| `font-family` | шрифт | `font-family: Arial, sans-serif;` |
| `font-size` | размер | `font-size: 18px;` |
| `font-weight` | жирность | `normal`, `bold`, `100–900` |
| `text-align` | выравнивание | `left`, `center`, `right`, `justify` |
| `line-height` | межстрочный интервал | `line-height: 1.5;` |
| `text-decoration` | подчёркивание | `none`, `underline`, `line-through` |
| `text-transform` | регистр | `uppercase`, `lowercase`, `capitalize` |
| `letter-spacing` | расстояние между буквами | `letter-spacing: 1px;` |

**Пример:**

```css
body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
    color: #333;
}

h1 {
    color: #2c3e50;
    text-align: center;
    font-size: 32px;
}

p {
    font-size: 16px;
    line-height: 1.5;
}
```

---

## Блочная модель (Box Model)

Каждый элемент — прямоугольник, состоящий из:

```
[ margin ]      внешний отступ
  [ border ]    рамка
    [ padding ] внутренний отступ
      [ content ] содержимое
    [ padding ]
  [ border ]
[ margin ]
```

| Свойство | Что делает |
|----------|------------|
| `width`, `height` | Ширина и высота содержимого |
| `padding` | Внутренний отступ (от содержимого до рамки) |
| `border` | Рамка |
| `margin` | Внешний отступ (от рамки до других элементов) |

**Важно:** по умолчанию `width` задаёт только ширину содержимого. Чтобы padding и border входили в ширину:

```css
* {
    box-sizing: border-box;
}
```

**Пример:**

```css
.box {
    width: 200px;
    padding: 20px;
    border: 2px solid black;
    margin: 10px;
    background-color: #f0f0f0;
}
```

---

## Размеры и отступы

| Свойство | Пример | Описание |
|----------|--------|----------|
| `width` | `width: 300px;` | Ширина |
| `height` | `height: 200px;` | Высота |
| `max-width` | `max-width: 800px;` | Максимальная ширина |
| `min-width` | `min-width: 200px;` | Минимальная ширина |
| `margin` | `margin: 10px 20px;` | Внешний отступ (вертикаль / горизонталь) |
| `padding` | `padding: 15px;` | Внутренний отступ |
| `margin: 0 auto;` | — | Центрирование блока по горизонтали |

**Единицы измерения:**

| Единица | Описание |
|---------|----------|
| `px` | Пиксели |
| `%` | Процент от родителя |
| `em` | Относительно размера шрифта родителя |
| `rem` | Относительно размера шрифта корневого элемента |
| `vw`, `vh` | Процент от ширины/высоты окна |

---

## Рамки и фон

### Рамки

```css
border: 2px solid #333;
border-radius: 10px;
```

| Свойство | Значения |
|----------|----------|
| `border-width` | `1px`, `thin`, `medium`, `thick` |
| `border-style` | `solid`, `dashed`, `dotted`, `none` |
| `border-color` | цвет |
| `border-radius` | радиус скругления |

### Фон

```css
background-color: #e3f2fd;
background-image: url('bg.jpg');
background-size: cover;
background-repeat: no-repeat;
background-position: center;
```

### Тень

```css
box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
```

---

## Display

| Значение | Поведение |
|----------|-----------|
| `block` | Занимает всю ширину, с новой строки (`div`, `p`, `h1`) |
| `inline` | В строке, не влияет на ширину/высоту (`span`, `a`) |
| `inline-block` | В строке, но можно задавать ширину/высоту |
| `none` | Скрыть элемент |
| `flex` | Включает Flexbox |
| `grid` | Включает Grid |

**Пример:**

```css
.card {
    display: inline-block;
    width: 200px;
    margin: 10px;
    padding: 15px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background: #fff;
}
```

---

## Flexbox

Включается у контейнера: `display: flex;`

### Свойства контейнера

| Свойство | Значения | Описание |
|----------|----------|----------|
| `flex-direction` | `row`, `column` | Направление главной оси |
| `justify-content` | `flex-start`, `center`, `space-between`, `space-around` | Выравнивание по главной оси |
| `align-items` | `stretch`, `center`, `flex-start`, `flex-end` | Выравнивание по поперечной оси |
| `gap` | `10px` | Расстояние между элементами |
| `flex-wrap` | `nowrap`, `wrap` | Перенос на новую строку |
| `align-content` | — | Выравнивание строк (при `wrap`) |

### Свойства элементов

| Свойство | Описание |
|----------|----------|
| `flex` | `flex: 1 1 200px;` — растяжение, сжатие, базовый размер |
| `order` | Порядок элемента |
| `align-self` | Выравнивание отдельного элемента |

**Пример:**

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
</div>
```

```css
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    background: #eee;
    padding: 10px;
}

.item {
    background: #2196f3;
    color: white;
    padding: 20px;
    border-radius: 5px;
}
```

**Центрирование через Flexbox:**

```css
.parent {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}
```

---

## Позиционирование

| Значение `position` | Описание |
|---------------------|----------|
| `static` | По умолчанию |
| `relative` | Сдвиг относительно себя |
| `absolute` | Относительно ближайшего позиционированного родителя |
| `fixed` | Относительно окна браузера |
| `sticky` | Гибрид: relative + fixed |

Дополнительно: `top`, `right`, `bottom`, `left`, `z-index`.

**Пример:**

```css
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: white;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    z-index: 100;
}
```

---

## Адаптивность и медиазапросы

```css
@media (max-width: 600px) {
    .menu {
        flex-direction: column;
    }
}
```

| Единица | Описание |
|---------|----------|
| `%` | От родителя |
| `rem` | От корневого шрифта |
| `em` | От текущего шрифта |
| `vw` | 1% ширины окна |
| `vh` | 1% высоты окна |

**Пример адаптивного меню:**

```css
.nav {
    display: flex;
    justify-content: center;
    gap: 15px;
    background: #333;
    padding: 15px;
}

@media (max-width: 600px) {
    .nav {
        flex-direction: column;
        align-items: center;
    }
}
```

---

## Псевдоклассы и псевдоэлементы

| Псевдокласс | Когда срабатывает |
|-------------|-------------------|
| `:hover` | При наведении |
| `:active` | При нажатии |
| `:focus` | При фокусе |
| `:visited` | Посещённая ссылка |
| `:first-child` | Первый ребёнок |
| `:last-child` | Последний ребёнок |
| `:nth-child(n)` | n-й ребёнок |

| Псевдоэлемент | Что делает |
|---------------|------------|
| `::before` | Вставляет содержимое перед элементом |
| `::after` | Вставляет содержимое после элемента |
| `::first-line` | Первая строка |
| `::first-letter` | Первая буква |

**Пример:**

```css
a {
    text-decoration: none;
    color: #1565c0;
}

a:hover {
    color: orange;
}

a:visited {
    color: gray;
}
```

---

## Полезные свойства (сводная таблица)

| Категория | Свойства |
|-----------|----------|
| Текст | `color`, `font-family`, `font-size`, `font-weight`, `text-align`, `line-height`, `text-decoration` |
| Блок | `width`, `height`, `max-width`, `margin`, `padding`, `border`, `border-radius` |
| Фон | `background-color`, `background-image`, `background-size`, `background-repeat` |
| Отображение | `display`, `visibility`, `overflow` |
| Flexbox | `display: flex`, `justify-content`, `align-items`, `gap`, `flex-wrap`, `flex` |
| Позиция | `position`, `top`, `left`, `z-index` |
| Адаптивность | `@media`, `vw`, `vh`, `rem`, `%` |

---

## Типичные ошибки

1. Забыли точку с запятой `;` после свойства.
2. Не подключили внешний CSS (`<link>`).
3. Одинаковые `id` на странице — ломает стили.
4. Специфичность: `id` перебивает классы, классы — теги.
5. `width` без `box-sizing: border-box` даёт неожиданные размеры.
6. `margin` схлопывается у соседних блоков (margin collapse).
7. Забыли единицы измерения: `width: 100` не работает, нужно `100px` или `100%`.

---

## Главное запомнить

| Что нужно | Как сделать |
|-----------|-------------|
| Подключить CSS | `<link rel="stylesheet" href="style.css">` |
| Выбрать все абзацы | `p { ... }` |
| Выбрать класс | `.warning { ... }` |
| Выбрать id | `#header { ... }` |
| Изменить цвет текста | `color: red;` |
| Задать фон | `background-color: #eee;` |
| Сделать отступы | `margin`, `padding` |
| Поставить рамку | `border: 1px solid #333;` |
| Скруглить углы | `border-radius: 10px;` |
| Расположить в ряд | `display: flex;` |
| Центрировать | `justify-content: center; align-items: center;` |
| Сделать адаптивно | `@media (max-width: 600px) { ... }` |
| Изменить стиль при наведении | `a:hover { ... }` |

P. S. CSS — это то, что превращает скелет HTML в аккуратный и удобный интерфейс. Чем лучше вы понимаете селекторы, блочную модель и Flexbox, тем проще создавать современные страницы.
