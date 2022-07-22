# html.js
Задача по обработке HTML-файлов. Копируем код из `copy.js` вставляем в `html.js` изменяем под задачу. Меняем имя функции и пути к файлам.

    // Функция обработки HTML файлов
    export const html = () => {
        return app.gulp.src(app.path.src.html)
            .pipe(app.gulp.dest(app.path.build.html));
    }

## path.js

    build: {
        html:  `${buildFolder}/`, // вставляем html файлы
        files: `${buildFolder}/files/`, // куда копируем файлы и папки
    }, // объект путей к папке с результатом
    src: {
        html:  `${srcFolder}/*.html`, // берем html файлы из корня
        files: `${srcFolder}/files/**/*.*`, // копируем все файлы и папки внутри папки files
    }, // объект путей к исходным файлам
    watch: {
        html:  `${srcFolder}/**/*.html`, // наблюдаем за всемм файлами html
        files: `${srcFolder}/files/**/*.*`,
    }, // объект путей к файлам и папкам за которыми нужно следить

## gulpfile.js

    // Импорт задач
    import { copy } from "./gulp/tasks/copy.js";   // задача копирования файлов
    import { reset } from "./gulp/tasks/reset.js"; // задача удаления папки dist
    import { html } from "./gulp/tasks/html.js";   // задача работы с html файлами

    // Наблюдатель за изменениями файлов
    function watcher() {
        // путь к файлам за которыми нужно следить, действие которое нужно выполнить
        gulp.watch(path.watch.files, copy)
        gulp.watch(path.watch.html, html)
    }

    // Параллельное выполнение задач, после команды gulp
    const mainTasks = gulp.parallel(copy, html)

    // Построение сценариев выполнения задач
    const dev = gulp.series(reset, mainTasks, watcher)

    // Заносим задачу копирования и наблюденяи в "по-умолчанию", gulp в консоли
    gulp.task("default", dev);

В данной инструкции `const mainTasks = gulp.parallel(copy, html)` файлы и из папки `/src/files` и папки `/src/html` будут скопированы в `dist`

## После установки `gulp-replace`

    // Функция обработки HTML файлов
    export const html = () => {
        return app.gulp.src(app.path.src.html)
            .pipe(fileInclude()) // соединяем части html-файла
            .pipe(app.plugins.replace(/@img\//g, 'img/')) // заменяем @img на img/
            .pipe(app.gulp.dest(app.path.build.html));
    }
