# Настройка проекта на новом компьютере

## Быстрый старт

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/FUYOH666/spotify-mcp-neuroplaylists.git
   cd spotify-mcp-neuroplaylists
   ```

2. **Создайте файл с секретами:**
   ```bash
   cp .env.example .env
   ```
   
   Затем откройте `.env` и заполните ваши Spotify API credentials:
   ```
   SPOTIFY_CLIENT_ID=your_client_id_here
   SPOTIFY_CLIENT_SECRET=your_client_secret_here
   SPOTIFY_REDIRECT_URI=http://127.0.0.1:8080/callback
   ```

3. **Установите зависимости:**
   ```bash
   uv sync
   ```

4. **Настройте MCP в Cursor:**
   
   Добавьте в `~/.cursor/mcp.json` (или настройки MCP в Cursor):
   ```json
   {
     "mcpServers": {
       "spotify": {
         "command": "uv",
         "args": [
           "--directory",
           "/path/to/spotify-mcp-neuroplaylists",
           "run",
           "spotify-mcp"
         ],
         "env": {
           "SPOTIFY_CLIENT_ID": "your_client_id_here",
           "SPOTIFY_CLIENT_SECRET": "your_client_secret_here",
           "SPOTIFY_REDIRECT_URI": "http://127.0.0.1:8080/callback"
         }
       }
     }
   }
   ```
   
   **Важно:** Замените `/path/to/spotify-mcp-neuroplaylists` на реальный путь к клонированному репозиторию.

5. **Перезапустите Cursor** для применения изменений

6. **При первом использовании** откроется браузер для авторизации Spotify

## Что делает этот проект

Создает 6 нейрофизиологических плейлистов Spotify, оптимизированных под разные когнитивные режимы работы мозга:

- **Кодинг / Глубокая логика** - для PFC-фокуса
- **Админка / Рутина** - для стабильной бодрости
- **Креатив** - для расширения ассоциаций через DMN
- **Остановиться / Снижение перегрева** - для парасимпатической активации
- **Быстрый старт** - для краткого всплеска бодрости
- **Радар / Метапозиция** - для открытого внимания

## Структура файлов

- `.env.example` - шаблон для новых пользователей
- `.env` - локальный файл с секретами (не коммитится, создается из .env.example)
- `secrets.env` - **НЕ ИСПОЛЬЗУЙТЕ** этот файл, он был удален из репозитория по соображениям безопасности

## Требования

- Python 3.12+
- uv (менеджер пакетов)
- Spotify Premium аккаунт
- Cursor IDE или другой MCP-клиент

## Получение Spotify API ключей

1. Зайдите на [developer.spotify.com](https://developer.spotify.com/)
2. Войдите в свой аккаунт Spotify (нужен **Spotify Premium**)
3. Перейдите в [Dashboard](https://developer.spotify.com/dashboard)
4. Нажмите "Create app"
5. Заполните форму:
   - **App name**: любое имя (например, "My AI Playlists")
   - **App description**: описание (опционально)
   - **Redirect URI**: `http://127.0.0.1:8080/callback` (обязательно!)
   - **Website**: можно оставить пустым
6. После создания приложения скопируйте:
   - **Client ID**
   - **Client Secret**
