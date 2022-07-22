# package.json
Файл в котором содержатся основные настройки и информация об установленных пакетах.

## Создание файла package.json
- npm init (enter)
- спрашивает название сборки (enter)
- версия сборки (enter)
- описание сборки (enter)
- точка входа (enter)
- тестовая команда (enter)
- гит репозиторий (enter)
- ключевые слова (enter)
- автор (enter)
- лицензия (enter)
- Is this OK? (yes) (enter)

Файл `package.json` создан.

    {
        "name": "gulp2022",
        "version": "1.0.0",
        "description": "",
        "main": "index.js",
        "scripts": {
            "test": "echo \"Error: no test specified\" && exit 1"
        },
        "author": "",
        "license": "ISC"
    }

Этот файл можно редактировать и менять его свойства и значения. Запишем вместо `"main": "index.js",` строку `"main": "gulpfile.js",` и добавим после него `"type": "module",` поддержка модулей ES6.

    {
        "name": "gulp2022",
        "version": "1.0.0",
        "description": "",
        "main": "gulpfile.js",
        "type": "module",
        "scripts": {
            "test": "echo \"Error: no test specified\" && exit 1"
        },
        "author": "",
        "license": "ISC"
    }

## Копируем файлы

    {
        "name": "gulp2022",
        "version": "1.0.0",
        "description": "",
        "main": "gulpfile.js",
        "type": "module",
        "scripts": {
            "test": "echo \"Error: no test specified\" && exit 1"
        },
        "author": "",
        "license": "ISC",
        "devDependencies": {
            "gulp": "^4.0.2"
        }
    }
