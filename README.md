# Документация проекта "Alt_access_editor"

## Общее описание

Проект "Alt_access_editor" - это веб-приложение для удобного управления и редактирования alt-текстов изображений в HTM/HTML-файлах.

## Структура проекта

Проект состоит из трёх основных файлов:

  * `server.js`: Серверная часть на Node.js, использующая Express.js для обработки HTTP-запросов.
  * `app.js`: Клиентский JavaScript, который обрабатывает взаимодействие с пользователем.
  * `index.html`: Основная веб-страница, через которую пользователь взаимодействует с приложением.

## Запуск проекта

### Установка Node.js

  1. Перейдите на [официальный сайт Node.js](https://nodejs.org/). На главной странице вы увидите две версии для скачивания: LTS (Long Term Support) (версию с длительным периодом поддержки) и Current (текущая версия). Рекомендуется выбрать LTS версию, так как она обеспечивает наилучшую стабильность и поддержку.
  2. Скачайте установщик для вашей операционной системы (Windows, MacOS или Linux) и следуйте инструкциям установщика.
  3. Откройте терминал или командную строку и введите `node -v` для проверки установки. В результате на экране должно появится сообщение с номером установленной версией, это означает, что установка прошла успешно.

### Запуск проекта

  1. Клонируйте репозиторий или скачайте файлы проекта.
  2. Перейдите в каталог проекта при помощи команды `cd [путь к папке проекта]` и выполните команду `npm install`, чтобы установить все необходимые зависимости проекта.
  3. Запустите сервер с помощью команды `node server.js`. В результате вы должны увидеть сообщение в терминале, указывающее, что сервер запущен и слушает на определенном порту (обычно `http://localhost:3000`). Пример сообщения: "Server running on http://localhost:1000"
  4. Откройте `index.html` в вашем браузере: откройте веб-браузер и введите адрес, на котором запущен сервер (например, `http://localhost:3000`). Вы должны увидеть интерфейс приложения.
  5. После завершения работы с приложением для остановки сервера, находясь в папке с проектом, нажмите "ctrl +C".

## Использование

Разместите проект, с которым вы хотите работать, по пути "папка с проектом/public/files". Введите абсолютный путь к папке с Htm/HTML-файлами в поле ввода на веб- странице. Пример абсолютного пути: "C:\Имя пользователя\документы\проекты\название_проекта\файлы\". Нажмите кнопку "Извлечь ALT-тексты". В результате появятся таблицы, соответствующие файлам, находящимся в указанной вами папке. Каждая таблица содержит  название изображения, по нажатию на которое можно просмотреть изобржение, текущее описание изображения, поле ввода для нового описания, а также рекомендации по улучшению. После редактирования файла нажмите кнопку "Сохранить изменения в этом файле", чтобы сохранить внесённые вами изменения. Если в каком либо из файлов нет изображений, вместо таблицы вы увидите соответствующее предупреждение. Обращайте внимание на сообщения об успехе, ошибке или предупреждениях, отображаемых в интерфейсе.

## Функции валидации

* Длина Alt-текста: Проверка длины alt-текста, чтобы она не превышала 255 символов.
* Точка в конце alt-текста: Проверка наличия точки в конце alt-текста.
* Количество Слов: Проверка количества слов в alt-тексте для соответствия рекомендуемому диапазону от 3 до 15 слов.
* Начальные Слова: Alt-текст не должен начинаться со слов "рисунок", "изображение" или "картинка".
* Значки: Проверка на соответствие изображения критериям значков и соответствующее отсутствие alt-текста.
* Дублирование с Подписью: Alt-текст не должен дублировать текст, который уже присутствует в подписи изображения.

## Ошибки и предупреждения

Пользовательский интерфейс обеспечивает отображение информационных сообщений и
предупреждений о валидации, помогая пользователям эффективно редактировать и
обновлять alt-тексты.

## Безопасность и настройки

Приложение включает проверку на то, что указанный путь действительно является папкой. Все операции чтения и записи файлов асинхронны для оптимизации
производительности и предотвращения блокировок.

