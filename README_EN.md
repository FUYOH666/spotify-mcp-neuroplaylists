# 🎵 Spotify MCP Neuroplaylists

[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Spotify](https://img.shields.io/badge/Spotify-Premium-1DB954.svg)](https://spotify.com)

**MCP server for creating neurophysiological Spotify playlists via AI**

[English](README_EN.md) | [Русский](README.md)

---

## 🌟 About

This project extends [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) capabilities for Spotify API, enabling AI assistants (Claude, ChatGPT, etc.) to create and manage playlists optimized for different cognitive brain states.

**Key feature:** Automatic creation of 6 neurophysiological playlists, each optimized for a specific cognitive work mode.

---

## 🧠 Neurophysiological Playlists

The project creates 6 specialized playlists, each optimized for a specific cognitive state:

### 1. 🧮 Coding / Deep Logic
**Goal:** Activate prefrontal cortex (PFC) for deep concentration  
**Music type:** Instrumental, minimalistic, without distracting vocals  
**Use case:** Programming, solving complex problems, analytical work

### 2. 📋 Admin / Routine
**Goal:** Maintain stable alertness without overstimulation  
**Music type:** Calm background, moderate tempo, neutral mood  
**Use case:** Email processing, documentation, routine tasks

### 3. 🎨 Creativity
**Goal:** Activate Default Mode Network (DMN) for expanded associations  
**Music type:** Diverse, unusual, imagination-stimulating  
**Use case:** Design, writing, brainstorming

### 4. 🛑 Stop / Reduce Overheating
**Goal:** Parasympathetic activation for recovery  
**Music type:** Slow, calming, meditative  
**Use case:** Breaks, recovery after stress, preparing for sleep

### 5. ⚡ Quick Start
**Goal:** Quick burst of alertness and energy  
**Music type:** Energetic, motivating, short tracks  
**Use case:** Morning boost, starting work, overcoming procrastination

### 6. 📡 Radar
**Goal:** Open attention, information scanning  
**Music type:** Atmospheric, non-intrusive, focus-supporting  
**Use case:** Learning new materials, reading, information review

---

## ✨ Features

- 🎵 **Playlist Management** - create, edit, add tracks  
- 🔍 **Music Search** - search tracks, albums, artists, playlists  
- 📊 **Music Information** - detailed info about tracks/albums/artists  
- ⏯️ **Playback Control** - play, pause, skip tracks  
- 📋 **Queue Management** - add tracks to playback queue  
- 🤖 **AI Integration** - work via MCP with Claude, ChatGPT and other assistants

---

## 🚀 Installation

### Requirements

- Python 3.12+
- [uv](https://github.com/astral-sh/uv) (package manager)
- Spotify Premium account
- Cursor IDE or other MCP client

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/FUYOH666/spotify-mcp-neuroplaylists.git
   cd spotify-mcp-neuroplaylists
   ```

2. **Create secrets file:**
   ```bash
   cp .env.example .env
   ```
   
   Fill `.env` with your Spotify API credentials (see [instructions](#getting-spotify-api-keys))

3. **Install dependencies:**
   ```bash
   uv sync
   ```

4. **Configure MCP in Cursor:**
   
   Add to `~/.cursor/mcp.json`:
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

5. **Restart Cursor**

Detailed instructions: [README_SETUP.md](README_SETUP.md) | [SETUP_RU.md](SETUP_RU.md)

---

## 📖 Getting Spotify API Keys

1. Go to [developer.spotify.com](https://developer.spotify.com/)
2. Sign in with your Spotify account (requires **Spotify Premium**)
3. Go to [Dashboard](https://developer.spotify.com/dashboard)
4. Click "Create app"
5. Fill the form:
   - **App name**: any name (e.g., "My AI Playlists")
   - **Redirect URI**: `http://127.0.0.1:8080/callback` (required!)
6. Copy **Client ID** and **Client Secret**

---

## 💡 Benefits of Automation

### For Developers

- ⚡ **Time saving** - no need to manually search and add tracks  
- 🎯 **Precise selection** - AI considers task context and cognitive state  
- 🔄 **Adaptability** - playlists update automatically for current needs  
- 📈 **Productivity** - right music increases work efficiency

### For Researchers

- 🧪 **Experimentation** - testing music's impact on cognitive functions  
- 📊 **Data collection** - automatic logging of playlist usage  
- 🔬 **Reproducibility** - standardized playlists for research

---

## 🛠️ Usage

After setup, you can ask AI to create a playlist:

```
"Create a playlist 'Morning Energy' with energetic tracks for quick start"
"Find lo-fi hip hop tracks and add them to 'Coding' playlist"
"Create a playlist for creative work with unusual tracks"
```

---

## 📚 Documentation

- [README.md](README.md) - Russian version
- [README_SETUP.md](README_SETUP.md) - Setup on new computer
- [SETUP_RU.md](SETUP_RU.md) - Detailed Russian instructions

---

## 🤝 Contributing

PRs welcome! If you have ideas for improving neurophysiological playlists or functionality, create an issue or pull request.

---

## 📄 License

MIT License - see [LICENSE](LICENSE) for details

---

## 🌐 Links

- 🌐 **Website:** [scanovich.ai](https://scanovich.ai)
- 📦 **Repository:** [GitHub](https://github.com/FUYOH666/spotify-mcp-neuroplaylists)
- 📖 **MCP Documentation:** [modelcontextprotocol.io](https://modelcontextprotocol.io/)
- 🎵 **Spotify API:** [developer.spotify.com](https://developer.spotify.com/)

---

## 🙏 Acknowledgments

Based on [spotify-mcp](https://github.com/varunneal/spotify-mcp) project by [@varunneal](https://github.com/varunneal)

---

**Made with ❤️ by [Scanovich.ai](https://scanovich.ai)**
