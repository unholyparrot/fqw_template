# TeX выпускной квалификационной работы

Большая благодарность [Amet13](https://github.com/Amet13) за его [репозиторий](https://github.com/Amet13/master-thesis/). Преамбула и часть структуры  были скопированы из его работы и частично дополнены. (автор оригинального репозитория).
Благодарность [unholyparrot](https://github.com/unholyparrot/fqw_template) за предоставленный шаблон.

## Важные ссылки
[Проект на Overleaf](https://www.overleaf.com/3887354913dnpfsrzyqzzs#fecd41)
[Проект на гитхабе](https://github.com/GIS-sys/FQW_bac_mipt)

## Структура шаблона

Сам шаблон находится в _pattern_, включает в себя:

```tree
pattern
 ┣ img
 ┃ ┣ картинка1
 ┃ ┣ картинка2
 ┃ ┗ ...
 ┣ inc
 ┃ ┣ 0-annotation.tex
 ┃ ┣ 0-bibliography.tex
 ┃ ┣ 0-glossary.tex
 ┃ ┣ 0-intro.tex
 ┃ ┣ 1-часть.tex
 ┃ ┣ 2-часть.tex
 ┃ ┣ ...
 ┃ ┣ 99-conclusion.tex
 ┃ ┣ a-app.tex
 ┃ ┗ preamble.tex
 ┣ main.tex
 ┗ references.bib
```

Пример готового файла — _fqw.pdf_

### Создание проекта и выбор компилятора

Скачиваем zip-архив, загружаем в [Overleaf](http://overleaf.com/).

![Загрузка архива и создание проекта](https://github.com/unholyparrot/furry-memory/blob/master/other/upload.png "Загрузка архива и создание проекта")

Сразу появится большое количество ошибок. 

![Ничего не компилируется](https://github.com/unholyparrot/furry-memory/blob/master/other/errors.png "Ничего не компилируется")

Чтобы исправить эту ошибку, меняем тип компилятора с __pdfLaTeX__ на __XeLaTeX__. Это также избавит от ошибок при загрузке работы в личный кабинет. Тип компилятора можно поменять в меню, там же можно включить проверку правописания. 

![Расположение меню](https://github.com/unholyparrot/furry-memory/blob/master/other/comp-type-1.png "Расположение меню")

В меню есть много полезных настроек, советую посмотреть их, но мы здесь пока только за компилятором. 

![Замена компилятора](https://github.com/unholyparrot/furry-memory/blob/master/other/comp-type-2.png "Замена компилятора")

После этого компиляция должна пройти без ошибок. 

### Использование пакетов

Не нужно добавлять пакет __amsmath__, так как он несовместим с используемым __mathtools__.

### Титульная страница

Титульная страница генерируется автоматически при отправке работы в личном кабинете на сайте МФТИ. После отправки работы её достаточно скачать, добавить в папку _inc_ и раскомментить в _main.tex_ строчку

```tex
%%% \includepdf[]{inc/0-titlepage.pdf} % Титульная страница
```

### Ссылки на литературу

Используется BibTeX, стиль __ugost2008l__. В файл _references.bib_ добавляются цитируемые работы. Для этого используем [Академию Google](https://scholar.google.com/), ищем нужную статью. Нажимаем на цитирование.

![Расположение кнопки цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-1.png "Расположение кнопки цитирования")

Далее выбираем цитирование для BibTeX.

![Выбираем способ цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-2.png "Выбираем способ цитирования")

Копируем полученный текст, вставляем в _references.bib_. 

![Образец формата цитирования](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-3.png "Образец формата цитирования")

Если цитируем русскую литературу, то обязательно добавляем к скопированному `language={russian}`, чтобы получить корректный формат цитирования. В итоге должно выглядеть примерно так. 

![Добавлен язык литературы](https://github.com/unholyparrot/furry-memory/blob/master/other/lit-example-4.png "Добавлен язык литературы")
