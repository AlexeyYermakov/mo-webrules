# Gulp

---

> Тут галп с [расширенным функционалом](https://github.com/MOgorodnik/mo-gulp). Подробные инструкции там же в разделе wiki.

За основу при написании своего варианта брал эти решения: [CSS-Tricks](https://github.com/zellwk/gulp-starter-csstricks) и [Приятная сборка frontend проекта (github)](https://habrahabr.ru/post/250569/) Доп. ресурсы(ссылки, видео, описания плагинов) [тут](https://github.com/4gekkman/DevKnowBase/blob/master/18.%20gulp/gulp).

**--save-dev**

**devDependencies** — пакеты, которые нужны для разработки. Всякие галпы-гранты и плагины к ним обычно подпадают в эту категорию.
Компиляторы-транспиляторы-трансляторы (типа Coffee, LESS, Jade), тест-раннеры, стайл-чекеры и линтеры (mocha, chai, karma, (js|es)lint, jscs), плагины для таск-раннеров (grunt-contrib-watch, gulp-jade) — все это обычно ставится как --save-dev, потому что нужно только тем, кто контрибьютит в этот проект, работает с его кодом.

**--save**

Библиотеки и фреймворки (expressjs, jquery, backbone), на основе которых работает ваш код, без которых ваш код не запустится у его потребителя — ставятся как **--save**.

**dependencies** — пакеты, от которых ваш пакет зависит непосредственно: как правило — библиотеки.

Ставятся они все в *node_modules.*
Тут подробнее: [https://toster.ru/answer?answer_id=559717#comments...](https://toster.ru/answer?answer_id=559717#comments_list_559717)

Если кто-то делает `npm install` вашему пакету, то npm подсосет те пакеты, которые указаны у него в **dependencies**, но не в **devDependencies**.
Если сделать `npm install` внутри папки, в которой есть package.json, то установятся и те, и другие.