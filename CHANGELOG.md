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