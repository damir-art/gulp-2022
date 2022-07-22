# del.js
Устанавливаем пакет:

    npm install --save-dev del

Задача для удаления папки `dist`:

    import del from "del"
    export const reset = () => {
        return del(app.path.clean) // путь к "dist"
    }

## gulpfile.js

    // Импорт задач
    import { copy } from "./gulp/tasks/copy.js"; // Импортируем задачу копирования файлов
    import { reset } from "./gulp/tasks/reset.js";

Задача удаления папки `dist` должна выполняться до выполенния всех остальных задач. Задачу `reset` ставим до `copy`:

    // Построение сценариев выполнения задач
    const dev = gulp.series(reset, copy, watcher)