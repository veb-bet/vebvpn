# veb-vpn

Минималистичное десктоп-приложение для подключения к VPN по ключам Shadowsocks, Trojan, VLESS.

## Возможности

- Поддержка протоколов: Shadowsocks, Trojan, VLESS (по ссылкам-ключам)
- Светлая и тёмная тема, фиолетовый акцент, минималистичный интерфейс
- Отображение статуса подключения, скорости, ошибок
- Сохранение последнего использованного ключа и автоматический запуск с ним
- Логирование всех действий в файл `vebforvpn.log`
- Автоматический выбор подходящего исполняемого файла xray для вашей платформы

## Требования

- Python 3.8+
- PyQt6 (`pip install PyQt6`)
- Исполняемый файл xray-core для вашей платформы (см. ниже)
- Ключи VPN (Shadowsocks, Trojan, VLESS)

## Установка

1. **Скачайте xray-core**  
   Скачайте архив с [официального репозитория xray-core](https://github.com/XTLS/Xray-core/releases) для вашей платформы.  
   Распакуйте его в папку рядом с программой, например:
   - `xray-linux-amd64/xray`
   - `xray-windows-amd64/xray.exe`

2. **Установите зависимости**
   ```bash
   pip install PyQt6
   ```

3. **Запустите приложение**
   ```bash
   python3 main.py
   ```

## Использование

1. Вставьте ваш VPN-ключ (Shadowsocks, Trojan, VLESS) в поле ввода.
2. Нажмите "Подключиться".
3. Статус, скорость и ошибки будут отображаться в окне.
4. Для смены темы используйте выпадающий список "Тема".
5. Для отключения нажмите "Отключить".

## Структура проекта

```
vebforvpn/
├── main.py
├── ui.py
├── vpn.py
├── parser.py
├── state.py
├── theme.py
├── README.md
├── vebforvpn.log
├── xray-linux-amd64/
│   └── xray
├── xray-windows-amd64/
│   └── xray.exe
└── ...
```

## Логирование

Все действия и ошибки пишутся в файл `vebforvpn.log` в корне проекта.

## Примечания

- Для работы VPN требуется наличие прав на запуск xray.
- Если приложение пишет "Не найден исполняемый файл 'xray'", убедитесь, что нужный файл xray лежит в соответствующей папке и имеет права на запуск.
- Скорость подключения отображается приблизительно (по логам xray или сетевой статистике).
