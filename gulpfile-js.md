# gulpfile.js

Вид файла при создании первой тестовой задачи копирующей файлы:

    // Импортируем gulp из пакета gulp
    import gulp from "gulp";
    // Импортируем объект с путями из файла
    import { path } from "./gulp/config/path.js";

    // Передаём значения в глобальную переменную
    global.app = {
        path: path,
        gulp: gulp
    }

    // Импортируем задачу копирования файлов
    import { copy } from "./gulp/tasks/copy.js";

    // Заносим задачу копирования в "по-умлочанию"
    gulp.task("default", copy);
