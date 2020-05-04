# Skyrim Platform
SkyrimPlatform - это новая система скриптинга для Skyrim Special Edition, позволяющая разрабатывать моды на современном TypeScript (JavaScript) в качестве альтернативы Papyrus.

## Возможности

### Hot Reload
Плагины для SkyrimPlatform могут быть добавлены/изменены/удалены без перезапуска игры, что значительно увеличивает удобство и скорость разработки. Вы буквально можете свернуть игру, внести изменение в скрипт и снова развернуть её.

### Скорость
Код работает значительно быстрее, чем на Papyrus. Вы можете вызывать любые функции каждый игровой кадр. Скорость ограничена лишь производительностью ПК пользователя. Издержки от самого JavaScript-движка снижаются с помощью различных оптимизаций.

### Глобальные скрипты
SkyrimPlatform позволяет создавать глобальные скрипты, не присоединённые к определённому объекту и выполняющиеся непрерывно. В том числе, на во время паузы и в главном меню. Создавать .esp не требуется.

### Совместимость с SKSE
SkyrimPlatform технически является SKSE-плагином, написанным на C++. При написании скриптов можно пользоваться стандартными функциями SKSE и функциями из SKSE-плагинов.

### ES6 Modules
SkyrimPlatform поддерживает импорты/экспорты, благодаря собственному загрузчику модулей.

## Установка и запуск
1. Вам потребуется [Skyrim Special Edition](https://store.steampowered.com/app/489830/The_Elder_Scrolls_V_Skyrim_Special_Edition/).
2. Установите [SKSE](https://skse.silverlock.org/) с официального сайта.
3. Скачайте последнюю версию Skyrim Platform на [странице с релизами.](https://github.com/skyrim-multiplayer/skyrimplatform-builds/releases). 
4. Архив распакуйте в корень игры (каталог, содержащий `SkyrimSE.exe`). Убедитесь, что в одной папке со `SkyrimSE.exe` после распаковки лежит `ChakraCore.dll`.
5. Для начала создания собственных модов на SkyrimPlatform см. инструкции в репозитории **[skyrimplatform-plugin-example](https://github.com/skyrim-multiplayer/skyrimplatform-plugin-example)**.

## Благодарности

 - **Bethesda Softworks** (игры серии TES)
 - **SKSE Team** (SKSE64)
 - **Ryan-rsm-McKenzie** (CommonLibSSE)
