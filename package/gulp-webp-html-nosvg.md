# gulp-webp-html-nosvg
Обработка изображений отличных от SVG.

    npm install --save-dev gulp-webp-html-nosvg

## html.js
После добавления плагина

    // Импортируем пакет gulp-file-include
    import fileInclude from "gulp-file-include";
    // Импортируем пакет gulp-file-include
    import webpHtmlNosvg from "gulp-webp-html-nosvg";

    // Функция обработки HTML файлов
    export const html = () => {
        return app.gulp.src(app.path.src.html)
            .pipe(fileInclude()) // соединяем части html-файла
            .pipe(app.plugins.replace(/@img\//g, 'img/')) // заменяем @img на img/
            .pipe(webpHtmlNosvg())
            .pipe(app.gulp.dest(app.path.build.html));
    }

Код img в файле `dist/index.html`:

        <picture>
            <source srcset="img/file.webp" type="image/webp">
                <img src="img/file.jpg" alt="">
        </picture>
