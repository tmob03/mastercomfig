---
description: Узнайте, как оптимизировать ОС Windows для повышения производительности.
...

# Windows

## Включение планирования графического процессора с аппаратным ускорением

Новая функция в Windows 10 Май 2020 Update (версия 2004) - аппаратно ускоренное планирование графического процессора, которое позволяет графическому процессору обрабатывать собственное планирование задач вместо Windows,
тем самым уменьшаются задержки и улучшаются исполнения. Вы можете узнать, как включить его с помощью [этого руководства](https://www.neowin.net/news/how-to-enable-hardware-accelerated-gpu-scheduling-on-windows-10-may-2020-update/).

Если вам интересно, что именно делает эта функция, вы можете прочитать этот [технический блог](https://devblogs.microsoft.com/directx/hardware-accelerated-gpu-scheduling/) от корпорации Майкрософт для получения дополнительных сведений.

При возникновении проблем или снижении производительности этой функции выключите ее и [отправьте отзыв](https://aka.ms/submitgameperformancefeedback).

## Отключить режим игры

Игровой режим _может_ снизить производительность и вызвать заикание/зависание. Прочитайте [эту статью Guru3D](https://www.guru3d.com/news-story/windows-10-game-mode-can-impact-fps-negatively-with-stutters-and-freezes.html) для получения дополнительной информации и инструкции о том, как его отключить, если у вас возникли проблемы.

## Отключить полноэкранную оптимизацию

Полноэкранная оптимизация - это функция в Windows 10, где полноэкранные окна вместо этого превращаются в окно без границ низкого уровня, которое достигает почти полноэкранной производительности с быстрой альт-табуляцией оконного режима.

Известно, что Source хуже работает с полноэкранной оптимизацией в некоторых системах, поэтому вы должны отключить его, если у вас возникнут проблемы.

Откройте папку игры через Steam. Затем щелкните правой кнопкой мыши `hl2.exe`,нажмите Свойства, перейдите на вкладку Совместимость, а затем выберите поле, содержащее `Disable Fullscreen Optimizations`.

Дополнительную информацию можно найти в [DirectX Блоге Разработчиков](https://devblogs.microsoft.com/directx/demystifying-full-screen-optimizations/) и в [этом Reddit треде](https://old.reddit.com/r/Windows10/comments/645ukf/windows_10_cu_fullscreen_optimizations/dg330ub/?context=3).

Если отключение полноэкранной оптимизации поможет [сообщите об этом в Майкрософт](https://aka.ms/fullscreenoptimizationsfeedback), чтобы они могли улучшить его в будущем.

!!! совет
    Если используется технология с переменной частотой обновления (VRR), например G-SYNC, отключение полноэкранных оптимизаций может нарушить ее в зависимости от монитора, драйверов и видеокарты. Таким образом, если после этого возникнут проблемы с VRR, попробуйте отменить изменение.

## Используйте высокоэффективный план электропитания

Откройте параметры электропитания и выберите план управления питанием Высокая производительность или план Максимальной производительности, если у вас установлена Windows 10 Pro для рабочих станций. Для пользователей AMD Ryzen Zen 2 и ниже используйте специальный план Ryzen, чтобы правильно использовать преимущества CPPC2. В качестве альтернативы [пользовательская схема питания Ryzen](https://www.techpowerup.com/download/1usmus-custom-power-plan-ryzen-3000-zen-2/) может использоваться для потенциально более высоких тактовых импульсов разгона.

## Отключить Radeon Chill

Radeon Chill это функция энергосбережения, которая вводит переменную карту кадров. Его можно отключить в приложении Настройки Radeon:

1. Перейдите на вкладку Игры.
2. Установите глобальные настройки или только для Team Fortress 2, если вы хотите использовать Chill в другом месте.
3. Выключите Chill.

## Отключить ненужные службы

Можно использовать [инструмент W10Privacy](https://www.winprivacy.de/deutsch-start/download/) уменьшить нагрузку на диск и другие рабочие нагрузки для [повышения производительности](https://www.phoronix.com/scan.php?page=article&item=windows10-w10priv-wsl).

## Оптимизация сети

Используйте [оптимизатор TCP](https://www.speedguide.net/downloads.php) для оптимизации параметров настройки Интернета.

1. Выберите скорость соединения с помощью ползунка вверху.
2. Выберите оптимальную настройку внизу.
3. Нажмите Применить Изменения.

!!! примечание
    Это может не сильно повлиять на TF2, поскольку его оптимизация в основном предназначена для TCP, что происходит только во время соединения,
    с небольшим битом, сделанным для UDP, который используется во время фактического игрового сеанса.

## Отключите Оверлей

Большая идея: отключить как можно больше оверлеев. Они прерывают процесс визуализации своими силами, что может сильно повлиять на производительность во многих случаях. Распространёнными примерами оверлеев являются: Discord и Nahimic.

### Отключите Nahimic

Nahimic это рограммное обеспечение для аудиоэффектов, предварительно установленное на некоторых игровых ноутбуках и настольных компьютерах таких производителей, как Alienware, Dell, MSI и ASUS ROG. Его оверлей особенно неэффективно, что приводит к падению FPS и, как правило, снижению FPS даже при отключении. Это, как известно, трудно удалить, так что вам больше повезет, если отключить драйвер с помощью следующих шагов:

1. Откройте Диспетчер устройств
2. Разверните раздел `Software Components`.
3. Щелкните правой кнопкой мыши и отключите все, что соответствует компоненту `A-Volute Audio Effects`.
4. Открыть службы.
5. Открыть службу Nahimic.
6. Выберите `Startup type:` `Disabled`.

## Автоматическое обновление панели Intel

Функция Intel Panel Self Refresh может сократить время задержки и тайминга кадров, особенно на гибридных ноутбуках (Optimus). Отключите параметры питания в вашем приложении настроек графики Intel.

## Оптимизация задержек драйверов

Плохо запрограммированные драйверы устройств в режиме ядра могут вызывать проблемы с задержкой, что приводит к таким проблемам, как частое заикание. Пользователь должен выяснить, какие именно драйверы вызывают задержку.

[Включение прерываний, сигнализируемых сообщениями (PCIe MSI)](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/) для всех драйверов - отличный способ снизить задержку DPC, вызванную драйверами (ring0). При наличии карты NVIDIA можно использовать [NVCleanstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/) чтобы включить это, с дополнительным преимуществом полной настройки установки драйвера.

Используйте [LatencyMon](https://www.resplendence.com/latencymon) и [DPC Latency Checker](https://www.thesycon.de/eng/latency_check.shtml) для анализа проблем с задержкой, вызванных драйверами устройств в режиме ядра. Если они сообщают о проблемах, попробуйте обновить или установить альтернативные драйверы.
