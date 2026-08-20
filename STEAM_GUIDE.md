# SE Mod Manager — Steam Guide

## English

SE Mod Manager is a desktop mod manager and conflict scanner for **Space Engineers**, built for players whose mod lists have become too large to manage comfortably in the game's standard interface.

It lets you select a world, view its installed mods, load Steam Workshop titles and preview images, build reusable collections, reorder mods with drag and drop, save `Sandbox_config.sbc` with an automatic backup, and find potential definition conflicts.

### Main features

- View all mods used by a selected world.
- Load mod titles, previews, and links from Steam Workshop.
- Detect locally installed or subscribed Workshop mods.
- Import mods and collections using a Workshop URL or ID.
- Add or remove world mods with drag and drop.
- Reorder the world mod list with drag and drop.
- Save `Sandbox_config.sbc` with an automatic backup.
- Create and manage reusable local mod collections.
- Switch between card and compact list layouts.
- Scan `.sbc` and `.sbm` files for duplicate `DefinitionId` entries.
- See the current load order and likely override winner.
- Use the application in English or Russian.

### How to use it

1. Close Space Engineers.
2. Start SE Mod Manager and select your world.
3. Wait for the world mod list to load.
4. Load Steam cards if you want titles and preview images.
5. Drag mods between the available-mod and world-mod lists.
6. Drag world mods up or down to change their order.
7. Click **Save world config**.
8. Use **Collections** to save reusable mod lists.
9. Run the conflict scanner when a large mod list behaves unexpectedly.

### Understanding load order

In many definition conflicts, a mod loaded later can override a mod loaded earlier. In the world-mod list, mods near the bottom are treated as later entries, so compatibility patches and rebalance mods are commonly placed after their base mods.

This is a general rule, not a guarantee for every mod. Always follow the load-order instructions provided by mod authors.

### Understanding conflict results

The scanner searches for duplicate `DefinitionId` entries. If two mods modify the same block, weapon, component, recipe, or other definition, SE Mod Manager shows both mods, their order, and the likely winner.

A reported conflict does **not** mean a mod is definitely broken. Intentional patches and rebalances also override definitions. Use the scanner to locate suspicious overlaps, then verify the result in-game.

### Important

- The application creates a backup before saving the world configuration.
- You should still keep separate backups of important worlds.
- Keep Space Engineers closed while saving changes.
- Private Steam subscriptions cannot normally be read from the public website; the application uses local Steam data when available.
- Test major changes before continuing to play an important world.

### Installation

Download `SEModManagerSetup.exe` from the project's latest GitHub Release and run it. A portable build may also be available; extract it and run `SeModManagerWpf.exe`.

---

## Русский

SE Mod Manager — настольный менеджер модов и сканер конфликтов для **Space Engineers**, созданный для игроков, чьи сборки стали слишком большими для удобного управления через стандартный интерфейс игры.

Он позволяет выбрать мир, посмотреть установленные моды, загрузить названия и изображения из Steam Workshop, создать многоразовые коллекции, изменить порядок модов перетаскиванием, сохранить `Sandbox_config.sbc` с автоматической резервной копией и найти потенциальные конфликты определений.

### Основные возможности

- Просмотр всех модов выбранного мира.
- Загрузка названий, изображений и ссылок из Steam Workshop.
- Поиск локально установленных модов и подписок Workshop.
- Импорт модов и коллекций по ссылке или Workshop ID.
- Добавление и удаление модов перетаскиванием.
- Изменение порядка загрузки мышкой.
- Сохранение `Sandbox_config.sbc` с автоматической резервной копией.
- Создание и управление локальными коллекциями модов.
- Переключение между карточками и компактным списком.
- Поиск одинаковых `DefinitionId` в файлах `.sbc` и `.sbm`.
- Отображение текущего порядка и вероятного победителя при перекрытии.
- Русский и английский интерфейс.

### Как пользоваться

1. Закройте Space Engineers.
2. Запустите SE Mod Manager и выберите мир.
3. Дождитесь загрузки списка модов.
4. Загрузите Steam-карточки, если нужны названия и изображения.
5. Перетаскивайте моды между списками доступных модов и модов мира.
6. Перетаскивайте моды мира выше или ниже, чтобы изменить порядок.
7. Нажмите **Сохранить config мира**.
8. Используйте вкладку **Коллекции**, чтобы хранить разные наборы модов.
9. Запускайте сканер конфликтов, если большая сборка работает странно.

### Как работает порядок загрузки

Во многих конфликтах определений загруженный позже мод может перекрыть загруженный раньше. В списке модов мира нижние позиции считаются более поздними, поэтому патчи совместимости и ребалансы обычно располагают после базовых модов.

Это общее правило, а не гарантия для каждого мода. Всегда следуйте инструкции автора, если он указал необходимый порядок загрузки.

### Как читать результаты конфликтов

Сканер ищет одинаковые `DefinitionId`. Если два мода меняют один блок, оружие, компонент, рецепт или другое определение, SE Mod Manager показывает оба мода, их порядок и вероятного победителя.

Найденный конфликт **не означает**, что мод точно сломан. Намеренные патчи и ребалансы тоже перекрывают определения. Используйте сканер для поиска подозрительных пересечений, а затем проверяйте результат в игре.

### Важно

- Перед сохранением конфигурации приложение создаёт резервную копию.
- Для важных миров всё равно стоит делать отдельные резервные копии.
- Во время сохранения изменений Space Engineers должен быть закрыт.
- Приватные подписки Steam обычно нельзя получить через публичный сайт; при наличии приложение использует локальные данные Steam.
- Проверяйте серьёзные изменения перед продолжением игры в важном мире.

### Установка

Скачайте `SEModManagerSetup.exe` из последнего GitHub Release проекта и запустите его. Также может быть доступна portable-сборка: распакуйте архив и запустите `SeModManagerWpf.exe`.
