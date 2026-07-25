# ChromiumFix

Фикс вылетов Google Play Market на Xiaomi.eu HyperOS 2 для Mi 11 Ultra

## Проблема

Google Play падает с ошибкой:
```
[FATAL:udp_socket_posix.cc(315)] Check failed: . : Bad file descriptor (9)
```

Причина — сломанная библиотека libchromium_net.so внутри com.android.tethering.apex

## Решение

Модуль заменяет сломанную библиотеку на рабочую из глобальной прошивки и отключает QUIC.

## Версии

| Версия | QUIC | Автообновление Google Play | Статус |
|--------|------|---------------------------|--------|
| **v2.1 stable** | Выключен | Заблокировано | Рекомендуется |
| v2.2 beta 2 | Включен | Заблокировано | Тестовая |

## Установка

1. Скачай ZIP из Releases
2. Magisk / KernelSU -> Модули -> Установить из хранилища
3. Перезагрузи телефон
4. Проверь лог: su -c "cat /data/local/tmp/ChromiumFix.log"

## Совместимость

- Устройство: Xiaomi Mi 11 Ultra (star)
- Прошивка: Xiaomi.eu HyperOS 2.x
- Android: 14
- Root: Magisk или KernelSU

## Дополнительные модули

| Модуль | Описание |
|--------|----------|
| [BackgroundKiller](https://github.com/arteosab-hub/BackgroundKiller) | Блокировка фоновых процессов |
| [X1Thermal](https://github.com/arteosab-hub/X1Thermal) | Управление частотой Cortex-X1 |

Рекомендуемый набор: BackgroundKiller + X1Thermal + ChromiumFix v2.1

## Автор

Lithium_01

## Лицензия

MIT
