# Vue Message Feed

### Описание

**Vue Message Feed** — это приложение на Vue.js, которое отображает ленту сообщений, загружаемую из JSON-файла. Каждое сообщение содержит текст, автора, дату и данные для стилизации текста. Текст в сообщениях раскрашивается в зависимости от тональности, и сообщения подгружаются порциями по 10 штук для удобства просмотра.

### Функционал

- **Загрузка сообщений**: Сообщения загружаются из JSON-файла.
- **Динамическая подгрузка**: При нажатии на кнопку "Загрузить больше" подгружается очередная порция сообщений.
- **Стилизация текста**: Текст раскрашивается согласно тональности в градиенте от красного до зеленого.
- **Отображение даты**: Дата публикации отображается в удобном формате (например, `31 августа 1986`).
- **Ссылки на авторов**: Имена авторов являются ссылками, открывающимися в новой вкладке.

### Технологии

- Vue 3
- Composition API
- JSON для данных
- Webpack для сборки

### Установка и запуск

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/your-username/vue-message-feed.git
   
2. Перейдите в папку проекта:
   ```bash
   cd vue-message-feed
3. Установите зависимости:
   ```bash
   npm install
4. Запустите локальный сервер разработки:
   ```bash
   npm run serve
5. Откройте браузер и перейдите по адресу:
   http://localhost:8080

### Структура проекта

- **src/assets/feed.json** — JSON-файл с сообщениями.
- **src/components/MessageFeed.vue** — Основной компонент для отображения ленты сообщений.
- **public/** — Папка для статических ресурсов.
- **src/App.vue** — Главный компонент приложения.

### JSON Структура

Каждое сообщение в JSON имеет следующую структуру:

```json
{
  "date": "1986-08-31T23:55:22Z",
  "authorName": "Успенский",
  "authorUrl": "https://example.com",
  "content": "Текст сообщения...",
  "contentPostTones": [
    {
      "position": 0,
      "tone": 0.5,
      "length": 5
    }
  ]
}   
```

- **date**: Дата публикации сообщения.
- **authorName**: Имя автора сообщения.
- **authorUrl**: Ссылка на профиль автора.
- **content**: Основной текст сообщения.
- **contentPostTones**: Массив объектов, описывающих участки текста, которые нужно стилизовать. Каждая часть содержит:
  - **position**: Индекс начала стилизации текста.
  - **tone**: Тональность (от -1 до 1), которая влияет на цвет (красный, желтый, зеленый).
  - **length**: Длина участка текста для стилизации.

### Лицензия

Этот проект распространяется под лицензией MIT. Вы можете свободно использовать и модифицировать его для личных или коммерческих целей.

