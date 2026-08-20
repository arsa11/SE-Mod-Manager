# SE Mod Manager

> **English** | [Русский](#русский)

SE Mod Manager is a desktop mod manager and conflict scanner for **Space Engineers**. It is designed for large mod lists and provides a clearer, faster way to manage world mods than editing configuration files manually.

Select a world, review its installed mods, load Steam Workshop metadata, build reusable collections, change the load order with drag and drop, and save an updated `Sandbox_config.sbc` with an automatic backup.

## Features

- Automatically discovers Space Engineers worlds.
- Reads the mod list from the selected world.
- Separate lists for world mods and available mods.
- Drag and drop mods between lists.
- Reorder the world load order with drag and drop.
- Steam Workshop cards with titles, preview images, and links.
- Detects locally installed or subscribed Workshop mods.
- Imports a mod, collection, or public profile using a Workshop URL or ID.
- Creates, renames, edits, saves, and applies custom mod collections.
- Card and compact list layouts.
- Recent-action history and notifications.
- Saves the world configuration with an automatic backup.
- Scans `.sbc` and `.sbm` files for duplicate `DefinitionId` entries.
- Shows conflict severity, load order, likely override winner, and suggested action.
- English and Russian interface.

## Installation

1. Download the latest `SEModManagerSetup.exe` from **Releases**.
2. Run the installer.
3. Start SE Mod Manager from the Start menu or desktop shortcut.

For the portable version, extract the archive and run `SeModManagerWpf.exe`.

## Quick start

1. Close Space Engineers before changing a world.
2. Select a world from the list on the left.
3. Load Steam cards if titles and previews have not appeared automatically.
4. Drag mods between the available-mod and world-mod lists.
5. Reorder world mods by dragging them up or down.
6. Click **Save world config**.
7. Run the conflict scanner and review any reported overrides.

## Worlds and configuration files

The application searches the standard save directory automatically:

```text
%APPDATA%\SpaceEngineers\Saves
```

If a world is missing, refresh the world list or use **Open config** to select its `Sandbox_config.sbc` manually.

When saving, SE Mod Manager updates the selected world's `Sandbox_config.sbc` and creates a backup first. Keep Space Engineers closed while saving so the game does not overwrite the file.

## Steam Workshop integration

SE Mod Manager can load:

- mod titles and preview images;
- Workshop links;
- local mod paths when available;
- locally installed or subscribed Workshop items;
- mods and collections imported by URL or ID.

Steam does not expose private subscriptions publicly. When possible, the application uses local Steam data instead. Public profile or collection imports depend on the information Steam makes available without signing in.

## Collections

Collections are reusable mod lists stored separately from individual worlds. You can create a collection from the current world, edit its contents, rename it, and apply it to another selected world.

Collections are stored locally in:

```text
%APPDATA%\SEModManagerWpf\profiles
```

## Conflict scanner

The scanner searches mod `.sbc` and `.sbm` files for duplicate `DefinitionId` entries. It shows which mods touch the same definition, their positions in the current load order, and which mod is likely to override the others.

A reported conflict is **not automatically an error**. It may be an intentional compatibility patch, add-on, or rebalance. Treat scanner results as diagnostic hints and test important changes in-game.

See [Conflict Guide](CONFLICTS_GUIDE.md) for a detailed explanation.

## Important notes

- Back up important worlds before changing a large mod list.
- Close Space Engineers before saving world configuration changes.
- A scanner result indicates a possible override, not a guaranteed broken mod.
- Keep compatibility patches after the mods they are intended to patch unless the author specifies otherwise.
- Always follow mod authors' load-order instructions when available.

---

# Русский

SE Mod Manager — настольный менеджер модов и сканер конфликтов для **Space Engineers**. Он рассчитан на большие сборки и позволяет управлять модами мира без ручного редактирования конфигурационных файлов.

Выберите мир, просмотрите установленные моды, загрузите данные из Steam Workshop, создайте собственные коллекции, измените порядок загрузки перетаскиванием и сохраните обновлённый `Sandbox_config.sbc` с автоматической резервной копией.

## Возможности

- Автоматический поиск миров Space Engineers.
- Чтение списка модов выбранного мира.
- Отдельные списки модов мира и доступных модов.
- Перетаскивание модов между списками.
- Изменение порядка загрузки мышкой.
- Карточки Steam Workshop с названием, изображением и ссылкой.
- Поиск локально установленных модов и подписок Workshop.
- Импорт мода, коллекции или публичного профиля по ссылке либо Workshop ID.
- Создание, переименование, редактирование, сохранение и применение коллекций.
- Отображение карточками или компактным списком.
- История последних действий и уведомления.
- Сохранение конфигурации мира с автоматической резервной копией.
- Поиск одинаковых `DefinitionId` в файлах `.sbc` и `.sbm`.
- Отображение серьёзности конфликта, порядка загрузки, вероятного победителя и рекомендации.
- Русский и английский интерфейс.

## Установка

1. Скачайте последнюю версию `SEModManagerSetup.exe` в разделе **Releases**.
2. Запустите установщик.
3. Откройте SE Mod Manager через меню «Пуск» или ярлык на рабочем столе.

Для portable-версии распакуйте архив и запустите `SeModManagerWpf.exe`.

## Быстрый старт

1. Закройте Space Engineers перед изменением мира.
2. Выберите мир в списке слева.
3. Загрузите Steam-карточки, если названия и изображения не появились автоматически.
4. Перетаскивайте моды между списками доступных модов и модов мира.
5. Меняйте порядок загрузки, перетаскивая моды выше или ниже.
6. Нажмите **Сохранить config мира**.
7. Запустите сканер конфликтов и проверьте найденные пересечения.

## Миры и конфигурационные файлы

Приложение автоматически проверяет стандартную папку сохранений:

```text
%APPDATA%\SpaceEngineers\Saves
```

Если нужный мир не появился, обновите список миров или нажмите **Открыть config** и вручную выберите его `Sandbox_config.sbc`.

При сохранении SE Mod Manager обновляет `Sandbox_config.sbc` выбранного мира, предварительно создавая резервную копию. Во время сохранения Space Engineers лучше держать закрытым, чтобы игра не перезаписала файл.

## Интеграция со Steam Workshop

SE Mod Manager может загружать:

- названия и изображения модов;
- ссылки на страницы Workshop;
- локальные пути к модам, если они доступны;
- локально установленные моды и подписки Workshop;
- моды и коллекции, импортированные по ссылке или ID.

Steam не показывает приватные подписки публично. Когда это возможно, приложение использует локальные данные Steam. Импорт публичного профиля или коллекции зависит от данных, которые Steam отдаёт без авторизации.

## Коллекции

Коллекции — это многоразовые наборы модов, которые хранятся отдельно от миров. Можно создать коллекцию из текущего мира, изменить её состав, переименовать и применить к другому выбранному миру.

Коллекции хранятся локально:

```text
%APPDATA%\SEModManagerWpf\profiles
```

## Сканер конфликтов

Сканер ищет одинаковые `DefinitionId` в файлах модов `.sbc` и `.sbm`. Он показывает, какие моды изменяют одно определение, их позиции в текущем порядке загрузки и какой мод, вероятнее всего, перекроет остальные.

Найденный конфликт **не обязательно является ошибкой**. Это может быть намеренный патч совместимости, аддон или ребаланс. Используйте результаты как подсказки для диагностики и проверяйте важные изменения в игре.

Подробности находятся в файле [Руководство по конфликтам](CONFLICTS_GUIDE.md).

## Важно

- Делайте отдельные резервные копии важных миров перед серьёзным изменением сборки.
- Закрывайте Space Engineers перед сохранением конфигурации мира.
- Результат сканирования означает возможное перекрытие, а не гарантированно сломанный мод.
- Обычно патчи совместимости должны находиться после модов, которые они исправляют, если автор не указал иначе.
- При наличии инструкции автора мода всегда ориентируйтесь на неё.

