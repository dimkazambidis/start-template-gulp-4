# Gulp 4 HTML5 шаблон для верстки
Автор: [dimkazambidis](https://github.com/dimkazambidis)
***
>Минификация js и sass, оптимизация изображений, использование webp.
---
Используется __Gulp v4__  
Сетка основана на __Bootstrap v4__ (настраивается: app/sass/_vars.sass см. "Настройки сетки")  
Используется __jQuery v3.1.1__  
Используемый препроцессор __SASS__

## Исспользуемые пакеты:
- browser-sync
- gulp-sass
- gulp-concat
- gulp-uglify
- gulp-babel
- gulp-clean-css
- gulp-rename
- del
- gulp-imagemin
- gulp-webp
- gulp-webp-html
- gulp-cache
- gulp-autoprefixer
- gulp-file-include

## Структура:

###Корень проекта
Здесь находятся все необходимые файлы для управления сборкой
- __gulpfile.js__ - команды и задач Gulp
- __package.json__ - список и настройки пакетов npm
- __.bowerrc__ - настройки менеджера пакетов Bower (подключение библиотек)
- __nodemodules__ - какталог с необходимыми пакетами
- __src__ - каталог с исходным кодом (именно здесь и производится основная работа)
- __dist__ - каталог для выгрузки готовой верстки

## Использование:
__Внимание!__ У вас должен быть установлен [Node.js](https://nodejs.org/en/), а затем глобально __gulp__ ( в командной строке - "__gulp -g__")

__1.__ [Скачать](https://github.com/dimkazambidis/start-template-gulp-4/archive/master.zip) и распаковать шаблон

__2.__ Установить требуемые пакеты Node (в папке в командной строке - "__npm i__")

__3.__ Установить менеджер пакетов Bower для быстрой установки библиотек (__npm install -g bower__). Настройки в файле __.bowerrc__ 

__4.__ Запустиить (в папке в командной строке - "__gulp__")

## Команды и задачи:
Расположение: __gulpfile.js__

### Команды
__gulp__ - запускает команду по умолчанию __'default'__ для разработки (__cleanFunc__, __htmlFunc__, __sassFunc__, __jsFunc__, __imgFunc__, __fontsFunc__, __browserSyncFunc__, __watchFunc__). Сборка происходит в папку dist.

__gulp build__ - запускает команду __'build'__ для сборки в папку dist со сбросом кэша (__clearcacheFunc__, __cleanFunc__, __htmlFunc__, __sassFunc__, __jsFunc__, __imgFunc__, __fontsFunc__)

__gulp clearcache__ - запускает команду __'clearcache'__ для отчистки кэша (__'clearcacheFunc'__). В данный момент кэшируется только минификация изображений.

### Задачи
__browserSyncFunc__ - автоперезагрузка браузера

__jsFunc__ - обрабатывает и собирает файлы javascript по пути __src/js__. (обрабатывает babel пользовательские скрипты, объеденяет со скриптами библиотек, создает полный и минифицированный файлы скриптов __scripts.js__ и __scripts.min.js__) (__jsUseFunc__, __jsLibFunc__)

__sassFunc__ - обрабатывает и собирает файлы sass по пути __src/sass__ (проставляет префиксы, создает полный и минифицированный файлы стилей __style.css__ и __style.min.css__)

__htmlFunc__ - обрабатывает и собирает файлы html (автоматичеси подключает webp формат изображений ([gulp-webp-html](https://www.npmjs.com/package/gulp-webp-html))

__imgFunc__ - обрабатывает файлы изображений (оптимизирует изобрежения, добавляет дубликат в формате webp)

__imgFonts__ - обрабатывает файлы шрифтов

__watchFunc__ - отслеживает изменения

__cleanFunc__ - удаляет директорию __dist__

__clearcacheFunc__ - сбрасывает кэш пакета __'gulp-cache'__

## Переменные:
Расположение: __src/sass/\_vars.sass__

### Шрифты
__$font-default__ - Шрифт по умолчанию (определяется в __src/sass/\_fonts.sass__)

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
Расположение: __src/sass/\_media.sass__

## Анимации
Расположение: __src/sass/\_animate.sass__

## Подключение шрифтов
Расположение: __src/sass/\_fonts.sass__

## Стили библиотек
Расположение: __app/sass/\_libs.sass__

## Стили header
Расположение: __src/sass/\_header.sass__

## Стили footer
Расположение: __src/sass/\_footer.sass__

## Стили контента (при желании можно разбить на составляющие)
Расположение: __src/sass/\_layout.sass__

## Основной файл стилей (сброс стилей, базовые стили, сборка в один файл)
Расположение: __src/sass/style.sass__

## Html
Расположение: __src__

## Подключаемые части html (header, footer, или например карточка товара)
Расположение: __src/parts__  
Подключение: в нужном месте __@include('parts/название\_файла.html')__

## Javascript
Расположение: __src/js/common.js__

## Подключаемые части js
Расположение: __src/js/parts__  
Подключение: в нужном месте __@include('parts/название\_файла.js')__

## Библиотеки и плагины
Расположение: __src/libs__

### Установка:
__1.__ Поместить папку с библиотекой в __app/libs__, или через __bower__ (например, в коммандной строке "__bower i slick-carousel__")

__2.__ Скрипты подключить в __gulpfile.js__ (Задача __jsLibFunc__, в __src__ добавив путь до нужного файла)
```JS
function jsLibFunc() {
	return gulp.src([
		srcFolder + '/libs/jquery/dist/jquery.min.js',
		srcFolder + '/libs/imagesloaded/imagesloaded.pkgd.min.js',
		distFolder + '/js/scripts.js'
	])
	.pipe(concat('scripts.js'))
	.pipe(gulp.dest(path.dist.js))
	.pipe(rename({
		suffix: '.min'
	}))
	.pipe(uglify())
	.pipe(gulp.dest(path.dist.js))
	.pipe(browserSync.stream());
}
```
__Внимание!__ Перезапустите Gulp

__3.__ Стили подключить в __src/sass/\_libs.sass__
