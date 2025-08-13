### Rutube Downloader

---

## 📥 Скачать готовую версию

[![Скачать для Windows](https://img.shields.io/badge/Download-Windows-blue?style=for-the-badge&logo=windows)](https://github.com/RoninOnis/Rutube_download/releases/tag/v1.0.0)

- Работает без установки Python
- Автономное исполнение
- Версия: v1.0 (17.8 МБ)

# Rutube Downloader GUI
![Python](https://img.shields.io/badge/Python-3.6%2B-blue?logo=python)

Графическое приложение для скачивания видео и плейлистов с Rutube с поддержкой выбора качества и других параметров загрузки.

## Особенности
- 🖥️ Интуитивный графический интерфейс (Tkinter)
- ⬇️ Скачивание видео и плейлистов
- 🎚️ Выбор качества видео (от 240p до 4K)
- 🚦 Ограничение скорости загрузки
- 📁 Автоматическое создание папок для плейлистов
- 📝 Настраиваемый формат имен файлов
- 📊 Логгирование процесса в реальном времени
- 🔍 Автоматическая проверка зависимостей

## Требования
- Python 3.6+
- yt-dlp (`pip install yt-dlp`)
- FFmpeg ([инструкции по установке](https://ffmpeg.org/download.html))

## Установка
1. Установите зависимости:
```bash
pip install yt-dlp
```

2. Установите FFmpeg:
- **Windows**: [Скачать](https://www.gyan.dev/ffmpeg/builds/)
- **Linux**: `sudo apt install ffmpeg`
- **MacOS**: `brew install ffmpeg`

## Использование
Запустите приложение:
```bash
python rutube_download.py
```

### Интерфейс

1. Вставьте URL видео/плейлиста
2. Выберите качество видео
3. Установите ограничение скорости (опционально)
4. Выберите папку назначения
5. Задайте формат имени файла
6. Нажмите "Начать скачивание"

## Поддерживаемые ссылки
- Видео: `https://rutube.ru/video/...`
- Плейлисты: `https://rutube.ru/plst/...` или `https://rutube.ru/play/...`

## Особенности работы
- Для плейлистов автоматически создается подпапка
- Поддержка возобновления прерванных загрузок
- Оптимизация видео для веб-воспроизведения
- Подробное логирование процесса
- Проверка наличия зависимостей при запуске

## Решение проблем
Если возникают ошибки:
1. Убедитесь что установлены:
   - yt-dlp (`pip show yt-dlp`)
   - FFmpeg (`ffmpeg -version`)
2. Проверьте интернет-соединение
3. Обновите yt-dlp: `pip install --upgrade yt-dlp`
4. Для проблем с кодировкой добавьте в начало файла:
```python
# -*- coding: utf-8 -*-
```


## Terminal версия

Самая простая версия для скачивания видео

Переменные:
-f "best[height<=1080]" качество видео
-f "best[filesize<100M]" размер скачиваемого видео
--limit-rate 5M ограничение скорости скачивания

Убедитесь что установлен:
   - yt-dlp (`pip show yt-dlp`)

Заменить https://rutube.ru/*******/ на нужное
```python
yt-dlp --merge-output-format mp4 "https://rutube.ru/*******/" -o "C:/Path/to/folder/output/%(title)s.%(ext)s"
```

С указанием качества 1080/720/480/360
```python
yt-dlp -f "best[height<=1080]" --merge-output-format mp4 "https://rutube.ru/*******/" -o "C:/Path/to/folder/output/%(title)s.%(ext)s"
```


С указанием размера файла 100М и ограничение скорости в 5М(не рекомендуется иначе будет каша из разного качества видео ИМХО)
```python
yt-dlp -f "best[filesize<100M]" --merge-output-format mp4 "https://rutube.ru/*******/" --limit-rate 5M -o "C:/Path/to/folder/output/%(title)s.%(ext)s"
```



