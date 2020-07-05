# TeX шаблон выпускной квалификационной работы

Чтобы потом не искать шаблон для написания ВКР, а также не тратить время на его создание, я решил собрать все по свежей памяти. Большая благодарность [Amet13](https://github.com/Amet13) за его [репозиторий](https://github.com/Amet13/master-thesis/). Преамбула и часть структуры  были скопированы из его работы и частично дополнены. Сборка проекта в Docker-контейнере мне была неудобна, работа полностью оформлена на [Overleaf](http://overleaf.com/), поэтому в шаблон [Amet13](https://github.com/Amet13) были внесены изменения.

## Структура шаблона

Сам шаблон находится в _pattern_, включает в себя:

```tree
pattern
 ┣ img
 ┃ ┣ 01-example-1.png
 ┃ ┣ 01-example-2.png
 ┃ ┗ app-pic.png
 ┣ inc
 ┃ ┣ 0-annotation.tex
 ┃ ┣ 0-bibliography.tex
 ┃ ┣ 0-glossary.tex
 ┃ ┣ 0-intro.tex
 ┃ ┣ 1-lit_review.tex
 ┃ ┣ 2-matherials-and-methods.tex
 ┃ ┣ 3-results.tex
 ┃ ┣ 4-discussion.tex
 ┃ ┣ 99-conclusion.tex
 ┃ ┣ a-app.tex
 ┃ ┗ preamble.tex
 ┣ main.tex
 ┗ references.bib
```

Пример готового файла -- _main.pdf_, постарался включить туда основные используемые функции.

## Держу в курсе

Здесь несколько советов, которые могут облегчить процесс оформления работы. В файлах есть комментарии, но некоторые из них я хочу вынести сюда.

### Создание проекта и выбор компилятора

Скачиваем zip-архив, загружаем в [Overleaf](http://overleaf.com/).

![Загрузка архива и создание проекта](https://github.com/unholyparrot/furry-memory/blob/master/other/upload.png)

Сразу появится большое количество ошибок. 

![Ничего не компилируется](https://github.com/unholyparrot/furry-memory/blob/master/other/errors.png)

Чтобы исправить эту ошибку, меняем тип компилятора с __pdfLaTeX__ на __XeLaTeX__. Это также избавит от ошибок при загрузке работы в личный кабинет.

![Ничего не компилируется](https://github.com/unholyparrot/furry-memory/blob/master/other/errors.png)

Тип компилятора можно поменять в меню, там же можно включить проверку правописания. 

![Расположение меню](https://github.com/unholyparrot/furry-memory/blob/master/other/comp-type-1.png)
![Замена компилятора](https://github.com/unholyparrot/furry-memory/blob/master/other/comp-type-2.png)

После этого компиляция должна пройти без ошибок. Можно удалить лишние файлы и директории из проекта -- _main.pdf_, _README.md_, а также лишние картинки, приложения и директорию _other_. 

### Использование пакетов

Не нужно добавлять пакет __amsmath__, так как он не совместим с используемым __mathtools__.

### Титульная страница

Титульная страница генерируется автоматически при отправке работы в личном кабинете на сайте МФТИ. После отправки работы её достаточно скачать, добавить в папку _inc_ и раскомментить в _main.tex_ строчку

```tex
%%% \includepdf[]{inc/0-titlepage.pdf} % Титульная страница
```

### Ссылки на литературу

Используется BibTeX, стиль __ugost2008l__. В файл _references.bib_ добавляются цитируемые работы. Для этого используем [Академию Google](https://scholar.google.com/), ищем нужную статью. Нажимаем на цитирование.

![Расположение кнопки цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-1.png)

Далее выбираем цитирование для BibTeX.

![Выбираем способ цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-2.png)

Копируем полученный текст, вставляем в _references.bib_. 

![Образец формата цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-3.png)

Если цитируем русскую литературу, то обязательно добавляем к скопированному `language={russian}`, чтобы получить корректный формат цитирования. Итого должно выглядеть примерно так. 

![Добавлен язык литературы](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-4.png)

### Мультикурсор

Для меня было целым открытием, что в [Overleaf](http://overleaf.com/) работает мультикурсор. Для этого нужно зажать `ctrl`, а затем щелкать в нужные места для добавления курсора. Очень удобно при редактировании таблиц и размеров рисунков.
