# HTML

---
Правила HTML для Opencart в разработке


# CSS

---

**Цель** — как и для WP, сохранить единый стиль оформления для всего сайта.

При заполнении из админки ч-з визуальный редактор нужно понимать, что Opencart преобразует текст в код по своим правилам.

Так например:

* набранный простой текст будет преобразован из `Lorem` - в 
```html
    <p>Lorem</p>
    ```

---
* Отступ между параграфами будет реализован - 
```html
<p><br></p>
```

---
* Выравнивание текста(`left, center, right, justify`) также происходит ч-з инлайновые стили.
```html
<p style="text-align: justify;">Lorem </p>
```

---
* Болдовость, наклон, окрашивание в другой цвет, заливка бэкграунда под текстом будут прописаны инлайново. Текст в виде нижнего/верхнего индекса, зачекивания, перечеркивания, цитаты и т.д.  - обернуты в спец теги html.

** Вид в визуальном редакторе **
<blockquote>
    <p><span style="color: rgb(107, 165, 74);">The main reason of our </span><a href="http://www.google.com" target="_blank">success </a><span style="color: rgb(107, 165, 74);">is that our <span style="font-weight: bold;">commodities</span> <span style="font-style: italic;">are the unique</span> <span style="text-decoration: underline;">combination</span> of <sup> original</sup> <sub>design</sub> and <span style="text-decoration: line-through;">numerous</span> useful options</span><br> <span style="font-weight: bold;">lorem ipsum </span>guote<br></p>
</blockquote>

** Преобразованный текст **
```html
<blockquote>
	<p><span style="color: rgb(107, 165, 74);">The main reason of our </span>
	<a href="http://www.google.com" target="_blank">success </a>
	<span style="color: rgb(107, 165, 74);">is that our <span style="font-weight: bold;">commodities</span> 
	<span style="font-style: italic;">are the unique</span> <span style="text-decoration: underline;">combination</span> of 
	<sup> original</sup> <sub>design</sub> and <span style="text-decoration: line-through;">numerous</span> useful options</span><br> 
	<span style="font-weight: bold;">lorem ipsum </span>guote<br></p>
</blockquote>
```

---
* Неопределенный и нумерованный списки `ul`, `ol`, а также заголовки будут стилизованы в зависимости от примененного **Reset CSS**, поэтому стилизовать такие их нужно глобально т.к. имплиментатор, а уж тем более пользователь добавляя списки ч-з визуальный редактор не должны заботиться о добавлении классов спискам. 

**ИСКЛЮЧЕНИЕ** - ЕСЛИ В ДИЗАЙНЕ НЕСКОЛЬКО ВИДОВ СТИЛИЗАЦИИ.
```css
h1-h6{стили исходя из дизайна для заголовков}
ul{
	стили исходя из дизайна для неопределенного списка
}
ol{
	стили исходя из дизайна для нумерованного списка
}
```

---
* Отдельно стоит отметить, что отступ типа `text-indent` будет реализован при помощи 

```html 
<p style="margin-left: NNpx;">lorem </p>
```

---
* Таблицы. Головная боль))))

Количество строк и ячеек в ней можно выбирать из визуального редактора поэтому ширины ячеек будут пропорциональны размеру таблицы и содержимому внутри ячеек, а поэтому если нужны ячейки определенной ширины то прийдется поиграться с добавлением классов. Еще одним минусом таблиц в Opencart является то, что они адаптированы к мобильным устройствам по методу предлагаемому Bootstrap для респонсив таблиц.(часть таблицы скрывается и доступна только при горизонтальном свайпе, что не всегда удобно)

```html
<table class="table table-bordered">
	<tbody>
		<tr>
			<td>
			...
```

---
* Ссылки добавляются как и во всех подобных визуальных редакторах, достаточно заполнить поля: `текст ссылки` и `url` . 

---
* Видео так же добавляется легко, вставляем `url` и получаем в странице готовый `iframe`.

---
* Картинки через визуальный редактор не вставляются(может в данном шаблоне, на других не проверялось)