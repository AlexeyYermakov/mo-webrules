# CSS

---

**Цель — сохранить единый стиль оформления для всего сайта.**
Если потребуется изменить стиль для динамического содержимого — классы использовать нельзя, переопределять стили нужно только контекстно.
Например, необходимо изменить отступ для параграфа в списке комментариев. Т.к. список комментариев это нумерованный список с классом `"commentlist"` генерируемый WP, то:

    .commentlist p{
         margin: 0 0 4px;
    }

Необходимо изменить стиль списка для виджета:

    div.sidebar .widget ul{
        //some style
    }

Подобным образом поступаем и с остальными элементами.
Также следует принять во внимание ряд базовых CSS классов, которые нужно использовать в подходящих ситуациях

    .aligncenter { text-align: center;}
    img.aligncenter {
       display: block;
       margin: 0 auto;
    }
    .alignleft {float: left;}
    .alignright {float: right;}
    .wp-caption {
        border: 1px solid #ddd;
        text-align: center;
        background-color: #f3f3f3;
        padding: 4px;
    }
    .wp-caption img {
        margin: 0;
        padding: 0;
        border: 0 none;
    }
    .wp-caption p.wp-caption-text {
        padding: 0 4px;
        margin: 0;
    }