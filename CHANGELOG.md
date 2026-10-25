# Delta Player — Changelog / История изменений

All notable changes and release notes for Delta Player.  
Все ключевые изменения и история релизов Delta Player.

[English](#english) · [Русский](#русский)

---

## English

### [0.1.2 (build 1285)] - 2026-10-25
#### Added & Improved
- **Intelligent Decode Planner & CPU Fallback:**
  - Added automatic decode planning (`decode_plan`) detecting GPU hardware decoder capabilities, profiles, and vendor quirks.
  - Graceful fallback to CPU decoding when the hardware decoder does not support a specific codec, profile, or bit depth, preventing playback failure or black screens.
  - Native 4:2:2 and high-bitdepth 4:2:0 processing on GPU: dedicated chroma plane uploading (`yuv420p16`, `yuv422p`, `yuv422p16`) for Direct3D 12 and Vulkan.
  - Vulkan Video 4:4:4 support and extended GPU chroma upsampling shaders.
- **Audio HUD Meter & Track Routing:**
  - Real-time pre-fader HUD audio meter (`ui.output_meter_skin`) showing unattenuated signal level and active channels even when muted or set to low volume.
  - Audio route indicator and active audio stream format details in the HUD.
- **Bidirectional Subtitles (FriBidi):**
  - Bundled `fribidi-0.dll` as a separate delay-loaded DLL under `lib/` for proper RTL text shaping (Arabic, Hebrew) and clean LGPL packaging.
- **Dolby Vision & Interface Polish:**
  - Dolby Vision Profile 7 MEL RPU metadata support and base-layer fallback for FEL frames without brightness jumps or crashes.
  - Improved cursor deadzone filtering against optical sensor micro-drift.

---

### [0.1.2 (build 1252)] - 2026-10-23
#### Added & Improved
- **Playback Speed Configuration:**
  - Added playback speed settings under System (`system.playback_speed` and `system.playback_speed_enabled`).
  - Option to automatically activate your preferred playback speed when opening new files and starting the player.
  - Chosen playback speed adjusted via HUD chip, slider, or context menu is now saved to `config.ini`.

---

### [0.1.2 (build 1239)] - 2026-10-22
#### Added & Improved
- **Context Menu Interpolation:** Added a dedicated **Interpolation** submenu to the right-click menu with direct access to NVIDIA VFG quality presets (High, Medium, Low), RIFE neural models, and MicroRIFE.
- **Independent Interpolation Toggle:** Decoupled the master on/off switch (`video.interpolation_enabled`) from the method selector in settings. Toggling frame generation no longer resets your chosen method or quality preset.
- **Vulkan Backend:** Bundled the optimized standalone `delta-player-vulkan.exe` beside the Direct3D 12 player in the portable release package.
- **HUD Themes Documentation:** Consolidated themes documentation directly inside `HUD/themes.md`.

#### Fixes
- **Mouse Cursor Flickering:** Resolved erratic cursor oscillations / reappearance during playback with an immobile mouse on the desk. Implemented a DPI-adaptive deadzone to filter out optical sensor micro-drift and synthetic OS events during DirectComposition presentation.
- **Notification Spam:** Eliminated redundant toast popups ("Color path" and "Tone mapping") repeatedly appearing during video playback.
- **Portable Runtimes:** Fixed bundling of TensorRT (`tensorrt_rtx`) and NVIDIA Video Effects (`nvidia_vfx_13`) runtimes so neural frame generation works out-of-the-box in portable installations.

---

### [0.1.2 (build 1220)] - 2026-10-21
#### Added & Improved
- **Playback Speed Control:**
  - Dynamic playback speed control with `[` and `]` in 0.1x increments (reset to 1.0x with `Backspace`).
  - Real-time speed indication in the HUD and technical OSD.
  - Audio time-stretching with pitch preservation.
- **Frame Snapshot:** Quick capture of the current video frame directly to the Windows clipboard via `Ctrl+C`.
- **HUD Customization:** Added settings to toggle visibility of individual HUD interface elements.
- **Expanded Sync Offsets:** Removed the ±5-second limit on audio and subtitle sync offsets; timeline HUD chips dynamically adapt to large values.
- **Sync Feedback:** Added OSD notifications when adjusting audio delay ("Audio sync") and subtitle delay ("Subtitle sync").

#### Fixes
- **Audio Desync on Seek:** Fixed external elementary audio track (AC-3, AAC ADTS, MP3, DTS) desynchronization after seeking by flushing demuxer state.
- **Volume HUD Glitch:** Fixed HUD notification remaining stuck at 100% when continuing to scroll up with the mouse wheel.
- **HUD Chip Drawing:** Fixed color/status chips staying visible behind open menus and improved shader efficiency.

---

### [0.1.2 (build 1192)] - 2026-10-20
#### Highlights
- **VRR Frame Pacing:** Accurate presentation timing designed for variable-refresh-rate (G-Sync / FreeSync) displays.
- **Neural Frame Interpolation:** RIFE and lightweight Micro Riffe compute shaders for smooth playback on high-refresh screens.
- **NVIDIA Video Frame Generation (VFG):** Native optical flow interpolation for GeForce RTX 40 / 50 series.
- **Predictive Scene-Cut Detection:** Motion-vector analysis using future frames to avoid blending artifacts across scene cuts.
- **Dolby Vision through HDR10:** Dynamic metadata tonemapping for HDR10 displays (Profile 7 FEL residual bypassed).
- **Dynamic Tone Mapping (DTM):** Real-time adaptation of HDR highlights to display luminance limits.
- **Automatic External Tracks:** Recursive search and pickup of subtitles and audio tracks in subfolders.
- **Spatial & Headphone Audio:** Native Windows Spatial Audio output and Valve Steam Audio binaural HRTF rendering for stereo headphones.
- **Automatic Black-Bar Cropping:** Aspect ratio detection and automatic letterbox cropping for ultrawide displays.
- **Watch History & Marks:** Resumable playback history and scene bookmarking with BC7 DDS keyframe thumbnails.

---

### [0.1.1 (build 1122)] - 2026-10-15
#### Initial Alpha Release
- Initial public alpha release of Delta Player.
- Direct3D 12 rendering engine with FL12_1 / SM6.6 baseline.
- High-precision color management and HDR10 playback pipeline.
- Built-in hardware decoding via D3D12 Video Acceleration.
- Native Win32 / DirectComposition presentation window with GPU-accelerated HUD.

---

## Русский

### [0.1.2 (сборка 1285)] - 25.10.2026
#### Добавлено и улучшено
- **Интеллектуальный планировщик декодирования и авто-фолбек на CPU:**
  - Добавлен автоматический планировщик декодирования (`decode_plan`), определяющий возможности GPU-декодера, поддерживаемые профили и аппаратные особенности.
  - Автоматический переход (fallback) на декодирование силами CPU, если аппаратный декодер видеокарты не поддерживает нужный кодек, профиль или разрядность цвета, исключая ошибки воспроизведения и чёрный экран.
  - Нативная поддержка 4:2:2 и 4:2:0 высокой разрядности на GPU: раздельная загрузка плоскостей цветности (`yuv420p16`, `yuv422p`, `yuv422p16`) в Direct3D 12 и Vulkan.
  - Поддержка Vulkan Video 4:4:4 и улучшенные шейдеры апскейла цветности на GPU.
- **Индикатор аудио и маршрутизация дорожек:**
  - Аудиометр HUD реального времени до регулировки громкости (pre-fader): шкалы отображают исходный уровень дорожки и каналы даже при низкой громкости плеера или включённом Mute.
  - Индикатор маршрута звука и параметры активного аудиопотока в интерфейсе HUD.
- **Субтитры справа налево (FriBidi):**
  - Библиотека `fribidi-0.dll` вынесена в отдельную DLL с отложенной загрузкой в папке `lib/` для корректного формирования двунаправленного текста (RTL-субтитры) и соблюдения лицензии LGPL.
- **Dolby Vision и оптимизации интерфейса:**
  - Поддержка RPU-метаданных Dolby Vision Profile 7 MEL и корректный fallback базового слоя для кадров FEL без скачков яркости.
  - Улучшенная фильтрация микросмещений курсора мыши на столе.

---

### [0.1.2 (сборка 1252)] - 23.10.2026
#### Добавлено и улучшено
- **Настройка скорости воспроизведения:**
  - В раздел «Система» (System) добавлены настройки скорости (`system.playback_speed` и `system.playback_speed_enabled`).
  - Возможность автоматически применять выбранную скорость воспроизведения сразу при открытии новых файлов и запуске плеера.
  - Сохранение установленной скорости в `config.ini` при её изменении через HUD-чип SPEED, ползунок или контекстное меню.

---

### [0.1.2 (сборка 1239)] - 22.10.2026
#### Добавлено и улучшено
- **Контекстное меню интерполяции:** Добавлен пункт **«Интерполяция»** в меню по правому клику с быстрым переключением пресетов NVIDIA VFG (High, Medium, Low), моделей RIFE и MicroRIFE.
- **Независимое включение интерполяции:** Включение/выключение генерации кадров вынесено в отдельный чекбокс (`video.interpolation_enabled`) в настройках и HUD. Переключение методов больше не сбрасывает выбранную модель или пресет качества.
- **Vulkan-бэкенд:** В портативный дистрибутив включён отдельный исполняемый файл `delta-player-vulkan.exe`.
- **Документация тем:** Описание создания тем оформления перенесено напрямую в папку `HUD/themes.md`.

#### Исправления
- **Мерцание курсора мыши:** Устранено самопроизвольное появление и исчезновение курсора мыши при воспроизведении на неподвижной мыши (добавлен DPI-адаптивный порог к микродрифту оптического сенсора при DirectComposition presentation).
- **Спам toast-уведомлений:** Отключены повторяющиеся всплывающие уведомления «Color path» и «Tone mapping» в процессе просмотра.
- **Рантаймы интерполяции:** Исправлена комплектация портативного архива — библиотеки TensorRT (`tensorrt_rtx`) и NVIDIA Video Effects (`nvidia_vfx_13`) теперь упакованы корректно и работают «из коробки».

---

### [0.1.2 (сборка 1220)] - 21.10.2026
#### Добавлено и улучшено
- **Управление скоростью воспроизведения:**
  - Плавная регулировка скорости клавишами `[` и `]` с шагом 0.1x (сброс на 1.0x клавишей `Backspace`).
  - Отображение текущей скорости в HUD и техническом OSD.
  - Качественное растяжение звука во времени с сохранением тональности (Pitch preservation).
- **Снимок кадра:** Быстрое копирование текущего кадра видео в буфер обмена Windows по `Ctrl+C`.
- **Настройка HUD:** Возможность гибко отключать отдельные элементы интерфейса HUD в настройках.
- **Расширенный сдвиг синхронизации:** Снято ограничение ±5 секунд на смещение аудио и субтитров; плашки HUD автоматически адаптируют ширину под большие значения.
- **Обратная связь синхронизации:** Добавлены OSD-уведомления при регулировке задержки дорожек («Audio sync» и «Subtitle sync»).

#### Исправления
- **Рассинхрон аудио при перемотке:** Исправлена потеря синхронизации внешних элементарных аудиодорожек (AC-3, AAC ADTS, MP3, DTS) после перемотки.
- **Индикация громкости:** Устранено залипание HUD-уведомления на 100% при продолжении прокрутки колесом мыши вверх.
- **Отрисовка HUD:** Устранено просвечивание плашек под открытыми окнами настроек и оптимизированы шейдеры интерфейса.

---

### [0.1.2 (сборка 1192)] - 20.10.2026
#### Ключевые возможности
- **VRR-синхронизация:** Вывод кадров под мониторы с переменной частотой обновления (G-Sync / FreeSync).
- **Нейросетевая генерация кадров:** Алгоритмы RIFE и облегчённый шейдер Micro Riffe для повышения плавности видео.
- **NVIDIA Video Frame Generation (VFG):** Аппаратная интерполяция на базе оптического потока для карт GeForce RTX 40 / 50.
- **Упреждающее определение склеек сцен:** Анализ векторов движения будущих кадров для предотвращения артефактов склейки на границах сцен.
- **Dolby Vision через HDR10:** Обработка динамических метаданных RPU для вывода на стандартные HDR10-дисплеи.
- **Динамический тонмаппинг (DTM):** Интеллектуальная адаптация яркости HDR-контента под параметры монитора.
- **Автоподхват внешних дорожек:** Рекурсивный поиск субтитров и звуковых дорожек в подпапках.
- **Пространственный звук:** Вывод через Windows Spatial Audio и бинауральное преобразование для стереонаушников на движке Valve Steam Audio.
- **Автообрезка чёрных полос:** Определение формата кадра и автоматическая обрезка каше под мониторы 21:9 и 32:9.
- **История просмотров и Метки:** Сохранение позиций просмотра и закладки с миниатюрами ключевых кадров в формате BC7 DDS.

---

### [0.1.1 (сборка 1122)] - 15.10.2026
#### Первый публичный альфа-релиз
- Первый публичный выпуск Delta Player.
- Графический движок Direct3D 12 (базовый уровень FL12_1 / SM6.6).
- Высокоточный цветовой конвейер и поддержка воспроизведения HDR10.
- Аппаратное декодирование через D3D12 Video Acceleration.
- Нативный оконный интерфейс Win32 / DirectComposition с ускоренным HUD.
