# copy.js
Первая тестовая задача копирующая файлы из папки `src` в папку `dist`.

    // Тестовая функция, копирующая файлы и папки из src в dist
    export const copy = () => {
        // Обращаемся к глобальной переменной app
        return app.gulp.src(app.path.src.files) // получаем доступ к файлам
            .pipe(app.gulp.dest(app.path.build.files)); // копируем файлы
    }
