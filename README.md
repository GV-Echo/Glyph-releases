# Glyph

[Русский](#русский) · [English](#english)

---

## Русский

**Glyph** — лёгкая утилита для строки меню macOS: ресурсы Mac, история буфера обмена,
локальное автодополнение текста в других приложениях, голосовой ввод и системный виджет.

### Скачать

Последняя версия — на странице [Releases](https://github.com/GV-Echo/Glyph-releases/releases/latest),
файл `Glyph-<версия>.dmg`. Нужна macOS 14 Sonoma или новее.

Файл `.aar` рядом нужен для автообновления, скачивать его вручную не надо.

### Установка

1. Откройте dmg и перетащите Glyph в папку «Программы».
2. Glyph не нотаризован Apple, поэтому после скачивания macOS не даст его открыть.
   Разрешите запуск одной командой в Терминале:

   ```bash
   xattr -dr com.apple.quarantine /Applications/Glyph.app && open /Applications/Glyph.app
   ```

   Или: Системные настройки → Конфиденциальность и безопасность → «Открыть всё равно».
3. Glyph живёт в строке меню, значка в Dock у него нет.
4. Для автодополнения нужен доступ: Системные настройки → Конфиденциальность и
   безопасность → Универсальный доступ.

### Возможности

| Раздел | Что есть |
|---|---|
| Строка меню | Иконка Glyph, по выбору температура CPU или живые CPU/RAM в две строки. Если места нет, Glyph возвращается к иконке; повторный запуск из Finder или Spotlight открывает окно |
| Ресурсы | Сводка состояния, CPU с графиком и температурой, температуры датчиков, память (примерно занятая), диск, сеть, батарея |
| Буфер обмена | До 10 последних элементов в памяти: текст, ссылки, файлы, изображения до 30 МБ |
| Автодополнение | Подсказка слова в поле ввода любого приложения: Tab — принять, Esc — скрыть |
| Текст с экрана | Выделите область экрана (`Ctrl+Opt+T`), и её текст попадёт в буфер обмена. Распознавание на устройстве, нужно разрешение «Запись экрана». Картинки из истории буфера распознаются кнопкой в строке, без этого разрешения |
| Транскрибация | Голосовой ввод в любое поле (`Ctrl+Opt+D`): нажать, сказать, нажать ещё раз. Речь распознаёт Whisper прямо на Mac и сам расставляет знаки препинания. Нужен модуль расширения (575 МБ): он скачивается один раз по кнопке во вкладке «Утилиты» и удаляется там же. Нужно разрешение на микрофон |
| Обучение | По желанию: Glyph учится на вашем тексте и на выбранных файлах; можно забыть последние 7 или 30 дней или всё |
| Виджет | Виджет ресурсов для рабочего стола и Центра уведомлений |
| Настройки | Язык RU/EN, тема, режим строки меню, история буфера, глобальные сочетания, запуск при входе |

### Автодополнение

- Работает локально, без сети: словарь частот слов и сочетаний. Встроенные списки слов для
  русского и английского дают подсказки с первого запуска.
- Умные подсказки (по желанию, Mac с процессором Apple): небольшая языковая модель
  Qwen3-0.6B подсказывает слова, которых ещё нет в словаре. Нужен модуль (347 МБ): он
  скачивается один раз во вкладке «Утилиты» и удаляется там же. Ваш словарь главнее.
- Включается в настройках («Дополнять текст в других приложениях») и сочетанием
  `Ctrl+Opt+Space`; нужно разрешение «Универсальный доступ».
- Подсказка рисуется серым текстом у курсора или, если поле не отдаёт положение курсора,
  в небольшой панели рядом с полем.

### Приватность

- История буфера хранится только в памяти, её можно отключить. Пароли из менеджеров
  паролей не попадают в историю. Содержимое буфера не пишется на диск и в логи.
- Обучение выключено по умолчанию. Glyph хранит только счётчики слов и сочетаний, а не
  текст, в зашифрованном файле на вашем Mac.
- Никогда не учится на полях паролей, приложениях из списка «Никогда не учиться» (менеджеры
  паролей по умолчанию) и токенах, похожих на ключи и номера карт.
- Голос, текст и данные никуда не отправляются. Интернет нужен только для загрузки
  модулей транскрибации и умных подсказок, а также для проверки обновлений раз в день.
  Запись голоса при диктовке держится только в оперативной памяти и не пишется на диск.

### Сочетания клавиш

| Сочетание | Действие |
|---|---|
| Клик / правый клик по иконке | Панель / меню: разделы, «О программе Glyph», выход |
| `Cmd+1`, `Cmd+2`, `Cmd+3`, `Cmd+,` | Ресурсы, буфер, утилиты, настройки |
| `Ctrl+Opt+G` | Открыть/закрыть панель на последней вкладке |
| `Ctrl+Opt+V` | Буфер обмена из любого приложения |
| `Ctrl+Opt+Space` | Включить/выключить автодополнение |
| `Ctrl+Opt+T` | Текст с экрана |
| `Ctrl+Opt+D` | Голосовой ввод (когда установлен модуль транскрибации) |
| `Tab`, `Esc` | Принять/скрыть подсказку |

### Обновления

Glyph раз в день проверяет, есть ли новая версия, и предлагает её установить. Обновление
ставится, только если его подпись совпадает с ключом, встроенным в приложение, и новая
сборка подписана тем же сертификатом.

Glyph использует whisper.cpp и MLX Swift (лицензия MIT); полный список — в окне
«О программе Glyph» → «Лицензии».

---

## English

**Glyph** is a lightweight macOS menu-bar utility: Mac resources, clipboard history, local
text autocomplete in other apps, voice input, and a system widget.

### Download

The latest version is on the [Releases](https://github.com/GV-Echo/Glyph-releases/releases/latest)
page, file `Glyph-<version>.dmg`. Requires macOS 14 Sonoma or newer.

The `.aar` file next to it is for automatic updates; you don't need to download it.

### Install

1. Open the dmg and drag Glyph into Applications.
2. Glyph is not notarized by Apple, so macOS blocks it after download. Allow it to run
   with one Terminal command:

   ```bash
   xattr -dr com.apple.quarantine /Applications/Glyph.app && open /Applications/Glyph.app
   ```

   Or: System Settings → Privacy & Security → "Open Anyway".
3. Glyph lives in the menu bar and has no Dock icon.
4. Autocomplete needs access: System Settings → Privacy & Security → Accessibility.

### Features

| Area | Details |
|---|---|
| Menu bar | Glyph icon, optionally CPU temperature or live CPU/RAM on two lines. Without room Glyph falls back to the icon; opening it again from Finder or Spotlight shows the popover |
| Resources | Health summary, CPU with trend and temperature, sensor temperatures, memory (approximate used), disk, network, battery |
| Clipboard | Up to 10 recent items in memory: text, links, files, images up to 30 MB |
| Autocomplete | Word suggestions in any app's text field: Tab accepts, Esc dismisses |
| Text from screen | Select a screen area (`Ctrl+Opt+T`) and its text goes to the clipboard. Recognised on device; needs the Screen Recording permission. Images in clipboard history are recognised from their row, without that permission |
| Transcription | Voice input into any field (`Ctrl+Opt+D`): press, speak, press again. Whisper recognises speech right on the Mac and adds the punctuation itself. Needs an extension module (575 MB), downloaded once from the Tools tab and deleted there too. Needs microphone access |
| Learning | Opt-in: Glyph learns from your writing and from files you choose; forget the last 7 or 30 days, or everything |
| Widget | Resources widget for the desktop and Notification Center |
| Settings | RU/EN language, appearance, menu-bar mode, clipboard history, global shortcuts, open at login |

### Autocomplete

- Local, no network: frequency tables of words and word sequences. Bundled Russian and
  English word lists give suggestions from the first launch.
- Smart suggestions (optional, Apple silicon): a small language model, Qwen3-0.6B,
  suggests words your vocabulary doesn't know yet. Needs a module (347 MB), downloaded
  once from the Tools tab and deleted there too. Your vocabulary comes first.
- Turned on in Settings ("Complete text in other apps") and with `Ctrl+Opt+Space`; needs
  Accessibility access.
- The suggestion is drawn as grey text at the caret, or in a small panel beside the field
  when the field does not report its caret position.

### Privacy

- Clipboard history lives in memory only and can be disabled. Secrets from password
  managers are not recorded. Clipboard contents never reach the disk or the logs.
- Learning is off by default. Glyph stores counts of words and word sequences, not text,
  in an encrypted file on your Mac.
- Never learns from password fields, apps on the "Never learn from" list (password
  managers by default), or tokens that look like keys or card numbers.
- Voice, text and data are never sent anywhere. The internet is used only to download
  the transcription and smart suggestions modules, and to check for updates once a day.
  Dictated voice stays in RAM only and never reaches the disk.

### Shortcuts

| Shortcut | Action |
|---|---|
| Click / right-click the icon | Popover / menu: sections, About Glyph, Quit |
| `Cmd+1`, `Cmd+2`, `Cmd+3`, `Cmd+,` | Resources, Clipboard, Tools, Settings |
| `Ctrl+Opt+G` | Open/close the panel on its last tab |
| `Ctrl+Opt+V` | Clipboard from any app |
| `Ctrl+Opt+Space` | Toggle autocomplete |
| `Ctrl+Opt+T` | Text from screen |
| `Ctrl+Opt+D` | Voice input (with the transcription module installed) |
| `Tab`, `Esc` | Accept / dismiss a suggestion |

### Updates

Once a day Glyph checks for a new version and offers to install it. An update installs
only if its signature matches the key built into the app and the new build is signed with
the same certificate.

Glyph uses whisper.cpp and MLX Swift (MIT licence); the full list is in About Glyph →
Licences.
