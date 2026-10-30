# Путеводитель: my-gym-training

Автономная инструкция: достаточно этой папки, исходников и перечисленных защищённых копий. История чатов и центральный каталог не требуются.

[Восстановление](RECOVERY.md) · [Карта файлов и зависимостей](PROJECT_MAP.json)

## Назначение

По [client/README.md](client/README.md): Уведомление для наладчиков по окончанию операции с возможностью печати отчета. - **Журнал испорченного инструмента:** Заполняется наладчиком или инструментальщиком, включает кто испортил, на каком станке, по какой причине.

Обнаруженные языки: JavaScript, PowerShell, Shell, Vue SFC.

## Порядок чтения

1. Локальные AGENTS.md / CLAUDE.md и документы ниже.
2. Манифесты: версии среды, зависимости, команды.
3. Кандидаты точек входа; фактический запуск проверить по манифесту.
4. PROJECT_MAP.json: imports_local от источника к импортируемому файлу; входящие рёбра — потребители модуля.
5. RECOVERY.md: независимые данные, восстановление среды, запуск и критерии приёмки.

- [client/README.md](client/README.md)
- [server/README.md](server/README.md)
- [client/doc/README.md](client/doc/README.md)

## Манифесты

- [client/package.json](client/package.json)
- [server/package.json](server/package.json)

## Кандидаты точек входа

- [client/src/main.js](client/src/main.js)
- [server/src/app.js](server/src/app.js)

## Основные файлы по локальным импортам

| Файл | Входящих импортов |
|---|---:|
| [server/src/config.js](server/src/config.js) | 6 |
| [server/src/db_type.js](server/src/db_type.js) | 6 |
| [client/src/modules/editor-finance/store/workoutStore.js](client/src/modules/editor-finance/store/workoutStore.js) | 2 |
| [client/src/App.vue](client/src/App.vue) | 1 |
| [client/src/router/index.js](client/src/router/index.js) | 1 |
| [client/src/plugins/index.js](client/src/plugins/index.js) | 1 |
| [server/src/routers.js](server/src/routers.js) | 1 |
| [server/src/controllers/workout-sets.controller.js](server/src/controllers/workout-sets.controller.js) | 1 |
| [server/src/controllers/exercise-types.controller.js](server/src/controllers/exercise-types.controller.js) | 1 |
| [server/src/controllers/muscle-groups.controller.js](server/src/controllers/muscle-groups.controller.js) | 1 |
| [server/src/controllers/workout.controller.js](server/src/controllers/workout.controller.js) | 1 |
| [client/src/api/get_nom.js](client/src/api/get_nom.js) | 1 |

## Проверки


## Чтение карты без специальных плагинов

PROJECT_MAP.json — UTF-8 JSON: nodes и edges. Пути файлов относительные. contains обозначает наличие файла; imports_local — статически распознанный импорт; declares_dependency — объявление пакета в манифесте. evidence содержит источник и, где доступно, строку. Карта не исполняет код.

Статус исходного анализа: static-scan-complete; ограничений чтения: 0. Исходный снимок: 2026-10-30T14:47:11.360Z.

После изменения кода перечитайте затронутые файлы: карта является снимком. Отсутствие ребра не доказывает отсутствие зависимости.
