# 📗 Шпаргалка: CSS — полный справочник свойств

> **Как пользоваться:** ищи поиском (Ctrl+F) по названию свойства или по описанию на русском.
> Например: «отступ внутри», «рамка», «тень», «жирность текста».
> **Название каждого свойства — это ссылка** на страницу справочника htmlbook.ru. Кликните по нему, чтобы открыть подробное описание с примерами и таблицами поддержки браузеров.

---

## 📖 Что такое CSS

**CSS** (Cascading Style Sheets — каскадные таблицы стилей) — язык описания внешнего вида HTML-документа.
CSS указывает браузеру, **как** отображать элементы: цвет, шрифт, отступы, рамки, расположение.

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
| RGB | `rgb(255, 0, 0)` | Красный, зелёный, синий |
| RGBA | `rgba(255, 0, 0, 0.5)` | С прозрачностью |
| HSL | `hsl(0, 100%, 50%)` | Тон, насыщенность, светлота |

### Свойства текста

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [color](https://htmlbook.ru/css/color) | Цвет текста | `color: <цвет>;` | `color: #333;` |
| [font-family](https://htmlbook.ru/css/font-family) | Семейство шрифта (гарнитура) | `font-family: <шрифт>, <запасной>;` | `font-family: Arial, sans-serif;` |
| [font-size](https://htmlbook.ru/css/font-size) | Размер шрифта | `font-size: <размер>;` | `font-size: 18px;` |
| [font-weight](https://htmlbook.ru/css/font-weight) | Жирность (насыщенность) шрифта | `font-weight: <жирность>;` | `font-weight: bold;` |
| [font-style](https://htmlbook.ru/css/font-style) | Стиль шрифта (курсив) | `font-style: <стиль>;` | `font-style: italic;` |
| [text-align](https://htmlbook.ru/css/text-align) | Выравнивание текста по горизонтали | `text-align: <выравнивание>;` | `text-align: center;` |
| [line-height](https://htmlbook.ru/css/line-height) | Межстрочный интервал (высота строки) | `line-height: <высота>;` | `line-height: 1.5;` |
| [text-decoration](https://htmlbook.ru/css/text-decoration) | Оформление текста линией (подчёркивание) | `text-decoration: <линия>;` | `text-decoration: none;` |
| [text-transform](https://htmlbook.ru/css/text-transform) | Изменение регистра букв | `text-transform: <регистр>;` | `text-transform: uppercase;` |
| [letter-spacing](https://htmlbook.ru/css/letter-spacing) | Расстояние между буквами | `letter-spacing: <расстояние>;` | `letter-spacing: 1px;` |
| [text-indent](https://htmlbook.ru/css/text-indent) | Отступ первой строки (красная строка) | `text-indent: <отступ>;` | `text-indent: 20px;` |
| [text-shadow](https://htmlbook.ru/css/text-shadow) | Тень текста | `text-shadow: <x> <y> <размытие> <цвет>;` | `text-shadow: 2px 2px 4px #000;` |
| [word-spacing](https://htmlbook.ru/css/word-spacing) | Расстояние между словами | `word-spacing: <расстояние>;` | `word-spacing: 5px;` |
| [white-space](https://htmlbook.ru/css/white-space) | Обработка пробелов и переносов | `white-space: <режим>;` | `white-space: nowrap;` |
| [text-overflow](https://htmlbook.ru/css/text-overflow) | Отображение переполнения текста | `text-overflow: <режим>;` | `text-overflow: ellipsis;` |

---

## 📦 Блочная модель — размеры и отступы

### Размеры

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [width](https://htmlbook.ru/css/width) | Ширина элемента | `width: <размер>;` | `width: 300px;` |
| [height](https://htmlbook.ru/css/height) | Высота элемента | `height: <размер>;` | `height: 200px;` |
| [max-width](https://htmlbook.ru/css/max-width) | Максимальная ширина | `max-width: <размер>;` | `max-width: 800px;` |
| [min-width](https://htmlbook.ru/css/min-width) | Минимальная ширина | `min-width: <размер>;` | `min-width: 200px;` |
| [max-height](https://htmlbook.ru/css/max-height) | Максимальная высота | `max-height: <размер>;` | `max-height: 500px;` |
| [min-height](https://htmlbook.ru/css/min-height) | Минимальная высота | `min-height: <размер>;` | `min-height: 100px;` |

### Внешние отступы (margin)

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [margin](https://htmlbook.ru/css/margin) | Внешний отступ со всех сторон | `margin: <верх> <право> <низ> <лево>;` | `margin: 10px 20px;` |
| [margin-top](https://htmlbook.ru/css/margin-top) | Внешний отступ сверху | `margin-top: <размер>;` | `margin-top: 10px;` |
| [margin-right](https://htmlbook.ru/css/margin-right) | Внешний отступ справа | `margin-right: <размер>;` | `margin-right: 20px;` |
| [margin-bottom](https://htmlbook.ru/css/margin-bottom) | Внешний отступ снизу | `margin-bottom: <размер>;` | `margin-bottom: 10px;` |
| [margin-left](https://htmlbook.ru/css/margin-left) | Внешний отступ слева | `margin-left: <размер>;` | `margin-left: 20px;` |

### Внутренние отступы (padding)

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [padding](https://htmlbook.ru/css/padding) | Внутренний отступ со всех сторон | `padding: <верх> <право> <низ> <лево>;` | `padding: 15px;` |
| [padding-top](https://htmlbook.ru/css/padding-top) | Внутренний отступ сверху | `padding-top: <размер>;` | `padding-top: 10px;` |
| [padding-right](https://htmlbook.ru/css/padding-right) | Внутренний отступ справа | `padding-right: <размер>;` | `padding-right: 20px;` |
| [padding-bottom](https://htmlbook.ru/css/padding-bottom) | Внутренний отступ снизу | `padding-bottom: <размер>;` | `padding-bottom: 10px;` |
| [padding-left](https://htmlbook.ru/css/padding-left) | Внутренний отступ слева | `padding-left: <размер>;` | `padding-left: 20px;` |
| [box-sizing](https://htmlbook.ru/css/box-sizing) | Модель расчёта размеров (учитывать padding и border) | `box-sizing: <значение>;` | `box-sizing: border-box;` |

---

## 🖼️ Рамки, фон и тень

### Рамки

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [border](https://htmlbook.ru/css/border) | Рамка со всех сторон (сокращённая запись) | `border: <ширина> <стиль> <цвет>;` | `border: 1px solid #ccc;` |
| [border-width](https://htmlbook.ru/css/border-width) | Толщина рамки | `border-width: <толщина>;` | `border-width: 2px;` |
| [border-style](https://htmlbook.ru/css/border-style) | Стиль рамки (сплошная, пунктир) | `border-style: <стиль>;` | `border-style: dashed;` |
| [border-color](https://htmlbook.ru/css/border-color) | Цвет рамки | `border-color: <цвет>;` | `border-color: red;` |
| [border-radius](https://htmlbook.ru/css/border-radius) | Скругление углов | `border-radius: <радиус>;` | `border-radius: 8px;` |
| [border-top](https://htmlbook.ru/css/border-top) | Рамка сверху | `border-top: <ширина> <стиль> <цвет>;` | `border-top: 2px solid blue;` |
| [border-right](https://htmlbook.ru/css/border-right) | Рамка справа | `border-right: <ширина> <стиль> <цвет>;` | `border-right: 2px solid blue;` |
| [border-bottom](https://htmlbook.ru/css/border-bottom) | Рамка снизу | `border-bottom: <ширина> <стиль> <цвет>;` | `border-bottom: 2px solid blue;` |
| [border-left](https://htmlbook.ru/css/border-left) | Рамка слева | `border-left: <ширина> <стиль> <цвет>;` | `border-left: 2px solid blue;` |

### Фон

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [background-color](https://htmlbook.ru/css/background-color) | Цвет фона | `background-color: <цвет>;` | `background-color: #f0f0f0;` |
| [background-image](https://htmlbook.ru/css/background-image) | Фоновое изображение | `background-image: url('<путь>');` | `background-image: url('bg.png');` |
| [background-size](https://htmlbook.ru/css/background-size) | Размер фонового изображения | `background-size: <размер>;` | `background-size: cover;` |
| [background-repeat](https://htmlbook.ru/css/background-repeat) | Повтор фонового изображения | `background-repeat: <режим>;` | `background-repeat: no-repeat;` |
| [background-position](https://htmlbook.ru/css/background-position) | Позиция фонового изображения | `background-position: <x> <y>;` | `background-position: center;` |
| [background-attachment](https://htmlbook.ru/css/background-attachment) | Прокрутка фона вместе с содержимым | `background-attachment: <режим>;` | `background-attachment: fixed;` |
| [background](https://htmlbook.ru/css/background) | Фон (сокращённая запись) | `background: <цвет> <изображение> ...;` | `background: #fff url('bg.png') center / cover no-repeat;` |

### Тень

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [box-shadow](https://htmlbook.ru/css/box-shadow) | Тень блока | `box-shadow: <x> <y> <размытие> <цвет>;` | `box-shadow: 0 2px 5px rgba(0,0,0,0.1);` |
| [text-shadow](https://htmlbook.ru/css/text-shadow) | Тень текста | `text-shadow: <x> <y> <размытие> <цвет>;` | `text-shadow: 1px 1px 2px #000;` |

---

## 📐 Display — тип отображения

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [display](https://htmlbook.ru/css/display) | Тип отображения элемента (блочный, строчный, flex, grid) | `display: <значение>;` | `display: flex;` |
| [visibility](https://htmlbook.ru/css/visibility) | Видимость элемента (скрыть, но оставить место) | `visibility: <значение>;` | `visibility: hidden;` |
| [opacity](https://htmlbook.ru/css/opacity) | Прозрачность элемента | `opacity: <число>;` | `opacity: 0.5;` |

---

## 🧩 Flexbox — выравнивание и раскладка

### Свойства контейнера

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [flex-direction](https://htmlbook.ru/css/flex-direction) | Направление главной оси flex-контейнера | `flex-direction: <направление>;` | `flex-direction: column;` |
| [justify-content](https://htmlbook.ru/css/justify-content) | Выравнивание по главной оси | `justify-content: <выравнивание>;` | `justify-content: center;` |
| [align-items](https://htmlbook.ru/css/align-items) | Выравнивание по поперечной оси | `align-items: <выравнивание>;` | `align-items: center;` |
| [align-content](https://htmlbook.ru/css/align-content) | Выравнивание строк (при переносе) | `align-content: <выравнивание>;` | `align-content: space-between;` |
| [flex-wrap](https://htmlbook.ru/css/flex-wrap) | Перенос flex-элементов на новую строку | `flex-wrap: <режим>;` | `flex-wrap: wrap;` |
| [gap](https://htmlbook.ru/css/gap) | Расстояние между flex-элементами | `gap: <размер>;` | `gap: 10px;` |

### Свойства элементов

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [flex](https://htmlbook.ru/css/flex) | Растяжение, сжатие и базовый размер элемента | `flex: <растяжение> <сжатие> <база>;` | `flex: 1 1 200px;` |
| [flex-grow](https://htmlbook.ru/css/flex-grow) | Коэффициент растяжения элемента | `flex-grow: <число>;` | `flex-grow: 2;` |
| [flex-shrink](https://htmlbook.ru/css/flex-shrink) | Коэффициент сжатия элемента | `flex-shrink: <число>;` | `flex-shrink: 0;` |
| [flex-basis](https://htmlbook.ru/css/flex-basis) | Базовый размер flex-элемента | `flex-basis: <размер>;` | `flex-basis: 200px;` |
| [order](https://htmlbook.ru/css/order) | Порядок элемента во flex-контейнере | `order: <число>;` | `order: 2;` |
| [align-self](https://htmlbook.ru/css/align-self) | Выравнивание отдельного элемента | `align-self: <выравнивание>;` | `align-self: flex-end;` |

---

## 📍 Позиционирование

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [position](https://htmlbook.ru/css/position) | Способ позиционирования элемента | `position: <значение>;` | `position: relative;` |
| [top](https://htmlbook.ru/css/top) | Смещение от верхнего края | `top: <размер>;` | `top: 10px;` |
| [right](https://htmlbook.ru/css/right) | Смещение от правого края | `right: <размер>;` | `right: 10px;` |
| [bottom](https://htmlbook.ru/css/bottom) | Смещение от нижнего края | `bottom: <размер>;` | `bottom: 10px;` |
| [left](https://htmlbook.ru/css/left) | Смещение от левого края | `left: <размер>;` | `left: 10px;` |
| [z-index](https://htmlbook.ru/css/z-index) | Порядок наложения элементов | `z-index: <число>;` | `z-index: 100;` |

---

## 📋 Полный список CSS-свойств по алфавиту

### A

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [align-content](https://htmlbook.ru/css/align-content) | Выравнивание строк во flex-контейнере | `align-content: <значение>;` | `align-content: center;` |
| [align-items](https://htmlbook.ru/css/align-items) | Выравнивание элементов по поперечной оси | `align-items: <значение>;` | `align-items: center;` |
| [align-self](https://htmlbook.ru/css/align-self) | Выравнивание отдельного элемента | `align-self: <значение>;` | `align-self: flex-end;` |
| [animation](https://htmlbook.ru/css/animation) | Сокращённая запись анимации | `animation: <имя> <длительность> ...;` | `animation: fadeIn 2s ease-in-out;` |
| [animation-delay](https://htmlbook.ru/css/animation-delay) | Задержка перед началом анимации | `animation-delay: <время>;` | `animation-delay: 0.5s;` |
| [animation-direction](https://htmlbook.ru/css/animation-direction) | Направление воспроизведения анимации | `animation-direction: <значение>;` | `animation-direction: alternate;` |
| [animation-duration](https://htmlbook.ru/css/animation-duration) | Длительность анимации | `animation-duration: <время>;` | `animation-duration: 2s;` |
| [animation-fill-mode](https://htmlbook.ru/css/animation-fill-mode) | Состояние до и после анимации | `animation-fill-mode: <значение>;` | `animation-fill-mode: forwards;` |
| [animation-iteration-count](https://htmlbook.ru/css/animation-iteration-count) | Количество повторов анимации | `animation-iteration-count: <число>;` | `animation-iteration-count: infinite;` |
| [animation-name](https://htmlbook.ru/css/animation-name) | Имя keyframes-анимации | `animation-name: <имя>;` | `animation-name: slideIn;` |
| [animation-play-state](https://htmlbook.ru/css/animation-play-state) | Пауза или запуск анимации | `animation-play-state: <значение>;` | `animation-play-state: paused;` |
| [animation-timing-function](https://htmlbook.ru/css/animation-timing-function) | Скорость (плавность) анимации | `animation-timing-function: <значение>;` | `animation-timing-function: ease-in;` |

### B

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [backface-visibility](https://htmlbook.ru/css/backface-visibility) | Видимость обратной стороны 3D-элемента | `backface-visibility: <значение>;` | `backface-visibility: hidden;` |
| [background](https://htmlbook.ru/css/background) | Фон (сокращённая запись) | `background: <цвет> <изображение> ...;` | `background: #fff url('bg.png') center / cover no-repeat;` |
| [background-attachment](https://htmlbook.ru/css/background-attachment) | Прокрутка фона вместе с содержимым | `background-attachment: <значение>;` | `background-attachment: fixed;` |
| [background-blend-mode](https://htmlbook.ru/css/background-blend-mode) | Режим смешивания фоновых слоёв | `background-blend-mode: <режим>;` | `background-blend-mode: multiply;` |
| [background-clip](https://htmlbook.ru/css/background-clip) | Область обрезки фона | `background-clip: <значение>;` | `background-clip: padding-box;` |
| [background-color](https://htmlbook.ru/css/background-color) | Цвет фона | `background-color: <цвет>;` | `background-color: #f0f0f0;` |
| [background-image](https://htmlbook.ru/css/background-image) | Фоновое изображение | `background-image: url('<путь>');` | `background-image: url('bg.png');` |
| [background-origin](https://htmlbook.ru/css/background-origin) | Начало координат фонового изображения | `background-origin: <значение>;` | `background-origin: content-box;` |
| [background-position](https://htmlbook.ru/css/background-position) | Позиция фонового изображения | `background-position: <x> <y>;` | `background-position: center;` |
| [background-repeat](https://htmlbook.ru/css/background-repeat) | Повтор фонового изображения | `background-repeat: <режим>;` | `background-repeat: no-repeat;` |
| [background-size](https://htmlbook.ru/css/background-size) | Размер фонового изображения | `background-size: <размер>;` | `background-size: cover;` |
| [border](https://htmlbook.ru/css/border) | Рамка со всех сторон (сокращённая запись) | `border: <ширина> <стиль> <цвет>;` | `border: 2px solid #333;` |
| [border-bottom](https://htmlbook.ru/css/border-bottom) | Рамка снизу | `border-bottom: <ширина> <стиль> <цвет>;` | `border-bottom: 1px dashed red;` |
| [border-bottom-color](https://htmlbook.ru/css/border-bottom-color) | Цвет нижней рамки | `border-bottom-color: <цвет>;` | `border-bottom-color: blue;` |
| [border-bottom-left-radius](https://htmlbook.ru/css/border-bottom-left-radius) | Скругление левого нижнего угла | `border-bottom-left-radius: <радиус>;` | `border-bottom-left-radius: 10px;` |
| [border-bottom-right-radius](https://htmlbook.ru/css/border-bottom-right-radius) | Скругление правого нижнего угла | `border-bottom-right-radius: <радиус>;` | `border-bottom-right-radius: 10px;` |
| [border-bottom-style](https://htmlbook.ru/css/border-bottom-style) | Стиль нижней рамки | `border-bottom-style: <стиль>;` | `border-bottom-style: dotted;` |
| [border-bottom-width](https://htmlbook.ru/css/border-bottom-width) | Толщина нижней рамки | `border-bottom-width: <толщина>;` | `border-bottom-width: 3px;` |
| [border-collapse](https://htmlbook.ru/css/border-collapse) | Объединение рамок таблицы | `border-collapse: <значение>;` | `border-collapse: collapse;` |
| [border-color](https://htmlbook.ru/css/border-color) | Цвет рамки | `border-color: <цвет>;` | `border-color: #ccc;` |
| [border-image](https://htmlbook.ru/css/border-image) | Изображение в качестве рамки | `border-image: <источник> <срез> ...;` | `border-image: url('border.png') 30 round;` |
| [border-left](https://htmlbook.ru/css/border-left) | Рамка слева | `border-left: <ширина> <стиль> <цвет>;` | `border-left: 2px solid green;` |
| [border-radius](https://htmlbook.ru/css/border-radius) | Скругление углов | `border-radius: <радиус>;` | `border-radius: 8px;` |
| [border-right](https://htmlbook.ru/css/border-right) | Рамка справа | `border-right: <ширина> <стиль> <цвет>;` | `border-right: 1px dotted #ccc;` |
| [border-style](https://htmlbook.ru/css/border-style) | Стиль рамки | `border-style: <стиль>;` | `border-style: solid;` |
| [border-top](https://htmlbook.ru/css/border-top) | Рамка сверху | `border-top: <ширина> <стиль> <цвет>;` | `border-top: 3px double black;` |
| [border-top-left-radius](https://htmlbook.ru/css/border-top-left-radius) | Скругление левого верхнего угла | `border-top-left-radius: <радиус>;` | `border-top-left-radius: 15px;` |
| [border-top-right-radius](https://htmlbook.ru/css/border-top-right-radius) | Скругление правого верхнего угла | `border-top-right-radius: <радиус>;` | `border-top-right-radius: 15px;` |
| [border-width](https://htmlbook.ru/css/border-width) | Толщина рамки | `border-width: <толщина>;` | `border-width: 2px;` |
| [bottom](https://htmlbook.ru/css/bottom) | Смещение от нижнего края | `bottom: <размер>;` | `bottom: 10px;` |
| [box-shadow](https://htmlbook.ru/css/box-shadow) | Тень блока | `box-shadow: <x> <y> <размытие> <цвет>;` | `box-shadow: 0 4px 8px rgba(0,0,0,0.2);` |
| [box-sizing](https://htmlbook.ru/css/box-sizing) | Модель расчёта размеров | `box-sizing: <значение>;` | `box-sizing: border-box;` |

### C

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [caption-side](https://htmlbook.ru/css/caption-side) | Положение заголовка таблицы | `caption-side: <значение>;` | `caption-side: bottom;` |
| [clear](https://htmlbook.ru/css/clear) | Запрет обтекания элемента | `clear: <значение>;` | `clear: both;` |
| [color](https://htmlbook.ru/css/color) | Цвет текста | `color: <цвет>;` | `color: #333;` |
| [column-count](https://htmlbook.ru/css/column-count) | Количество колонок текста | `column-count: <число>;` | `column-count: 3;` |
| [column-gap](https://htmlbook.ru/css/column-gap) | Расстояние между колонками | `column-gap: <размер>;` | `column-gap: 20px;` |
| [column-rule](https://htmlbook.ru/css/column-rule) | Линия между колонками | `column-rule: <ширина> <стиль> <цвет>;` | `column-rule: 1px solid #ccc;` |
| [column-span](https://htmlbook.ru/css/column-span) | Объединение колонок | `column-span: <значение>;` | `column-span: all;` |
| [column-width](https://htmlbook.ru/css/column-width) | Ширина колонки | `column-width: <размер>;` | `column-width: 200px;` |
| [columns](https://htmlbook.ru/css/columns) | Колонки (сокращённая запись) | `columns: <ширина> <количество>;` | `columns: 200px 3;` |
| [content](https://htmlbook.ru/css/content) | Содержимое псевдоэлемента | `content: <значение>;` | `content: "→";` |
| [counter-increment](https://htmlbook.ru/css/counter-increment) | Увеличение счётчика | `counter-increment: <имя> <число>;` | `counter-increment: section 1;` |
| [counter-reset](https://htmlbook.ru/css/counter-reset) | Сброс счётчика | `counter-reset: <имя> <число>;` | `counter-reset: section 0;` |
| [cursor](https://htmlbook.ru/css/cursor) | Вид курсора мыши | `cursor: <тип>;` | `cursor: pointer;` |

### D

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [direction](https://htmlbook.ru/css/direction) | Направление текста (слева направо или справа налево) | `direction: <значение>;` | `direction: rtl;` |
| [display](https://htmlbook.ru/css/display) | Тип отображения элемента | `display: <значение>;` | `display: flex;` |

### E

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [empty-cells](https://htmlbook.ru/css/empty-cells) | Отображение пустых ячеек таблицы | `empty-cells: <значение>;` | `empty-cells: hide;` |

### F

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [filter](https://htmlbook.ru/css/filter) | Графические эффекты (размытие, яркость) | `filter: <функция>;` | `filter: blur(5px);` |
| [flex](https://htmlbook.ru/css/flex) | Растяжение, сжатие и база flex-элемента | `flex: <растяжение> <сжатие> <база>;` | `flex: 1 1 200px;` |
| [flex-basis](https://htmlbook.ru/css/flex-basis) | Базовый размер flex-элемента | `flex-basis: <размер>;` | `flex-basis: 200px;` |
| [flex-direction](https://htmlbook.ru/css/flex-direction) | Направление главной оси | `flex-direction: <направление>;` | `flex-direction: column;` |
| [flex-flow](https://htmlbook.ru/css/flex-flow) | Направление и перенос (сокращённая запись) | `flex-flow: <направление> <перенос>;` | `flex-flow: row wrap;` |
| [flex-grow](https://htmlbook.ru/css/flex-grow) | Коэффициент растяжения | `flex-grow: <число>;` | `flex-grow: 2;` |
| [flex-shrink](https://htmlbook.ru/css/flex-shrink) | Коэффициент сжатия | `flex-shrink: <число>;` | `flex-shrink: 0;` |
| [flex-wrap](https://htmlbook.ru/css/flex-wrap) | Перенос flex-элементов | `flex-wrap: <режим>;` | `flex-wrap: wrap;` |
| [float](https://htmlbook.ru/css/float) | Обтекание элемента текстом | `float: <значение>;` | `float: left;` |
| [font](https://htmlbook.ru/css/font) | Шрифт (сокращённая запись) | `font: <стиль> <жирность> <размер>/<высота> <семейство>;` | `font: italic bold 16px/1.5 Arial;` |
| [font-family](https://htmlbook.ru/css/font-family) | Семейство шрифта | `font-family: <шрифт>, <запасной>;` | `font-family: Arial, sans-serif;` |
| [font-size](https://htmlbook.ru/css/font-size) | Размер шрифта | `font-size: <размер>;` | `font-size: 18px;` |
| [font-style](https://htmlbook.ru/css/font-style) | Стиль шрифта (курсив) | `font-style: <стиль>;` | `font-style: italic;` |
| [font-variant](https://htmlbook.ru/css/font-variant) | Вариант шрифта (капитель) | `font-variant: <значение>;` | `font-variant: small-caps;` |
| [font-weight](https://htmlbook.ru/css/font-weight) | Жирность шрифта | `font-weight: <жирность>;` | `font-weight: bold;` |

### G

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [gap](https://htmlbook.ru/css/gap) | Расстояние между элементами | `gap: <размер>;` | `gap: 20px;` |
| [grid](https://htmlbook.ru/css/grid) | Grid-раскладка (сокращённая запись) | `grid: <шаблон>;` | `grid: 100px 1fr / 1fr 1fr;` |
| [grid-area](https://htmlbook.ru/css/grid-area) | Область Grid-элемента | `grid-area: <имя>;` | `grid-area: header;` |
| [grid-column](https://htmlbook.ru/css/grid-column) | Положение по колонкам Grid | `grid-column: <начало> / <конец>;` | `grid-column: 1 / 3;` |
| [grid-row](https://htmlbook.ru/css/grid-row) | Положение по строкам Grid | `grid-row: <начало> / <конец>;` | `grid-row: 2 / 4;` |
| [grid-template-columns](https://htmlbook.ru/css/grid-template-columns) | Шаблон колонок Grid | `grid-template-columns: <размеры>;` | `grid-template-columns: 1fr 1fr 1fr;` |
| [grid-template-rows](https://htmlbook.ru/css/grid-template-rows) | Шаблон строк Grid | `grid-template-rows: <размеры>;` | `grid-template-rows: auto 1fr auto;` |

### H

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [height](https://htmlbook.ru/css/height) | Высота элемента | `height: <размер>;` | `height: 200px;` |

### I

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [isolation](https://htmlbook.ru/css/isolation) | Изоляция контекста наложения | `isolation: <значение>;` | `isolation: isolate;` |

### J

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [justify-content](https://htmlbook.ru/css/justify-content) | Выравнивание по главной оси | `justify-content: <выравнивание>;` | `justify-content: center;` |

### L

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [left](https://htmlbook.ru/css/left) | Смещение от левого края | `left: <размер>;` | `left: 20px;` |
| [letter-spacing](https://htmlbook.ru/css/letter-spacing) | Расстояние между буквами | `letter-spacing: <размер>;` | `letter-spacing: 1px;` |
| [line-height](https://htmlbook.ru/css/line-height) | Межстрочный интервал | `line-height: <значение>;` | `line-height: 1.5;` |
| [list-style](https://htmlbook.ru/css/list-style) | Список (сокращённая запись) | `list-style: <тип> <позиция> <изображение>;` | `list-style: none;` |
| [list-style-image](https://htmlbook.ru/css/list-style-image) | Маркер-изображение списка | `list-style-image: url('<путь>');` | `list-style-image: url('marker.png');` |
| [list-style-position](https://htmlbook.ru/css/list-style-position) | Позиция маркера списка | `list-style-position: <значение>;` | `list-style-position: inside;` |
| [list-style-type](https://htmlbook.ru/css/list-style-type) | Тип маркера списка | `list-style-type: <тип>;` | `list-style-type: square;` |

### M

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [margin](https://htmlbook.ru/css/margin) | Внешний отступ со всех сторон | `margin: <верх> <право> <низ> <лево>;` | `margin: 10px 20px;` |
| [margin-bottom](https://htmlbook.ru/css/margin-bottom) | Внешний отступ снизу | `margin-bottom: <размер>;` | `margin-bottom: 15px;` |
| [margin-left](https://htmlbook.ru/css/margin-left) | Внешний отступ слева | `margin-left: <размер>;` | `margin-left: 20px;` |
| [margin-right](https://htmlbook.ru/css/margin-right) | Внешний отступ справа | `margin-right: <размер>;` | `margin-right: 20px;` |
| [margin-top](https://htmlbook.ru/css/margin-top) | Внешний отступ сверху | `margin-top: <размер>;` | `margin-top: 10px;` |
| [max-height](https://htmlbook.ru/css/max-height) | Максимальная высота | `max-height: <размер>;` | `max-height: 500px;` |
| [max-width](https://htmlbook.ru/css/max-width) | Максимальная ширина | `max-width: <размер>;` | `max-width: 800px;` |
| [min-height](https://htmlbook.ru/css/min-height) | Минимальная высота | `min-height: <размер>;` | `min-height: 100px;` |
| [min-width](https://htmlbook.ru/css/min-width) | Минимальная ширина | `min-width: <размер>;` | `min-width: 200px;` |

### O

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [object-fit](https://htmlbook.ru/css/object-fit) | Масштабирование изображения внутри контейнера | `object-fit: <значение>;` | `object-fit: cover;` |
| [opacity](https://htmlbook.ru/css/opacity) | Прозрачность элемента | `opacity: <число>;` | `opacity: 0.5;` |
| [order](https://htmlbook.ru/css/order) | Порядок элемента во flex-контейнере | `order: <число>;` | `order: 2;` |
| [outline](https://htmlbook.ru/css/outline) | Внешняя рамка (контур) | `outline: <ширина> <стиль> <цвет>;` | `outline: 2px solid red;` |
| [outline-color](https://htmlbook.ru/css/outline-color) | Цвет контура | `outline-color: <цвет>;` | `outline-color: blue;` |
| [outline-offset](https://htmlbook.ru/css/outline-offset) | Смещение контура | `outline-offset: <размер>;` | `outline-offset: 3px;` |
| [outline-style](https://htmlbook.ru/css/outline-style) | Стиль контура | `outline-style: <стиль>;` | `outline-style: dotted;` |
| [outline-width](https://htmlbook.ru/css/outline-width) | Толщина контура | `outline-width: <толщина>;` | `outline-width: 3px;` |
| [overflow](https://htmlbook.ru/css/overflow) | Переполнение содержимого | `overflow: <значение>;` | `overflow: hidden;` |
| [overflow-wrap](https://htmlbook.ru/css/overflow-wrap) | Перенос длинных слов | `overflow-wrap: <значение>;` | `overflow-wrap: break-word;` |
| [overflow-x](https://htmlbook.ru/css/overflow-x) | Переполнение по горизонтали | `overflow-x: <значение>;` | `overflow-x: auto;` |
| [overflow-y](https://htmlbook.ru/css/overflow-y) | Переполнение по вертикали | `overflow-y: <значение>;` | `overflow-y: scroll;` |

### P

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [padding](https://htmlbook.ru/css/padding) | Внутренний отступ со всех сторон | `padding: <верх> <право> <низ> <лево>;` | `padding: 15px;` |
| [padding-bottom](https://htmlbook.ru/css/padding-bottom) | Внутренний отступ снизу | `padding-bottom: <размер>;` | `padding-bottom: 10px;` |
| [padding-left](https://htmlbook.ru/css/padding-left) | Внутренний отступ слева | `padding-left: <размер>;` | `padding-left: 20px;` |
| [padding-right](https://htmlbook.ru/css/padding-right) | Внутренний отступ справа | `padding-right: <размер>;` | `padding-right: 20px;` |
| [padding-top](https://htmlbook.ru/css/padding-top) | Внутренний отступ сверху | `padding-top: <размер>;` | `padding-top: 10px;` |
| [perspective](https://htmlbook.ru/css/perspective) | Перспектива 3D-преобразований | `perspective: <размер>;` | `perspective: 1000px;` |
| [pointer-events](https://htmlbook.ru/css/pointer-events) | Реакция элемента на события мыши | `pointer-events: <значение>;` | `pointer-events: none;` |
| [position](https://htmlbook.ru/css/position) | Способ позиционирования | `position: <значение>;` | `position: relative;` |

### Q

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [quotes](https://htmlbook.ru/css/quotes) | Кавычки для цитат | `quotes: <пары>;` | `quotes: "«" "»";` |

### R

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [right](https://htmlbook.ru/css/right) | Смещение от правого края | `right: <размер>;` | `right: 10px;` |

### S

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [scroll-behavior](https://htmlbook.ru/css/scroll-behavior) | Плавность прокрутки | `scroll-behavior: <значение>;` | `scroll-behavior: smooth;` |

### T

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [table-layout](https://htmlbook.ru/css/table-layout) | Алгоритм раскладки таблицы | `table-layout: <значение>;` | `table-layout: fixed;` |
| [text-align](https://htmlbook.ru/css/text-align) | Выравнивание текста | `text-align: <выравнивание>;` | `text-align: center;` |
| [text-decoration](https://htmlbook.ru/css/text-decoration) | Оформление текста линией | `text-decoration: <линия>;` | `text-decoration: none;` |
| [text-indent](https://htmlbook.ru/css/text-indent) | Отступ первой строки | `text-indent: <размер>;` | `text-indent: 20px;` |
| [text-overflow](https://htmlbook.ru/css/text-overflow) | Переполнение текста | `text-overflow: <значение>;` | `text-overflow: ellipsis;` |
| [text-shadow](https://htmlbook.ru/css/text-shadow) | Тень текста | `text-shadow: <x> <y> <размытие> <цвет>;` | `text-shadow: 2px 2px 4px #000;` |
| [text-transform](https://htmlbook.ru/css/text-transform) | Регистр текста | `text-transform: <регистр>;` | `text-transform: uppercase;` |
| [top](https://htmlbook.ru/css/top) | Смещение от верхнего края | `top: <размер>;` | `top: 0;` |
| [transform](https://htmlbook.ru/css/transform) | Трансформация элемента (поворот, масштаб) | `transform: <функция>;` | `transform: rotate(45deg);` |
| [transition](https://htmlbook.ru/css/transition) | Плавный переход (сокращённая запись) | `transition: <свойство> <длительность> ...;` | `transition: color 0.3s ease;` |
| [transition-delay](https://htmlbook.ru/css/transition-delay) | Задержка перехода | `transition-delay: <время>;` | `transition-delay: 0.2s;` |
| [transition-duration](https://htmlbook.ru/css/transition-duration) | Длительность перехода | `transition-duration: <время>;` | `transition-duration: 0.5s;` |
| [transition-property](https://htmlbook.ru/css/transition-property) | Свойство для перехода | `transition-property: <свойство>;` | `transition-property: all;` |
| [transition-timing-function](https://htmlbook.ru/css/transition-timing-function) | Скорость перехода | `transition-timing-function: <значение>;` | `transition-timing-function: ease-in-out;` |

### U

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [user-select](https://htmlbook.ru/css/user-select) | Выделение текста пользователем | `user-select: <значение>;` | `user-select: none;` |

### V

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [vertical-align](https://htmlbook.ru/css/vertical-align) | Вертикальное выравнивание | `vertical-align: <значение>;` | `vertical-align: middle;` |
| [visibility](https://htmlbook.ru/css/visibility) | Видимость элемента | `visibility: <значение>;` | `visibility: hidden;` |

### W

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [white-space](https://htmlbook.ru/css/white-space) | Обработка пробелов | `white-space: <режим>;` | `white-space: nowrap;` |
| [width](https://htmlbook.ru/css/width) | Ширина элемента | `width: <размер>;` | `width: 100%;` |
| [word-break](https://htmlbook.ru/css/word-break) | Перенос слов | `word-break: <режим>;` | `word-break: break-all;` |
| [word-spacing](https://htmlbook.ru/css/word-spacing) | Расстояние между словами | `word-spacing: <размер>;` | `word-spacing: 5px;` |
| [writing-mode](https://htmlbook.ru/css/writing-mode) | Направление письма | `writing-mode: <значение>;` | `writing-mode: vertical-rl;` |

### Z

| Свойство | Описание | Синтаксис | Пример |
|----------|----------|-----------|--------|
| [z-index](https://htmlbook.ru/css/z-index) | Порядок наложения элементов | `z-index: <число>;` | `z-index: 100;` |

---

## ⚠️ Устаревшие и неиспользуемые свойства

| Свойство | Описание | Статус | Альтернатива |
|----------|----------|--------|--------------|
| [clip](https://htmlbook.ru/css/clip) | Обрезка элемента | ⚠️ Устаревшее | `clip-path` |
| [word-wrap](https://htmlbook.ru/css/word-wrap) | Перенос длинных слов | ⚠️ Устаревшее | `overflow-wrap` |
| `azimuth` | Звуковое позиционирование | ❌ Не используется | Удалено из спецификации |
| `elevation` | Звуковое позиционирование | ❌ Не используется | Удалено из спецификации |
| `pause` | Звуковая пауза | ❌ Не используется | Удалено из спецификации |
| `pitch` | Звуковой тон | ❌ Не используется | Удалено из спецификации |
| `play-during` | Звуковое сопровождение | ❌ Не используется | Удалено из спецификации |
| `speak` | Озвучивание | ❌ Не используется | Удалено из спецификации |
| `volume` | Громкость | ❌ Не используется | Удалено из спецификации |

---

## 📝 @-правила

| @-правило | Описание | Пример | Ссылка |
|-----------|----------|--------|--------|
| [@media](https://htmlbook.ru/css/media) | Медиазапросы для адаптивности | `@media (max-width: 600px) { ... }` | [htmlbook.ru/css/media](https://htmlbook.ru/css/media) |
| [@keyframes](https://htmlbook.ru/css/keyframes) | Определение анимации | `@keyframes slide { from { left: 0; } to { left: 100px; } }` | [htmlbook.ru/css/keyframes](https://htmlbook.ru/css/keyframes) |
| [@font-face](https://htmlbook.ru/css/font-face) | Подключение шрифта | `@font-face { font-family: 'MyFont'; src: url('font.woff2'); }` | [htmlbook.ru/css/font-face](https://htmlbook.ru/css/font-face) |
| [@import](https://htmlbook.ru/css/import) | Импорт другого CSS | `@import url('style.css');` | [htmlbook.ru/css/import](https://htmlbook.ru/css/import) |
| [@supports](https://htmlbook.ru/css/supports) | Проверка поддержки свойства | `@supports (display: grid) { ... }` | [htmlbook.ru/css/supports](https://htmlbook.ru/css/supports) |

---

## 🎭 Псевдоклассы

| Псевдокласс | Описание | Пример |
|-------------|----------|--------|
| [:hover](https://htmlbook.ru/css/hover) | Наведение курсора | `a:hover { color: red; }` |
| [:active](https://htmlbook.ru/css/active) | Нажатие | `button:active { transform: scale(0.98); }` |
| [:focus](https://htmlbook.ru/css/focus) | Фокус (клик или Tab) | `input:focus { border-color: blue; }` |
| [:visited](https://htmlbook.ru/css/visited) | Посещённая ссылка | `a:visited { color: purple; }` |
| [:link](https://htmlbook.ru/css/link) | Непосещённая ссылка | `a:link { color: blue; }` |
| [:first-child](https://htmlbook.ru/css/first-child) | Первый ребёнок | `li:first-child { font-weight: bold; }` |
| [:last-child](https://htmlbook.ru/css/last-child) | Последний ребёнок | `li:last-child { margin-bottom: 0; }` |
| [:nth-child(n)](https://htmlbook.ru/css/nth-child) | n-й ребёнок | `tr:nth-child(even) { background: #f2f2f2; }` |
| [:not(селектор)](https://htmlbook.ru/css/not) | Исключение | `p:not(.special) { color: #333; }` |
| [:checked](https://htmlbook.ru/css/checked) | Отмеченный чекбокс/радио | `input:checked + label { font-weight: bold; }` |
| [:disabled](https://htmlbook.ru/css/disabled) | Отключённый элемент | `input:disabled { opacity: 0.5; }` |

---

## ✨ Псевдоэлементы

| Псевдоэлемент | Описание | Пример |
|---------------|----------|--------|
| [::before](https://htmlbook.ru/css/before) | Вставка до содержимого | `p::before { content: "→ "; }` |
| [::after](https://htmlbook.ru/css/after) | Вставка после содержимого | `p::after { content: " ←"; }` |
| [::first-line](https://htmlbook.ru/css/first-line) | Первая строка | `p::first-line { font-weight: bold; }` |
| [::first-letter](https://htmlbook.ru/css/first-letter) | Первая буква | `p::first-letter { font-size: 2em; }` |
| [::selection](https://htmlbook.ru/css/selection) | Выделенный текст | `::selection { background: yellow; }` |
| [::placeholder](https://htmlbook.ru/css/placeholder) | Плейсхолдер поля ввода | `input::placeholder { color: #999; }` |

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

*Шпаргалка создана на основе справочника CSS от htmlbook.ru. Все названия свойств — это ссылки на соответствующие страницы справочника.*
