# gulp-file-include
Подключает части html-файлов:

    npm install --save-dev gulp-file-include

Для склейки header.html и index.html внутри index.html прописываем: `@@include("html/header.html", {})`. Передаем параметры при склейке: 

    @@include("html/header.html", {
        "title": "Главная",
    })

В header.html в title указываем `@@title`.

## Задача `html.js`

    // Импортируем пакет gulp-file-include
    import fileInclude from "gulp-file-include";

    // Функция обработки HTML файлов
    export const html = () => {
        return app.gulp.src(app.path.src.html)
            .pipe(fileInclude())
            .pipe(app.gulp.dest(app.path.build.html));
    }

## Решаем проблему с изображениями
Её можно решать или не решать. Просто если не решать то во вложенных HTML-файлах при выборе изображений не будет появляться в редакторе списка изображений в папке. Можно сначала прописать путь до папки, выбрать изображение а потом переписать путь, а можно настроить в VSC пути (сомнительное решение).

Пример проблемы. Создадим файл `src/img/file.jpg`, подключаем его в `index.html`:

    <img src="img/file.jpg" alt="" />

Здесь при компиляции, путь к файлу правильный, но если его прописать например в `html/header.html`, то путь до папки img будет:

    <img src="../img/file.jpg" alt="" />

- устанавливаем плагин VSC `Path Autocomplete`
- f1 `open settings json`
- добавляем найстройки для `Path Autocomplete`

Код:

    "path-autocomplete.pathMappings": {
        "@img": "${folder}/src/img",   // alias for images
        "@scss": "${folder}/src/scss", // alias for scss
        "@js": "${folder}/src/js",     // alias for js
    },

- устанавливаем пакет `gulp-replace`
- преходим в `gulp/config/plugins.js`
