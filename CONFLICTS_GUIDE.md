# Space Engineers Mod Conflicts

> **English** | [Русский](#конфликты-модов-space-engineers)

This guide explains the **Conflicts** tab in SE Mod Manager and how to interpret scan results.

## What counts as a conflict?

Many Space Engineers objects are described by definitions in `.sbc` files, including blocks, weapons, ammunition, components, recipes, NPC settings, economy settings, and other game data.

Each definition has an identifier commonly represented as:

```text
TypeId / SubtypeId
```

Example:

```text
AmmoMagazine / NATO_25x184mm
```

If multiple mods provide or modify the same definition, the scanner reports a potential conflict. This does not necessarily mean something is broken; it identifies a place where one mod may override another.

## How the likely winner is determined

When multiple mods contain the same `DefinitionId`, the later-loaded definition will often override the earlier one. In the displayed world list:

- a mod placed higher is loaded earlier;
- a mod placed lower is loaded later;
- the lower mod is therefore shown as the likely winner.

This is a useful rule of thumb, not a universal guarantee. Scripts, special loading behavior, dependency rules, and the way a particular definition is merged can affect the actual result. Follow the mod author's instructions when available.

## Scanner columns

- **Severity** — how important the overlap appears to be.
- **Action** — a suggested check or next step.
- **Definition** — the duplicated `DefinitionId`.
- **Mods** — the mods containing that definition.
- **Load order** — their current positions in the world mod list.
- **Likely winner** — the mod most likely to supply the effective definition.

## When a conflict may be intentional

- A compatibility patch intentionally overrides a base mod.
- A rebalance changes weapons, blocks, components, or recipes.
- An add-on adjusts settings from its framework.
- A mod updates or fixes a definition from another mod.
- Several add-ons rely on the same NPC or weapon framework.

## Warning signs

- Unrelated mods accidentally use the same `SubtypeId`.
- A compatibility patch is loaded before the mod it should patch.
- An outdated mod overrides a newer replacement.
- Two mods change the same block in incompatible ways.
- Blocks, weapons, recipes, or NPCs disappear or behave incorrectly after a load-order change.

## Resolving a conflict

### 1. Decide which mod should win

Determine which version of the definition you want:

- frameworks and libraries usually load before their add-ons;
- compatibility patches usually load after all mods they patch;
- rebalance mods usually load after the original content;
- if two independent mods provide the same item, removing one may be safer.

These are general recommendations. A mod author's documented load-order requirement takes priority.

### 2. Change the load order

Drag mods in the world-mod list. A practical starting order for a large mod list is:

1. Libraries and frameworks.
2. Major system mods.
3. Content mods: blocks, weapons, NPCs, and economy.
4. Add-ons for major mods.
5. Compatibility patches.
6. Rebalance or overhaul patches.
7. Personal local fixes.

Then click **Save world config**.

### 3. Scan again and test

Run the scanner again. If the intended mod is now shown as the likely winner, the override may be controlled. Start the world and verify the relevant blocks, recipes, weapons, or NPCs in-game.

### 4. Remove an unnecessary mod

If two independent mods do the same thing and are not designed to work together, changing the order may only hide the problem. Keeping one of them is often the cleaner solution.

## Example

The scanner reports:

```text
AmmoMagazine / NATO_25x184mm
```

Affected mods:

1. `Weapon Pack`
2. `Weapon Pack Rebalance`

If the rebalance is intended to change the ammunition from `Weapon Pack`, it should normally load after the base mod. The order above allows the rebalance definition to take precedence.

## Scanner limitations

The scanner detects potential definition overlaps; it cannot determine every mod author's intention or guarantee that an overlap causes a problem. It helps answer:

- which mods touch the same definition;
- which mod is likely to win with the current order;
- where the order may need attention;
- which mods may be involved in unexpected behavior.

Always back up important worlds and verify changes in-game.

---

# Конфликты модов Space Engineers

Это руководство объясняет вкладку **Конфликты** в SE Mod Manager и помогает правильно читать результаты сканирования.

## Что считается конфликтом

Многие объекты Space Engineers описаны определениями в файлах `.sbc`: блоки, оружие, боеприпасы, компоненты, рецепты, настройки NPC и экономики, а также другие игровые данные.

У каждого определения есть идентификатор, который обычно можно представить так:

```text
TypeId / SubtypeId
```

Пример:

```text
AmmoMagazine / NATO_25x184mm
```

Если несколько модов содержат или изменяют одно определение, сканер сообщает о потенциальном конфликте. Это не обязательно означает поломку — сканер лишь находит место, где один мод может перекрыть другой.

## Как определяется вероятный победитель

Если несколько модов содержат одинаковый `DefinitionId`, определение из загруженного позже мода часто перекрывает более раннее. В отображаемом списке мира:

- мод выше загружается раньше;
- мод ниже загружается позже;
- поэтому нижний мод указывается как вероятный победитель.

Это полезное практическое правило, но не универсальная гарантия. На результат могут влиять скрипты, особенности загрузки, зависимости и способ объединения конкретных определений. Если автор мода указал порядок загрузки, следуйте его инструкции.

## Столбцы сканера

- **Серьёзность** — насколько важным выглядит пересечение.
- **Действие** — рекомендуемая проверка или следующий шаг.
- **Определение** — повторяющийся `DefinitionId`.
- **Моды** — моды, содержащие это определение.
- **Порядок загрузки** — их текущие позиции в списке модов мира.
- **Вероятный победитель** — мод, чьё определение, скорее всего, будет использовано.

## Когда конфликт может быть нормальным

- Патч совместимости намеренно перекрывает базовый мод.
- Ребаланс изменяет оружие, блоки, компоненты или рецепты.
- Аддон меняет настройки своего фреймворка.
- Мод исправляет или обновляет определение другого мода.
- Несколько аддонов используют общий NPC- или weapon-фреймворк.

## Тревожные признаки

- Независимые моды случайно используют одинаковый `SubtypeId`.
- Патч совместимости загружается раньше мода, который должен исправлять.
- Устаревший мод перекрывает новую замену.
- Два мода несовместимым образом изменяют один блок.
- После изменения порядка исчезают или неправильно работают блоки, оружие, рецепты либо NPC.

## Как исправить конфликт

### 1. Решите, какой мод должен победить

Определите, чья версия вам нужна:

- библиотеки и фреймворки обычно загружаются раньше аддонов;
- патчи совместимости обычно загружаются после всех исправляемых модов;
- ребалансы обычно загружаются после оригинального контента;
- если два независимых мода добавляют одно и то же, безопаснее отключить один из них.

Это общие рекомендации. Требование автора мода по порядку загрузки всегда важнее.

### 2. Измените порядок загрузки

Перетащите моды в списке модов мира. В качестве отправной точки для большой сборки можно использовать такой порядок:

1. Библиотеки и фреймворки.
2. Крупные системные моды.
3. Контентные моды: блоки, оружие, NPC и экономика.
4. Аддоны к крупным модам.
5. Патчи совместимости.
6. Ребаланс- и overhaul-патчи.
7. Личные локальные исправления.

Затем нажмите **Сохранить config мира**.

### 3. Повторите сканирование и проверьте игру

Запустите сканер снова. Если нужный мод теперь указан как вероятный победитель, перекрытие можно считать контролируемым. Запустите мир и проверьте соответствующие блоки, рецепты, оружие или NPC в игре.

### 4. Удалите лишний мод

Если два независимых мода делают одно и то же и не рассчитаны на совместную работу, перестановка может только скрыть проблему. Часто надёжнее оставить один из них.

## Пример

Сканер сообщает о пересечении:

```text
AmmoMagazine / NATO_25x184mm
```

Затронутые моды:

1. `Weapon Pack`
2. `Weapon Pack Rebalance`

Если ребаланс должен менять боеприпасы из `Weapon Pack`, обычно его следует загружать после базового мода. При указанном выше порядке определение ребаланса получит приоритет.

## Ограничения сканера

Сканер обнаруживает потенциальные пересечения определений. Он не может определить замысел каждого автора или гарантировать, что пересечение вызывает проблему. Сканер помогает понять:

- какие моды изменяют одно определение;
- какой мод, вероятнее всего, победит при текущем порядке;
- где стоит проверить порядок загрузки;
- какие моды могут быть связаны со странным поведением игры.

Всегда делайте резервные копии важных миров и проверяйте изменения в игре.

