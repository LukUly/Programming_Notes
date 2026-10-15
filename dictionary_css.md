# 📗 Шпаргалка: CSS — полный справочник свойств со ссылками на htmlbook.ru

> **Как пользоваться:** ищи поиском (Ctrl+F) по названию свойства или по описанию на русском.
> Например: «отступ внутри», «рамка», «тень», «жирность текста».
> **Каждое свойство имеет ссылку** на страницу справочника htmlbook.ru — кликните, чтобы открыть подробное описание с примерами и таблицами поддержки браузеров .

---

## 📖 Что такое CSS

**CSS** (Cascading Style Sheets — каскадные таблицы стилей) — язык описания внешнего вида HTML-документа.
CSS указывает браузеру, **как** отображать элементы: цвет, шрифт, отступы, рамки, расположение .

**Главная идея:** HTML отвечает за структуру, CSS — за оформление.

---

## 🔌 Способы подключения CSS

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

## ✏️ Синтаксис CSS

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

## 🎯 Основные селекторы

| Селектор | Пример | Что выбирает |
|----------|--------|--------------|
| Универсальный | `* { ... }` | Все элементы |
| Тег | `p { ... }` | Все `<p>` |
| Класс | `.warning { ... }` | Все элементы с `class="warning"` |
| Идентификатор | `#header { ... }` | Элемент с `id="header"` |
| Группа | `h1, h2 { ... }` | Все `<h1>` и `<h2>` |
| Потомок | `div p { ... }` | Все `<p>` внутри `<div>` |
| Дочерний | `div > p { ... }` | Только прямые дети `<p>` внутри `<div>` |
| Соседний | `h1 + p { ... }` | Первый `<p>` сразу после `<h1>` |
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

## 🏆 Каскад и специфичность (кратко)

Когда несколько правил конфликтуют, побеждает более **специфичное**:

1. `!important` — наивысший приоритет (использовать осторожно).
2. Inline-стили (`style="..."`).
3. `id` (`#header`).
4. Классы, атрибуты, псевдоклассы (`.warning`, `:hover`).
5. Теги (`p`, `h1`).

Позже объявленное правило побеждает при равной специфичности.

---

## 🎨 Цвет и текст

### Цвет

| Формат | Пример | Описание |
|--------|--------|----------|
| Имя | `red`, `blue` | Простые цвета |
| HEX | `#ff0000` | 16-ричный |
| RGB | `rgb(255, 0, 0)` | Красный, зелёный, синий  |
| RGBA | `rgba(255, 0, 0, 0.5)` | С прозрачностью |
| HSL | `hsl(0, 100%, 50%)` | Тон, насыщенность, светлота |
| OKLCH | `oklch(62% 0.23 30)` | Современная цветовая модель  |

### Свойства текста

| Свойство | Синтаксис | Значения | Пример | Ссылка |
|----------|-----------|----------|--------|--------|
| `color` | `color: <цвет>;` | цвет | `color: #333;` | [htmlbook.ru/css/color](https://htmlbook.ru/css/color) |
| `font-family` | `font-family: <шрифт>, <запасной>;` | имя шрифта, `serif`, `sans-serif`, `monospace` | `font-family: Arial, sans-serif;` | [htmlbook.ru/css/font-family](https://htmlbook.ru/css/font-family) |
| `font-size` | `font-size: <размер>;` | `px`, `em`, `rem`, `%`, `small`, `large` | `font-size: 18px;` | [htmlbook.ru/css/font-size](https://htmlbook.ru/css/font-size) |
| `font-weight` | `font-weight: <жирность>;` | `normal`, `bold`, `100–900` | `font-weight: bold;` | [htmlbook.ru/css/font-weight](https://htmlbook.ru/css/font-weight) |
| `font-style` | `font-style: <стиль>;` | `normal`, `italic`, `oblique` | `font-style: italic;` | [htmlbook.ru/css/font-style](https://htmlbook.ru/css/font-style) |
| `text-align` | `text-align: <выравнивание>;` | `left`, `center`, `right`, `justify` | `text-align: center;` | [htmlbook.ru/css/text-align](https://htmlbook.ru/css/text-align) |
| `line-height` | `line-height: <высота>;` | число, `px`, `em`, `%` | `line-height: 1.5;` | [htmlbook.ru/css/line-height](https://htmlbook.ru/css/line-height) |
| `text-decoration` | `text-decoration: <линия>;` | `none`, `underline`, `line-through`, `overline` | `text-decoration: none;` | [htmlbook.ru/css/text-decoration](https://htmlbook.ru/css/text-decoration) |
| `text-transform` | `text-transform: <регистр>;` | `uppercase`, `lowercase`, `capitalize` | `text-transform: uppercase;` | [htmlbook.ru/css/text-transform](https://htmlbook.ru/css/text-transform) |
| `letter-spacing` | `letter-spacing: <расстояние>;` | `px`, `em` | `letter-spacing: 1px;` | [htmlbook.ru/css/letter-spacing](https://htmlbook.ru/css/letter-spacing) |
| `text-indent` | `text-indent: <отступ>;` | `px`, `em`, `%` | `text-indent: 20px;` | [htmlbook.ru/css/text-indent](https://htmlbook.ru/css/text-indent) |
| `text-shadow` | `text-shadow: <сдвиг-x> <сдвиг-y> <размытие> <цвет>;` | значения через пробел | `text-shadow: 2px 2px 4px #000;` | [htmlbook.ru/css/text-shadow](https://htmlbook.ru/css/text-shadow) |
| `word-spacing` | `word-spacing: <расстояние>;` | `px`, `em` | `word-spacing: 5px;` | [htmlbook.ru/css/word-spacing](https://htmlbook.ru/css/word-spacing) |
| `white-space` | `white-space: <режим>;` | `normal`, `nowrap`, `pre`, `pre-wrap` | `white-space: nowrap;` | [htmlbook.ru/css/white-space](https://htmlbook.ru/css/white-space) |
| `text-overflow` | `text-overflow: <режим>;` | `ellipsis`, `clip` | `text-overflow: ellipsis;` | [htmlbook.ru/css/text-overflow](https://htmlbook.ru/css/text-overflow) |

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

## 📦 Блочная модель (Box Model) — отступы и размеры

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

### Размеры

| Свойство | Синтаксис | Значения | Пример | Ссылка |
|----------|-----------|----------|--------|--------|
| `width` | `width: <размер>;` | `px`, `%`, `auto`, `vw` | `width: 300px;` | [htmlbook.ru/css/width](https://htmlbook.ru/css/width) |
| `height` | `height: <размер>;` | `px`, `%`, `auto`, `vh` | `height: 200px;` | [htmlbook.ru/css/height](https://htmlbook.ru/css/height) |
| `max-width` | `max-width: <размер>;` | `px`, `%`, `none` | `max-width: 800px;` | [htmlbook.ru/css/max-width](https://htmlbook.ru/css/max-width) |
| `min-width` | `min-width: <размер>;` | `px`, `%` | `min-width: 200px;` | [htmlbook.ru/css/min-width](https://htmlbook.ru/css/min-width) |
| `max-height` | `max-height: <размер>;` | `px`, `%`, `none` | `max-height: 500px;` | [htmlbook.ru/css/max-height](https://htmlbook.ru/css/max-height) |
| `min-height` | `min-height: <размер>;` | `px`, `%` | `min-height: 100px;` | [htmlbook.ru/css/min-height](https://htmlbook.ru/css/min-height) |

### Отступы (внутренние и внешние)

| Свойство | Синтаксис | Пример | Ссылка |
|----------|-----------|--------|--------|
| `margin` | `margin: <верх> <право> <низ> <лево>;` | `margin: 10px 20px;` | [htmlbook.ru/css/margin](https://htmlbook.ru/css/margin) |
| `margin-top` | `margin-top: <размер>;` | `margin-top: 10px;` | [htmlbook.ru/css/margin-top](https://htmlbook.ru/css/margin-top) |
| `margin-right` | `margin-right: <размер>;` | `margin-right: 20px;` | [htmlbook.ru/css/margin-right](https://htmlbook.ru/css/margin-right) |
| `margin-bottom` | `margin-bottom: <размер>;` | `margin-bottom: 10px;` | [htmlbook.ru/css/margin-bottom](https://htmlbook.ru/css/margin-bottom) |
| `margin-left` | `margin-left: <размер>;` | `margin-left: 20px;` | [htmlbook.ru/css/margin-left](https://htmlbook.ru/css/margin-left) |
| `padding` | `padding: <верх> <право> <низ> <лево>;` | `padding: 15px;` | [htmlbook.ru/css/padding](https://htmlbook.ru/css/padding) |
| `padding-top` | `padding-top: <размер>;` | `padding-top: 10px;` | [htmlbook.ru/css/padding-top](https://htmlbook.ru/css/padding-top) |
| `padding-right` | `padding-right: <размер>;` | `padding-right: 20px;` | [htmlbook.ru/css/padding-right](https://htmlbook.ru/css/padding-right) |
| `padding-bottom` | `padding-bottom: <размер>;` | `padding-bottom: 10px;` | [htmlbook.ru/css/padding-bottom](https://htmlbook.ru/css/padding-bottom) |
| `padding-left` | `padding-left: <размер>;` | `padding-left: 20px;` | [htmlbook.ru/css/padding-left](https://htmlbook.ru/css/padding-left) |

**Единицы измерения:**

| Единица | Описание |
|---------|----------|
| `px` | Пиксели |
| `%` | Процент от родителя |
| `em` | Относительно размера шрифта родителя |
| `rem` | Относительно размера шрифта корневого элемента |
| `vw`, `vh` | Процент от ширины/высоты окна |

**Важно:** по умолчанию `width` задаёт только ширину содержимого. Чтобы padding и border входили в ширину:

```css
* {
    box-sizing: border-box;
}
```

---

## 🖼️ Рамки, фон и тень

### Рамки

| Свойство | Синтаксис | Пример | Ссылка |
|----------|-----------|--------|--------|
| `border` | `border: <ширина> <стиль> <цвет>;` | `border: 1px solid #ccc;` | [htmlbook.ru/css/border](https://htmlbook.ru/css/border) |
| `border-width` | `border-width: <толщина>;` | `border-width: 2px;` | [htmlbook.ru/css/border-width](https://htmlbook.ru/css/border-width) |
| `border-style` | `border-style: <стиль>;` | `border-style: dashed;` | [htmlbook.ru/css/border-style](https://htmlbook.ru/css/border-style) |
| `border-color` | `border-color: <цвет>;` | `border-color: red;` | [htmlbook.ru/css/border-color](https://htmlbook.ru/css/border-color) |
| `border-radius` | `border-radius: <радиус>;` | `border-radius: 8px;` | [htmlbook.ru/css/border-radius](https://htmlbook.ru/css/border-radius) |
| `border-top` | `border-top: <ширина> <стиль> <цвет>;` | `border-top: 2px solid blue;` | [htmlbook.ru/css/border-top](https://htmlbook.ru/css/border-top) |
| `border-right` | `border-right: <ширина> <стиль> <цвет>;` | `border-right: 2px solid blue;` | [htmlbook.ru/css/border-right](https://htmlbook.ru/css/border-right) |
| `border-bottom` | `border-bottom: <ширина> <стиль> <цвет>;` | `border-bottom: 2px solid blue;` | [htmlbook.ru/css/border-bottom](https://htmlbook.ru/css/border-bottom) |
| `border-left` | `border-left: <ширина> <стиль> <цвет>;` | `border-left: 2px solid blue;` | [htmlbook.ru/css/border-left](https://htmlbook.ru/css/border-left) |

### Фон

| Свойство | Синтаксис | Пример | Ссылка |
|----------|-----------|--------|--------|
| `background-color` | `background-color: <цвет>;` | `background-color: #f0f0f0;` | [htmlbook.ru/css/background-color](https://htmlbook.ru/css/background-color) |
| `background-image` | `background-image: url('<путь>');` | `background-image: url('bg.png');` | [htmlbook.ru/css/background-image](https://htmlbook.ru/css/background-image) |
| `background-size` | `background-size: <размер>;` | `background-size: cover;` | [htmlbook.ru/css/background-size](https://htmlbook.ru/css/background-size) |
| `background-repeat` | `background-repeat: <режим>;` | `background-repeat: no-repeat;` | [htmlbook.ru/css/background-repeat](https://htmlbook.ru/css/background-repeat) |
| `background-position` | `background-position: <x> <y>;` | `background-position: center;` | [htmlbook.ru/css/background-position](https://htmlbook.ru/css/background-position) |
| `background-position-y` | `background-position-y: top \| center \| bottom;` | `background-position-y: center;` | [htmlbook.ru/css/background-position-y](https://htmlbook.ru/css/background-position-y)  |
| `background-attachment` | `background-attachment: <режим>;` | `background-attachment: fixed;` | [htmlbook.ru/css/background-attachment](https://htmlbook.ru/css/background-attachment) |
| `background` | `background: <цвет> <изображение> <позиция> / <размер> <повтор>;` | `background: #fff url('bg.png') center / cover no-repeat;` | [htmlbook.ru/css/background](https://htmlbook.ru/css/background) |

### Тень

| Свойство | Синтаксис | Пример | Ссылка |
|----------|-----------|--------|--------|
| `box-shadow` | `box-shadow: <x> <y> <размытие> <распространение> <цвет>;` | `box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);` | [htmlbook.ru/css/box-shadow](https://htmlbook.ru/css/box-shadow) |
| `text-shadow` | `text-shadow: <x> <y> <размытие> <цвет>;` | `text-shadow: 1px 1px 2px #000;` | [htmlbook.ru/css/text-shadow](https://htmlbook.ru/css/text-shadow) |

---

## 📐 Display

| Значение | Поведение | Ссылка |
|----------|-----------|--------|
| `block` | Занимает всю ширину, с новой строки (`div`, `p`, `h1`) | [htmlbook.ru/css/display](https://htmlbook.ru/css/display)  |
| `inline` | В строке, не влияет на ширину/высоту (`span`, `a`) | |
| `inline-block` | В строке, но можно задавать ширину/высоту | |
| `none` | Скрыть элемент | |
| `flex` | Включает Flexbox | |
| `grid` | Включает Grid | |

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

## 🧩 Flexbox — выравнивание и раскладка

Включается у контейнера: `display: flex;`

### Свойства контейнера

| Свойство | Синтаксис | Значения | Ссылка |
|----------|-----------|----------|--------|
| `flex-direction` | `flex-direction: <направление>;` | `row`, `column`, `row-reverse`, `column-reverse` | [htmlbook.ru/css/flex-direction](https://htmlbook.ru/css/flex-direction) |
| `justify-content` | `justify-content: <выравнивание>;` | `flex-start`, `center`, `space-between`, `space-around` | [htmlbook.ru/css/justify-content](https://htmlbook.ru/css/justify-content) |
| `align-items` | `align-items: <выравнивание>;` | `stretch`, `center`, `flex-start`, `flex-end` | [htmlbook.ru/css/align-items](https://htmlbook.ru/css/align-items) |
| `gap` | `gap: <размер>;` | `10px`, `1rem` | [htmlbook.ru/css/gap](https://htmlbook.ru/css/gap) |
| `flex-wrap` | `flex-wrap: <режим>;` | `nowrap`, `wrap`, `wrap-reverse` | [htmlbook.ru/css/flex-wrap](https://htmlbook.ru/css/flex-wrap) |
| `align-content` | `align-content: <выравнивание>;` | `flex-start`, `center`, `space-between`, `stretch` | [htmlbook.ru/css/align-content](https://htmlbook.ru/css/align-content) |

### Свойства элементов

| Свойство | Синтаксис | Описание | Ссылка |
|----------|-----------|----------|--------|
| `flex` | `flex: <растяжение> <сжатие> <базовый-размер>;` | `flex: 1 1 200px;` | [htmlbook.ru/css/flex](https://htmlbook.ru/css/flex) |
| `order` | `order: <число>;` | Порядок элемента | [htmlbook.ru/css/order](https://htmlbook.ru/css/order) |
| `align-self` | `align-self: <выравнивание>;` | Выравнивание отдельного элемента | [htmlbook.ru/css/align-self](https://htmlbook.ru/css/align-self) |

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

## 📍 Позиционирование

| Значение `position` | Описание | Ссылка |
|---------------------|----------|--------|
| `static` | По умолчанию | [htmlbook.ru/css/position](https://htmlbook.ru/css/position) |
| `relative` | Сдвиг относительно себя | |
| `absolute` | Относительно ближайшего позиционированного родителя | |
| `fixed` | Относительно окна браузера | |
| `sticky` | Гибрид: relative + fixed | |

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

## 📱 Адаптивность и медиазапросы

```css
@media (max-width: 600px) {
    .menu {
        flex-direction: column;
    }
}
```

---

## 📋 Полный список CSS-свойств по алфавиту

### A

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `align-content` | Выравнивание строк во flex-контейнере | `align-content: <значение>;` | [htmlbook.ru/css/align-content](https://htmlbook.ru/css/align-content) |
| `align-items` | Выравнивание элементов по поперечной оси | `align-items: <значение>;` | [htmlbook.ru/css/align-items](https://htmlbook.ru/css/align-items) |
| `align-self` | Выравнивание отдельного элемента | `align-self: <значение>;` | [htmlbook.ru/css/align-self](https://htmlbook.ru/css/align-self) |
| `animation` | Сокращённая запись анимации | `animation: <имя> <длительность> <функция> <задержка> <повтор> <направление> <режим>;` | [htmlbook.ru/css/animation](https://htmlbook.ru/css/animation) |
| `animation-delay` | Задержка перед анимацией | `animation-delay: <время>;` | [htmlbook.ru/css/animation-delay](https://htmlbook.ru/css/animation-delay) |
| `animation-direction` | Направление анимации | `animation-direction: <значение>;` | [htmlbook.ru/css/animation-direction](https://htmlbook.ru/css/animation-direction) |
| `animation-duration` | Длительность анимации | `animation-duration: <время>;` | [htmlbook.ru/css/animation-duration](https://htmlbook.ru/css/animation-duration) |
| `animation-fill-mode` | Состояние до/после анимации | `animation-fill-mode: <значение>;` | [htmlbook.ru/css/animation-fill-mode](https://htmlbook.ru/css/animation-fill-mode) |
| `animation-iteration-count` | Количество повторов | `animation-iteration-count: <число>;` | [htmlbook.ru/css/animation-iteration-count](https://htmlbook.ru/css/animation-iteration-count) |
| `animation-name` | Имя keyframes | `animation-name: <имя>;` | [htmlbook.ru/css/animation-name](https://htmlbook.ru/css/animation-name) |
| `animation-play-state` | Пауза/запуск анимации | `animation-play-state: <значение>;` | [htmlbook.ru/css/animation-play-state](https://htmlbook.ru/css/animation-play-state) |
| `animation-timing-function` | Скорость анимации | `animation-timing-function: <значение>;` | [htmlbook.ru/css/animation-timing-function](https://htmlbook.ru/css/animation-timing-function) |

### B

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `backface-visibility` | Видимость обратной стороны 3D-элемента | `backface-visibility: <значение>;` | [htmlbook.ru/css/backface-visibility](https://htmlbook.ru/css/backface-visibility) |
| `background` | Сокращённая запись фона | `background: <цвет> <изображение> <позиция> / <размер> <повтор> <attachment>;` | [htmlbook.ru/css/background](https://htmlbook.ru/css/background) |
| `background-attachment` | Прокрутка фона | `background-attachment: <значение>;` | [htmlbook.ru/css/background-attachment](https://htmlbook.ru/css/background-attachment) |
| `background-blend-mode` | Режим смешивания фона | `background-blend-mode: <режим>;` | [htmlbook.ru/css/background-blend-mode](https://htmlbook.ru/css/background-blend-mode) |
| `background-clip` | Область обрезки фона | `background-clip: <значение>;` | [htmlbook.ru/css/background-clip](https://htmlbook.ru/css/background-clip) |
| `background-color` | Цвет фона | `background-color: <цвет>;` | [htmlbook.ru/css/background-color](https://htmlbook.ru/css/background-color) |
| `background-image` | Фоновое изображение | `background-image: url('<путь>');` | [htmlbook.ru/css/background-image](https://htmlbook.ru/css/background-image) |
| `background-origin` | Начало координат фона | `background-origin: <значение>;` | [htmlbook.ru/css/background-origin](https://htmlbook.ru/css/background-origin) |
| `background-position` | Позиция фона | `background-position: <x> <y>;` | [htmlbook.ru/css/background-position](https://htmlbook.ru/css/background-position) |
| `background-position-y` | Позиция фона по вертикали | `background-position-y: top \| center \| bottom;` | [htmlbook.ru/css/background-position-y](https://htmlbook.ru/css/background-position-y)  |
| `background-repeat` | Повтор фона | `background-repeat: <режим>;` | [htmlbook.ru/css/background-repeat](https://htmlbook.ru/css/background-repeat) |
| `background-size` | Размер фона | `background-size: <размер>;` | [htmlbook.ru/css/background-size](https://htmlbook.ru/css/background-size) |
| `border` | Сокращённая запись рамки | `border: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/border](https://htmlbook.ru/css/border) |
| `border-bottom` | Рамка снизу | `border-bottom: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/border-bottom](https://htmlbook.ru/css/border-bottom) |
| `border-bottom-color` | Цвет нижней рамки | `border-bottom-color: <цвет>;` | [htmlbook.ru/css/border-bottom-color](https://htmlbook.ru/css/border-bottom-color) |
| `border-bottom-left-radius` | Скругление левого нижнего угла | `border-bottom-left-radius: <радиус>;` | [htmlbook.ru/css/border-bottom-left-radius](https://htmlbook.ru/css/border-bottom-left-radius) |
| `border-bottom-right-radius` | Скругление правого нижнего угла | `border-bottom-right-radius: <радиус>;` | [htmlbook.ru/css/border-bottom-right-radius](https://htmlbook.ru/css/border-bottom-right-radius) |
| `border-bottom-style` | Стиль нижней рамки | `border-bottom-style: <стиль>;` | [htmlbook.ru/css/border-bottom-style](https://htmlbook.ru/css/border-bottom-style) |
| `border-bottom-width` | Толщина нижней рамки | `border-bottom-width: <толщина>;` | [htmlbook.ru/css/border-bottom-width](https://htmlbook.ru/css/border-bottom-width) |
| `border-collapse` | Объединение рамок таблицы | `border-collapse: <значение>;` | [htmlbook.ru/css/border-collapse](https://htmlbook.ru/css/border-collapse) |
| `border-color` | Цвет всех рамок | `border-color: <цвет>;` | [htmlbook.ru/css/border-color](https://htmlbook.ru/css/border-color) |
| `border-image` | Изображение-рамка | `border-image: <источник> <срез> / <ширина> <повтор>;` | [htmlbook.ru/css/border-image](https://htmlbook.ru/css/border-image) |
| `border-left` | Рамка слева | `border-left: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/border-left](https://htmlbook.ru/css/border-left) |
| `border-radius` | Скругление углов | `border-radius: <радиус>;` | [htmlbook.ru/css/border-radius](https://htmlbook.ru/css/border-radius) |
| `border-right` | Рамка справа | `border-right: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/border-right](https://htmlbook.ru/css/border-right) |
| `border-style` | Стиль всех рамок | `border-style: <стиль>;` | [htmlbook.ru/css/border-style](https://htmlbook.ru/css/border-style) |
| `border-top` | Рамка сверху | `border-top: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/border-top](https://htmlbook.ru/css/border-top) |
| `border-top-left-radius` | Скругление левого верхнего угла | `border-top-left-radius: <радиус>;` | [htmlbook.ru/css/border-top-left-radius](https://htmlbook.ru/css/border-top-left-radius) |
| `border-top-right-radius` | Скругление правого верхнего угла | `border-top-right-radius: <радиус>;` | [htmlbook.ru/css/border-top-right-radius](https://htmlbook.ru/css/border-top-right-radius) |
| `border-width` | Толщина всех рамок | `border-width: <толщина>;` | [htmlbook.ru/css/border-width](https://htmlbook.ru/css/border-width) |
| `bottom` | Положение снизу | `bottom: <размер>;` | [htmlbook.ru/css/bottom](https://htmlbook.ru/css/bottom) |
| `box-shadow` | Тень блока | `box-shadow: <x> <y> <размытие> <распространение> <цвет>;` | [htmlbook.ru/css/box-shadow](https://htmlbook.ru/css/box-shadow) |
| `box-sizing` | Модель расчёта размеров | `box-sizing: <значение>;` | [htmlbook.ru/css/box-sizing](https://htmlbook.ru/css/box-sizing) |

### C

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `caption-side` | Положение заголовка таблицы | `caption-side: <значение>;` | [htmlbook.ru/css/caption-side](https://htmlbook.ru/css/caption-side) |
| `clear` | Запрет обтекания | `clear: <значение>;` | [htmlbook.ru/css/clear](https://htmlbook.ru/css/clear) |
| `color` | Цвет текста | `color: <цвет>;` | [htmlbook.ru/css/color](https://htmlbook.ru/css/color) |
| `column-count` | Количество колонок | `column-count: <число>;` | [htmlbook.ru/css/column-count](https://htmlbook.ru/css/column-count) |
| `column-gap` | Расстояние между колонками | `column-gap: <размер>;` | [htmlbook.ru/css/column-gap](https://htmlbook.ru/css/column-gap) |
| `column-rule` | Линия между колонками | `column-rule: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/column-rule](https://htmlbook.ru/css/column-rule) |
| `column-span` | Объединение колонок | `column-span: <значение>;` | [htmlbook.ru/css/column-span](https://htmlbook.ru/css/column-span) |
| `column-width` | Ширина колонки | `column-width: <размер>;` | [htmlbook.ru/css/column-width](https://htmlbook.ru/css/column-width) |
| `columns` | Сокращённая запись колонок | `columns: <ширина> <количество>;` | [htmlbook.ru/css/columns](https://htmlbook.ru/css/columns) |
| `content` | Содержимое псевдоэлемента | `content: <значение>;` | [htmlbook.ru/css/content](https://htmlbook.ru/css/content) |
| `counter-increment` | Увеличение счётчика | `counter-increment: <имя> <число>;` | [htmlbook.ru/css/counter-increment](https://htmlbook.ru/css/counter-increment) |
| `counter-reset` | Сброс счётчика | `counter-reset: <имя> <число>;` | [htmlbook.ru/css/counter-reset](https://htmlbook.ru/css/counter-reset) |
| `cursor` | Курсор мыши | `cursor: <тип>;` | [htmlbook.ru/css/cursor](https://htmlbook.ru/css/cursor) |

### D

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `direction` | Направление текста | `direction: <значение>;` | [htmlbook.ru/css/direction](https://htmlbook.ru/css/direction) |
| `display` | Тип отображения | `display: <значение>;` | [htmlbook.ru/css/display](https://htmlbook.ru/css/display)  |

### E

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `empty-cells` | Отображение пустых ячеек | `empty-cells: <значение>;` | [htmlbook.ru/css/empty-cells](https://htmlbook.ru/css/empty-cells) |

### F

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `filter` | Графические эффекты | `filter: <функция>;` | [htmlbook.ru/css/filter](https://htmlbook.ru/css/filter) |
| `flex` | Сокращённая запись flex | `flex: <растяжение> <сжатие> <база>;` | [htmlbook.ru/css/flex](https://htmlbook.ru/css/flex) |
| `flex-basis` | Базовый размер flex-элемента | `flex-basis: <размер>;` | [htmlbook.ru/css/flex-basis](https://htmlbook.ru/css/flex-basis) |
| `flex-direction` | Направление главной оси | `flex-direction: <направление>;` | [htmlbook.ru/css/flex-direction](https://htmlbook.ru/css/flex-direction) |
| `flex-flow` | Направление + перенос | `flex-flow: <направление> <перенос>;` | [htmlbook.ru/css/flex-flow](https://htmlbook.ru/css/flex-flow) |
| `flex-grow` | Коэффициент растяжения | `flex-grow: <число>;` | [htmlbook.ru/css/flex-grow](https://htmlbook.ru/css/flex-grow) |
| `flex-shrink` | Коэффициент сжатия | `flex-shrink: <число>;` | [htmlbook.ru/css/flex-shrink](https://htmlbook.ru/css/flex-shrink) |
| `flex-wrap` | Перенос flex-элементов | `flex-wrap: <режим>;` | [htmlbook.ru/css/flex-wrap](https://htmlbook.ru/css/flex-wrap) |
| `float` | Обтекание | `float: <значение>;` | [htmlbook.ru/css/float](https://htmlbook.ru/css/float) |
| `font` | Сокращённая запись шрифта | `font: <стиль> <вариант> <жирность> <размер>/<высота> <семейство>;` | [htmlbook.ru/css/font](https://htmlbook.ru/css/font) |
| `font-family` | Семейство шрифта | `font-family: <шрифт>, <запасной>;` | [htmlbook.ru/css/font-family](https://htmlbook.ru/css/font-family) |
| `font-size` | Размер шрифта | `font-size: <размер>;` | [htmlbook.ru/css/font-size](https://htmlbook.ru/css/font-size) |
| `font-style` | Стиль шрифта | `font-style: <стиль>;` | [htmlbook.ru/css/font-style](https://htmlbook.ru/css/font-style) |
| `font-variant` | Вариант шрифта | `font-variant: <значение>;` | [htmlbook.ru/css/font-variant](https://htmlbook.ru/css/font-variant) |
| `font-weight` | Жирность шрифта | `font-weight: <жирность>;` | [htmlbook.ru/css/font-weight](https://htmlbook.ru/css/font-weight) |

### G

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `gap` | Расстояние между элементами | `gap: <размер>;` | [htmlbook.ru/css/gap](https://htmlbook.ru/css/gap) |
| `grid` | Сокращённая запись Grid | `grid: <шаблон>;` | [htmlbook.ru/css/grid](https://htmlbook.ru/css/grid) |
| `grid-area` | Область Grid | `grid-area: <имя>;` | [htmlbook.ru/css/grid-area](https://htmlbook.ru/css/grid-area) |
| `grid-column` | Колонки Grid | `grid-column: <начало> / <конец>;` | [htmlbook.ru/css/grid-column](https://htmlbook.ru/css/grid-column) |
| `grid-row` | Строки Grid | `grid-row: <начало> / <конец>;` | [htmlbook.ru/css/grid-row](https://htmlbook.ru/css/grid-row) |
| `grid-template-columns` | Шаблон колонок | `grid-template-columns: <размеры>;` | [htmlbook.ru/css/grid-template-columns](https://htmlbook.ru/css/grid-template-columns) |
| `grid-template-rows` | Шаблон строк | `grid-template-rows: <размеры>;` | [htmlbook.ru/css/grid-template-rows](https://htmlbook.ru/css/grid-template-rows) |

### H

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `height` | Высота элемента | `height: <размер>;` | [htmlbook.ru/css/height](https://htmlbook.ru/css/height) |

### I

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `isolation` | Изоляция контекста наложения | `isolation: <значение>;` | [htmlbook.ru/css/isolation](https://htmlbook.ru/css/isolation) |

### J

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `justify-content` | Выравнивание по главной оси | `justify-content: <выравнивание>;` | [htmlbook.ru/css/justify-content](https://htmlbook.ru/css/justify-content) |

### L

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `left` | Положение слева | `left: <размер>;` | [htmlbook.ru/css/left](https://htmlbook.ru/css/left) |
| `letter-spacing` | Расстояние между буквами | `letter-spacing: <размер>;` | [htmlbook.ru/css/letter-spacing](https://htmlbook.ru/css/letter-spacing) |
| `line-height` | Межстрочный интервал | `line-height: <значение>;` | [htmlbook.ru/css/line-height](https://htmlbook.ru/css/line-height) |
| `list-style` | Сокращённая запись списка | `list-style: <тип> <позиция> <изображение>;` | [htmlbook.ru/css/list-style](https://htmlbook.ru/css/list-style) |
| `list-style-image` | Маркер-изображение | `list-style-image: url('<путь>');` | [htmlbook.ru/css/list-style-image](https://htmlbook.ru/css/list-style-image) |
| `list-style-position` | Позиция маркера | `list-style-position: <значение>;` | [htmlbook.ru/css/list-style-position](https://htmlbook.ru/css/list-style-position) |
| `list-style-type` | Тип маркера | `list-style-type: <тип>;` | [htmlbook.ru/css/list-style-type](https://htmlbook.ru/css/list-style-type) |

### M

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `margin` | Внешние отступы | `margin: <верх> <право> <низ> <лево>;` | [htmlbook.ru/css/margin](https://htmlbook.ru/css/margin) |
| `margin-bottom` | Внешний отступ снизу | `margin-bottom: <размер>;` | [htmlbook.ru/css/margin-bottom](https://htmlbook.ru/css/margin-bottom) |
| `margin-left` | Внешний отступ слева | `margin-left: <размер>;` | [htmlbook.ru/css/margin-left](https://htmlbook.ru/css/margin-left) |
| `margin-right` | Внешний отступ справа | `margin-right: <размер>;` | [htmlbook.ru/css/margin-right](https://htmlbook.ru/css/margin-right) |
| `margin-top` | Внешний отступ сверху | `margin-top: <размер>;` | [htmlbook.ru/css/margin-top](https://htmlbook.ru/css/margin-top) |
| `max-height` | Максимальная высота | `max-height: <размер>;` | [htmlbook.ru/css/max-height](https://htmlbook.ru/css/max-height) |
| `max-width` | Максимальная ширина | `max-width: <размер>;` | [htmlbook.ru/css/max-width](https://htmlbook.ru/css/max-width) |
| `min-height` | Минимальная высота | `min-height: <размер>;` | [htmlbook.ru/css/min-height](https://htmlbook.ru/css/min-height) |
| `min-width` | Минимальная ширина | `min-width: <размер>;` | [htmlbook.ru/css/min-width](https://htmlbook.ru/css/min-width) |

### O

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `object-fit` | Масштабирование изображения | `object-fit: <значение>;` | [htmlbook.ru/css/object-fit](https://htmlbook.ru/css/object-fit) |
| `opacity` | Прозрачность | `opacity: <число>;` | [htmlbook.ru/css/opacity](https://htmlbook.ru/css/opacity) |
| `order` | Порядок flex-элемента | `order: <число>;` | [htmlbook.ru/css/order](https://htmlbook.ru/css/order) |
| `outline` | Внешняя рамка (контур) | `outline: <ширина> <стиль> <цвет>;` | [htmlbook.ru/css/outline](https://htmlbook.ru/css/outline) |
| `outline-color` | Цвет контура | `outline-color: <цвет>;` | [htmlbook.ru/css/outline-color](https://htmlbook.ru/css/outline-color) |
| `outline-offset` | Смещение контура | `outline-offset: <размер>;` | [htmlbook.ru/css/outline-offset](https://htmlbook.ru/css/outline-offset) |
| `outline-style` | Стиль контура | `outline-style: <стиль>;` | [htmlbook.ru/css/outline-style](https://htmlbook.ru/css/outline-style) |
| `outline-width` | Толщина контура | `outline-width: <толщина>;` | [htmlbook.ru/css/outline-width](https://htmlbook.ru/css/outline-width) |
| `overflow` | Переполнение содержимого | `overflow: <значение>;` | [htmlbook.ru/css/overflow](https://htmlbook.ru/css/overflow) |
| `overflow-wrap` | Перенос длинных слов | `overflow-wrap: <значение>;` | [htmlbook.ru/css/overflow-wrap](https://htmlbook.ru/css/overflow-wrap) |
| `overflow-x` | Переполнение по горизонтали | `overflow-x: <значение>;` | [htmlbook.ru/css/overflow-x](https://htmlbook.ru/css/overflow-x) |
| `overflow-y` | Переполнение по вертикали | `overflow-y: <значение>;` | [htmlbook.ru/css/overflow-y](https://htmlbook.ru/css/overflow-y) |

### P

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `padding` | Внутренние отступы | `padding: <верх> <право> <низ> <лево>;` | [htmlbook.ru/css/padding](https://htmlbook.ru/css/padding) |
| `padding-bottom` | Внутренний отступ снизу | `padding-bottom: <размер>;` | [htmlbook.ru/css/padding-bottom](https://htmlbook.ru/css/padding-bottom) |
| `padding-left` | Внутренний отступ слева | `padding-left: <размер>;` | [htmlbook.ru/css/padding-left](https://htmlbook.ru/css/padding-left) |
| `padding-right` | Внутренний отступ справа | `padding-right: <размер>;` | [htmlbook.ru/css/padding-right](https://htmlbook.ru/css/padding-right) |
| `padding-top` | Внутренний отступ сверху | `padding-top: <размер>;` | [htmlbook.ru/css/padding-top](https://htmlbook.ru/css/padding-top) |
| `perspective` | Перспектива 3D | `perspective: <размер>;` | [htmlbook.ru/css/perspective](https://htmlbook.ru/css/perspective) |
| `pointer-events` | Реакция на события мыши | `pointer-events: <значение>;` | [htmlbook.ru/css/pointer-events](https://htmlbook.ru/css/pointer-events) |
| `position` | Позиционирование | `position: <значение>;` | [htmlbook.ru/css/position](https://htmlbook.ru/css/position) |

### Q

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `quotes` | Кавычки для цитат | `quotes: <пары>;` | [htmlbook.ru/css/quotes](https://htmlbook.ru/css/quotes) |

### R

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `right` | Положение справа | `right: <размер>;` | [htmlbook.ru/css/right](https://htmlbook.ru/css/right) |

### S

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `scroll-behavior` | Плавность прокрутки | `scroll-behavior: <значение>;` | [htmlbook.ru/css/scroll-behavior](https://htmlbook.ru/css/scroll-behavior) |

### T

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `table-layout` | Алгоритм раскладки таблицы | `table-layout: <значение>;` | [htmlbook.ru/css/table-layout](https://htmlbook.ru/css/table-layout) |
| `text-align` | Выравнивание текста | `text-align: <выравнивание>;` | [htmlbook.ru/css/text-align](https://htmlbook.ru/css/text-align) |
| `text-decoration` | Оформление текста | `text-decoration: <линия>;` | [htmlbook.ru/css/text-decoration](https://htmlbook.ru/css/text-decoration) |
| `text-indent` | Отступ первой строки | `text-indent: <размер>;` | [htmlbook.ru/css/text-indent](https://htmlbook.ru/css/text-indent) |
| `text-overflow` | Переполнение текста | `text-overflow: <значение>;` | [htmlbook.ru/css/text-overflow](https://htmlbook.ru/css/text-overflow) |
| `text-shadow` | Тень текста | `text-shadow: <x> <y> <размытие> <цвет>;` | [htmlbook.ru/css/text-shadow](https://htmlbook.ru/css/text-shadow) |
| `text-transform` | Регистр текста | `text-transform: <регистр>;` | [htmlbook.ru/css/text-transform](https://htmlbook.ru/css/text-transform) |
| `top` | Положение сверху | `top: <размер>;` | [htmlbook.ru/css/top](https://htmlbook.ru/css/top) |
| `transform` | Трансформация элемента | `transform: <функция>;` | [htmlbook.ru/css/transform](https://htmlbook.ru/css/transform) |
| `transition` | Плавный переход | `transition: <свойство> <длительность> <функция> <задержка>;` | [htmlbook.ru/css/transition](https://htmlbook.ru/css/transition) |
| `transition-delay` | Задержка перехода | `transition-delay: <время>;` | [htmlbook.ru/css/transition-delay](https://htmlbook.ru/css/transition-delay) |
| `transition-duration` | Длительность перехода | `transition-duration: <время>;` | [htmlbook.ru/css/transition-duration](https://htmlbook.ru/css/transition-duration) |
| `transition-property` | Свойство для перехода | `transition-property: <свойство>;` | [htmlbook.ru/css/transition-property](https://htmlbook.ru/css/transition-property) |
| `transition-timing-function` | Скорость перехода | `transition-timing-function: <значение>;` | [htmlbook.ru/css/transition-timing-function](https://htmlbook.ru/css/transition-timing-function) |

### U

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `user-select` | Выделение текста пользователем | `user-select: <значение>;` | [htmlbook.ru/css/user-select](https://htmlbook.ru/css/user-select) |

### V

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `vertical-align` | Вертикальное выравнивание | `vertical-align: <значение>;` | [htmlbook.ru/css/vertical-align](https://htmlbook.ru/css/vertical-align) |
| `visibility` | Видимость элемента | `visibility: <значение>;` | [htmlbook.ru/css/visibility](https://htmlbook.ru/css/visibility) |

### W

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `white-space` | Обработка пробелов | `white-space: <режим>;` | [htmlbook.ru/css/white-space](https://htmlbook.ru/css/white-space) |
| `width` | Ширина элемента | `width: <размер>;` | [htmlbook.ru/css/width](https://htmlbook.ru/css/width) |
| `word-break` | Перенос слов | `word-break: <режим>;` | [htmlbook.ru/css/word-break](https://htmlbook.ru/css/word-break) |
| `word-spacing` | Расстояние между словами | `word-spacing: <размер>;` | [htmlbook.ru/css/word-spacing](https://htmlbook.ru/css/word-spacing) |
| `writing-mode` | Направление письма | `writing-mode: <значение>;` | [htmlbook.ru/css/writing-mode](https://htmlbook.ru/css/writing-mode) |

### Z

| Свойство | Описание | Синтаксис | Ссылка |
|----------|----------|-----------|--------|
| `z-index` | Порядок наложения | `z-index: <число>;` | [htmlbook.ru/css/z-index](https://htmlbook.ru/css/z-index) |

---

## ⚠️ Устаревшие и неиспользуемые свойства

| Свойство | Описание | Статус | Альтернатива | Ссылка |
|----------|----------|--------|--------------|--------|
| `clip` | Обрезка элемента | ⚠️ Устаревшее | `clip-path` | [htmlbook.ru/css/clip](https://htmlbook.ru/css/clip) |
| `word-wrap` | Перенос слов | ⚠️ Устаревшее | `overflow-wrap` | [htmlbook.ru/css/word-wrap](https://htmlbook.ru/css/word-wrap) |
| `azimuth` | Звуковое позиционирование | ❌ Не используется | Удалено из спецификации | — |
| `elevation` | Звуковое позиционирование | ❌ Не используется | Удалено из спецификации | — |
| `pause` | Звуковая пауза | ❌ Не используется | Удалено из спецификации | — |
| `pitch` | Звуковой тон | ❌ Не используется | Удалено из спецификации | — |
| `play-during` | Звуковое сопровождение | ❌ Не используется | Удалено из спецификации | — |
| `speak` | Озвучивание | ❌ Не используется | Удалено из спецификации | — |
| `volume` | Громкость | ❌ Не используется | Удалено из спецификации | — |

---

## 📝 @-правила

| @-правило | Описание | Пример | Ссылка |
|-----------|----------|--------|--------|
| `@media` | Медиазапросы для адаптивности | `@media (max-width: 600px) { ... }` | [htmlbook.ru/css/media](https://htmlbook.ru/css/media) |
| `@keyframes` | Определение анимации | `@keyframes slide { from { left: 0; } to { left: 100px; } }` | [htmlbook.ru/css/keyframes](https://htmlbook.ru/css/keyframes) |
| `@font-face` | Подключение шрифта | `@font-face { font-family: 'MyFont'; src: url('font.woff2'); }` | [htmlbook.ru/css/font-face](https://htmlbook.ru/css/font-face) |
| `@import` | Импорт другого CSS | `@import url('style.css');` | [htmlbook.ru/css/import](https://htmlbook.ru/css/import) |
| `@supports` | Проверка поддержки свойства | `@supports (display: grid) { ... }` | [htmlbook.ru/css/supports](https://htmlbook.ru/css/supports) |

---

## 🎭 Псевдоклассы

| Псевдокласс | Описание | Пример | Ссылка |
|-------------|----------|--------|--------|
| `:hover` | Наведение курсора | `a:hover { color: red; }` | [htmlbook.ru/css/hover](https://htmlbook.ru/css/hover) |
| `:active` | Нажатие | `button:active { transform: scale(0.98); }` | [htmlbook.ru/css/active](https://htmlbook.ru/css/active) |
| `:focus` | Фокус (клик или Tab) | `input:focus { border-color: blue; }` | [htmlbook.ru/css/focus](https://htmlbook.ru/css/focus) |
| `:visited` | Посещённая ссылка | `a:visited { color: purple; }` | [htmlbook.ru/css/visited](https://htmlbook.ru/css/visited) |
| `:link` | Непосещённая ссылка | `a:link { color: blue; }` | [htmlbook.ru/css/link](https://htmlbook.ru/css/link) |
| `:first-child` | Первый ребёнок | `li:first-child { font-weight: bold; }` | [htmlbook.ru/css/first-child](https://htmlbook.ru/css/first-child) |
| `:last-child` | Последний ребёнок | `li:last-child { margin-bottom: 0; }` | [htmlbook.ru/css/last-child](https://htmlbook.ru/css/last-child) |
| `:nth-child(n)` | n-й ребёнок | `tr:nth-child(even) { background: #f2f2f2; }` | [htmlbook.ru/css/nth-child](https://htmlbook.ru/css/nth-child) |
| `:not(селектор)` | Исключение | `p:not(.special) { color: #333; }` | [htmlbook.ru/css/not](https://htmlbook.ru/css/not) |
| `:checked` | Отмеченный чекбокс/радио | `input:checked + label { font-weight: bold; }` | [htmlbook.ru/css/checked](https://htmlbook.ru/css/checked) |
| `:disabled` | Отключённый элемент | `input:disabled { opacity: 0.5; }` | [htmlbook.ru/css/disabled](https://htmlbook.ru/css/disabled) |

---

## ✨ Псевдоэлементы

| Псевдоэлемент | Описание | Пример | Ссылка |
|---------------|----------|--------|--------|
| `::before` | Вставка до содержимого | `p::before { content: "→ "; }` | [htmlbook.ru/css/before](https://htmlbook.ru/css/before) |
| `::after` | Вставка после содержимого | `p::after { content: " ←"; }` | [htmlbook.ru/css/after](https://htmlbook.ru/css/after) |
| `::first-line` | Первая строка | `p::first-line { font-weight: bold; }` | [htmlbook.ru/css/first-line](https://htmlbook.ru/css/first-line) |
| `::first-letter` | Первая буква | `p::first-letter { font-size: 2em; }` | [htmlbook.ru/css/first-letter](https://htmlbook.ru/css/first-letter) |
| `::selection` | Выделенный текст | `::selection { background: yellow; }` | [htmlbook.ru/css/selection](https://htmlbook.ru/css/selection) |
| `::placeholder` | Плейсхолдер поля ввода | `input::placeholder { color: #999; }` | [htmlbook.ru/css/placeholder](https://htmlbook.ru/css/placeholder) |

---

## 📐 Единицы измерения

| Единица | Описание |
|---------|----------|
| `px` | Пиксели |
| `%` | Процент от родителя |
| `em` | Относительно размера шрифта родителя |
| `rem` | Относительно размера шрифта корневого элемента (`html`) |
| `vw` | 1% от ширины окна просмотра |
| `vh` | 1% от высоты окна просмотра |
| `vmin` | 1% от меньшей стороны окна |
| `vmax` | 1% от большей стороны окна |
| `s`, `ms` | Секунды, миллисекунды |
| `deg` | Градусы (для поворота) |
| `fr` | Фракция (для Grid) |

---

## 💡 Полезные советы

1. **Всегда используйте** `box-sizing: border-box;` — это упрощает расчёт размеров.
2. **Центрирование блока по горизонтали:** `margin: 0 auto;` (при заданной ширине).
3. **Центрирование через Flexbox:** `display: flex; justify-content: center; align-items: center;`
4. **Убирайте подчёркивание ссылок:** `text-decoration: none;`
5. **Добавляйте плавность:** `transition: all 0.3s ease;`
6. **Используйте переменные CSS:**

```css
:root {
    --primary-color: #2196f3;
    --spacing: 16px;
}

.button {
    background: var(--primary-color);
    padding: var(--spacing);
}
```

---

*Шпаргалка создана на основе справочника CSS от htmlbook.ru. Все ссылки ведут на соответствующие страницы свойств.*
