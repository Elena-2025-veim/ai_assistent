```markdown
# ИИ-ассистент для компании по установке окон

Проект представляет собой интеллектуального ассистента, разработанного для автоматизации взаимодействия с клиентами компании, занимающейся установкой окон. Ассистент способен вести осмысленный диалог, отвечать на вопросы клиентов на основе базы знаний, а также записывать клиентов на встречи и добавлять их в Google Календарь .
Ссылка на проект - t.me/oknarodnye_bot



## Содержание

- [Описание](#описание)
- [Функционал](#функционал)
- [Технологии](#технологии)
- [Установка](#установка)
- [Использование](#использование)
- [Документация](#документация)
- [Лицензия](#лицензия)

## Описание

ИИ-ассистент создан для улучшения клиентского опыта и оптимизации рабочих процессов в компании по установке окон. Он помогает клиентам получать точную информацию о продуктах и услугах, а также автоматически планирует встречи, что значительно снижает нагрузку на сотрудников компании .

Основная цель проекта — предоставить клиентам удобный и быстрый способ получения информации и записи на встречи, одновременно упрощая внутренние процессы компании.

## Функционал

### Основные возможности:
- **Осмысленное ведение диалога**: Ассистент может поддерживать естественные и логичные разговоры с клиентами.
- **Ответы на вопросы по базе знаний**: Ассистент использует предварительно загруженную базу знаний для предоставления точных ответов на вопросы клиентов.
- **Запись клиента на встречу**: Ассистент может записывать клиентов на встречи, собирая необходимую информацию (например, дату, время и место).
- **Добавление встречи в Google Календарь**: После записи клиента на встречу ассистент автоматически добавляет её в Google Календарь.

### Планы на будущее:
- Добавить возможность отправки напоминаний о встречах через SMS или электронную почту.
- Интегрировать ассистента с CRM-системой компании для более эффективного управления данными клиентов.

## Технологии

Проект создан с использованием следующих технологий и сервисов:
- **Qwen**: Используется для создания системных промтов и базы знаний, обеспечивающих высокую точность ответов ассистента.
- **Savvy (Suvvy.ai)**: Платформа для создания и настройки ИИ-ассистента, обеспечивающая его интеграцию с различными сервисами .
- **Google Calendar API**: Для автоматического добавления встреч в календарь.
- **Язык программирования**: Python (для написания скриптов интеграции и обработки данных).

## Установка

Чтобы установить и запустить проект, выполните следующие шаги:

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/username/ai-assistant-for-windows-installation.git
   ```

2. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```

3. Настройте переменные окружения:
   Создайте файл `.env` и добавьте следующие параметры:
   ```
   GOOGLE_CALENDAR_API_KEY=ваш_ключ_API
   QWEN_API_KEY=ваш_ключ_API_Qwen
   SAVVY_API_KEY=ваш_ключ_API_Savvy
   ```

4. Запустите проект:
   ```bash
   python app.py
   ```

## Использование

Пример использования ассистента:

1. Клиент обращается к ассистенту с вопросом: "Какие типы окон вы предлагаете?"
2. Ассистент анализирует базу знаний и предоставляет подробный ответ.
3. Клиент запрашивает запись на встречу: "Хочу записаться на замер окон."
4. Ассистент собирает данные (дата, время, адрес) и добавляет встречу в Google Календарь.

Пример кода для демонстрации работы с Google Calendar API:
```python
from google.oauth2 import service_account
from googleapiclient.discovery import build

def add_event_to_calendar(summary, start_time, end_time):
    credentials = service_account.Credentials.from_service_account_file('path_to_credentials.json')
    service = build('calendar', 'v3', credentials=credentials)

    event = {
        'summary': summary,
        'start': {'dateTime': start_time},
        'end': {'dateTime': end_time},
    }

    event = service.events().insert(calendarId='primary', body=event).execute()
    print(f"Event created: {event.get('htmlLink')}")
```

## Документация

Документация проекта доступна в формате Markdown. Подробное описание API и примеры использования можно найти в папке `docs`.

## Лицензия

Этот проект распространяется под лицензией MIT. Подробности можно найти в файле [LICENSE](LICENSE).
```

Это описание проекта в формате Markdown охватывает все ключевые аспекты, включая функционал, технологии, установку и использование. Оно также содержит ссылки на источники и примеры кода для лучшего понимания реализации.
