# path.js

    // Получаем имя папки проекта
    import * as nodePath from 'path'
    const rootFolder = nodePath.basename(nodePath.resolve())

    const buildFolder = `./dist` // путь к папке с обработанными файлами, также можно использовать rootFolder
    const srcFolder   = `./src`  // путь к папке с исходными файлами

    // Объект хранящий пути
    const path = {
        build: {}, // объект путей к папке с результатом
        src: {}, // объект путей к исходным файлам
        watch: {}, // объект путей к файлам и папкам за которыми нужно следить
        clean: buildFolder,
        buildFolder: buildFolder,
        srcFolder: srcFolder,
        rootFolder: rootFolder,
        ftp: ``,
    }

## Копируем файлы

    // Получаем имя папки проекта
    import * as nodePath from 'path';
    const rootFolder = nodePath.basename(nodePath.resolve());

    const buildFolder = `./dist`; // путь к папке с обработанными файлами, также можно использовать rootFolder
    const srcFolder   = `./src`;  // путь к папке с исходными файлами

    // Объект хранящий пути, экспортируем чтобы иметь возможность использовать его в других файлах
    export const path = {
        build: {
            files: `${buildFolder}/files/`, // куда копируем файлы и папки
        }, // объект путей к папке с результатом
        src: {
            files: `${srcFolder}/files/**/*.*`, // копируем все файлы и папки внутри папки files
        }, // объект путей к исходным файлам
        watch: {}, // объект путей к файлам и папкам за которыми нужно следить
        clean: buildFolder,
        buildFolder: buildFolder,
        srcFolder: srcFolder,
        rootFolder: rootFolder,
        ftp: ``,
    }
