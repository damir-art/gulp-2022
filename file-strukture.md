# Файловая структура проекта
- создаём `gulpfile.js` - главный файл сценария gulp
- создаём папку с исходными файлами `src`
- создаём папку с вспмогательными файлами для работы с gulp `gulp`
    - `config` - файлы настроек
        - `ftp.js` - настройки для выгрузки результата
        - `path.js` - файл с путями
        - `plugins.js` - информация о плагинах
    - `tasks` - папка с файлами задач
        `copy.js` - тестовая задача

Схема файловой структуры:

    gulp
        config
            ftp.js
            path.js
            plugins.js
        tasks
            copy.js
    src
        files
        index.html
    gulpfile.js
    package.json
