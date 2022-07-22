# gulp-replace
Пакет для поиска и замены.

    npm install --save-dev gulp-replace

В файле `gulp/config/plugins.js` записываем:

    import replace from "gulp-replace" // поиск и замена

    // Экспортируем объект с плагинами
    export const plugins = {
        replace: replace
    }

В `gulpfile.js` записываем:

    // Импортируем объект с плагинами
    import { plugins } from "./gulp/config/plugins.js";

    // Передаём значения в глобальную переменную
    global.app = {
        path: path,
        gulp: gulp,
        plugins: plugins,
    }

Теперь можно использовать этот плагин в задаче html.js и других задачах.
