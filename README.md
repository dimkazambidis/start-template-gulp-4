# Gulp 4 HTML5 шаблон для верстки
Автор: [dimkazambidis](https://github.com/dimkazambidis)
***
>Огромное спасибо [WebDesign Master](http://webdesign-master.ru), именно на базе его шаблона был создан этот!
---
Используется __Gulp v4__  
Сетка основана на __Bootstrap v4__ (настраивается: app/sass/_vars.sass см. "Настройки сетки")  
Используется __jQuery v3.1.1__  
Используемый препроцессор __SASS__

## Исспользуемые пакеты:
- gulp-sass
- browser-sync
- gulp-concat
- gulp-uglify
- gulp-clean-css
- gulp-rename
- del
- gulp-imagemin
- gulp-cache
- gulp-autoprefixer
- gulp-file-include

## Использование:
__Внимание!__ У вас должен быть установлен [Node.js](https://nodejs.org/en/), а затем глобально __gulp__ ( в командной строке - "__npm i gulp -g__")

1. [Скачать](https://github.com/dimkazambidis/start-template-gulp-4/archive/master.zip) и распаковать шаблон

2. Установить требуемые пакеты Node (в папке в командной строке - "__npm i__")

3. Запустиить (в папке в командной строке - "__gulp__")

## Gulp tasks:
__gulp__ ('default') - task для разработки ('__include__', '__sass__', '__js__', '__browser-sync__', '__watch__')  
__build__ - task для сборки в папку dist ('__removedist__', '__imagemin__', '__sass__', '__js__', '__prebuild__')

## Переменные:
Расположение: __app/sass/\_vars.sass__

### Шрифты
__$font-default__ - Шрифт по умолчанию

### Цвет  
__$color-base__ - Основной цвет  
__$color-accent__ - Акцентный цвет  
__$color-placeholder__ - Цвет placeholders  
__$color-success__ - Цвет успешно выполненного действия  
__$color-danger__ - Цвет невыполненного действия (ошибка)  
__$color-text__ - Цвет текста  
__$color-link__ - Цвет ссылок

### Параметры текста
__$fz-base__ - базовый размер шрифта (px)  
__$lh-base__ - базовая высота строки

### Функции
__+fz($fz)__ - выведет __font-size: $fz/$fz-base + rem__, где __$fz__ - размер шрифта в px (переведет размер шрифта из px в rem)  
__+lh($fz, $lh)__ - выведет __line-height: $lh/$fz__, где __$fz__ - размер шрифта в px, __$lh__ - высота строки в px

### Настройки сетки
__$grid-gutter-width__ - расстояние между колонками  
__$grid-columns__ - количество колонок  
__$grid-breakpoints__ - контрольные точки  
__$container-max-widths__ - ширина контейнера

## Media запросы
Расположение: __app/sass/\_media.sass__

## Анимации
Расположение: __app/sass/\_animate.sass__

## Подключение шрифтов
Расположение: __app/sass/\_fonts.sass__

## Стили библиотек
Расположение: __app/sass/\_libs.sass__

## Стили header
Расположение: __app/sass/\_header.sass__

## Стили footer
Расположение: __app/sass/\_footer.sass__

## Стили контента (при желании можно разбить на составляющие)
Расположение: __app/sass/\_layout.sass__

## Основной файл стилей (сброс стилей, базовые стили, сборка в один файл)
Расположение: __app/sass/style.sass__

## Html
Расположение: __app/include__  
__Внимание!__ Верстка производится исключительно в этой папке __app/include__ (не в __app__), иначе при изменении любого файла в app/include в корне файл перезапишется, и отобразятся, только изменения файлов в папке "include"

## Подключаемые части (header, footer, или например карточка товара)
Расположение: __app/include/parts__  
Подключение: в нужном месте __@include('parts/название\_файла.html')__

## Javascript
Расположение: __app/js/common.js__

## Библиотеки и плагины
Расположение: __app/libs__

## Установка:
1. Поместить папку с библиотекой в __app/libs__, или через __bower__ (например, в коммандной строке "__bower i slick-carousel__")

2. Скрипты подключить в __gulpfile.js__ (__task__ - "__js__", в __src__ добавив путь до нужного файла)  
__Внимание!__ Перезапустите Gulp

3. Стили подключить в __app/sass/\_libs.sass__
