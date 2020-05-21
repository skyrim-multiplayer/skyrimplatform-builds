# История изменений

 - **0.1.0** - первая публичная альфа-версия.
 - **0.1.1** - hotfix функций getPositionX, getPositionY, getPositionZ, возвращавших неправильные значения.
 - **0.1.2** - исправлено: вызов многих нативных функций приводил к крашу игры или неправильному результату.



# 0.2.0

## Добавлено
- Полная поддержка асинхронных функций игры (Latent Functions):
```typescript
await Game.getPlayer().setPosition(0,0,0);
await Utility.wait(1);
await Utility.waitMenuMode(1);
```
Обновите также `skyrimplatform-plugin-example`, чтобы получить новый `skyrimPlatform.ts`.
- Вывод ошибки в консоль при Unhandled promise rejection (ранее такие ситуации игнорировались)

## Исправлено
- Строки не работали в качестве параметров и возвращаемых значений. Теперь такие вещи работают как надо:
```typescript
let base = Game.getPlayer().getBaseObject();
base.setName('Todd');
printConsole(base.getName()); // 'Todd'
```
- Вызов `Debug.sendAnimationEvent` приводил к вылету игры.
- Динамическое приведение типов не поддерживало приведение от потомка к родителю:

```typescript
printConsole(ObjectReference.from(Game.getPlayer()));
// До: null
// После: [object ObjectReference]
```

# 0.3.0

## Добавлено
 - Papyrus-класс `WorldSpace` теперь доступен в SkyrimPlatform
 - Добавлен Papyrus-класс `TESModPlatform` и функция `moveRefrToPosition`, позволяющая телепортировать ссылку в любую ячейку/мир на любые координаты

## Исправлено
 - latent-функции с аргументами типа Int не работали (напр. `setMotionType`)
 - Динамическое приведение типов не работало в некоторых специфичных случаях (напр. `ObjectReference.from(Game.getForm(0x14))`)

# 0.3.1

## Исправлено
 - Функции из SKSE-плагинов не вызывались.
 - `Debug.sendAnimationEvent`/`Debug.notification` не работали в локациях, которые не является городом или поселением.

# 0.4.0

## Добавлено
 - DumpFunctions теперь выводит оффсеты функций вместо адресов.
 - Хук `sendAnimationEvent`.
 - Документация по реализованному на текущий момент функционалу.

## Исправлено
 - Краш при использовании DumpFunctions в Debug-конфигурации.
 - Внутренний цикл событий игры был перегружен.
 - Ошибка генерации CMake, связанная с кэшированием.

# 0.5.0

## Добавлено
 - Компилятор Papyrus интегрирован с нашей сборочной системой.
 - Papyrus-классы `Action`, `Activator`, `ActiveMagicEffect`, `Key`, `VoiceType`, `LocationRefType`, `EncounterZone`, `ImpactDataSet`, `AssociationType`, `Idle`, `Class`, `Projectile`, `MiscObject`, `Apparatus`, `AssociationType`, `ConstructibleObject`, `Container`, `DefaultObjectManager`, `Door`, `EncounterZone`, `Explosion`, `Furniture`, `WordOfPower`, `Hazard`, `LeveledSpell`, `Static`, `SoundCategory`, `TalkingActivator`, `TreeObject` теперь доступны в SkyrimPlatform.
 - Добавлен enum `MotionType` для `ObjectReference.setMotionType`.
 - Добавлен метод `once`, аналогичный методу из модуля events в NodeJS.

# 0.6.0

## Добавлено
 - Функция `setWeaponDrawnMode` в Papyrus-класс `TESModPlatform`
 - Функция `getNthVtableElement` в Papyrus-класс `TESModPlatform`

## Удалено
 - Незадокументированная функция `writeScript`
