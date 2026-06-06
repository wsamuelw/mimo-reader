# MiMo TTS Reader — Free Open Source AI Text-to-Speech Tool

An open source, browser-based AI voice generator and text-to-speech tool. Create custom voices, clone any voice, and export audio as WAV or MP3 — no installation required.

**[Live Demo →](https://wsamuelw.github.io/mimo-reader/)**
**[GitHub →](https://github.com/wsamuelw/mimo-reader)**

## Highlights

- **Free & Open Source** — MIT licensed, no subscription required
- **No Install** — runs entirely in your browser
- **100+ Voices** — across 6 categories
- **Voice Cloning** — clone any voice from a short audio sample
- **WAV/MP3 Export** — download for any project

https://github.com/user-attachments/assets/5bd1c4ec-60b7-4899-a73b-d29ac71049c5

*Demo of voice design, cloning, and playback in the browser.*

## Why This Tool?

- **No server-side processing** — text and audio are sent directly from your browser to the MiMo TTS API
- **Single-file app** — the entire app is one `index.html` file, no build step needed
- **Custom voices** — fine-tune any voice with editable descriptions
- **Fast generation** — voice design in 2-5 seconds, voice clone in 10-60 seconds

## Use Cases

- **Podcast Production** — Generate voiceovers for intros, outros, and ad reads. Choose from 100 voices or clone your own.
- **Marketing Content** — Create voiceovers for social media videos, ads, and presentations. Match your brand voice with custom descriptions.
- **Accessibility** — Listen to any text read aloud. Useful for dyslexia, visual impairments, or audio-first learning.
- **E-Learning** — Narrate training materials, courses, and tutorials with consistent, professional voices.
- **Content Localization** — Generate voiceovers in any accent or tone for international audiences.

## Features

- **100 preset voices** across 6 categories (Conversational, Professional, Expressive, Youthful, Character, Accent)
- **Voice cloning** from audio file or microphone recording
- **Voice design** with editable descriptions for fine-tuned control
- **Random voice generator** — generate wildcard descriptions for exploration
- **Voice preview** — play a sample for any voice before generating
- **Pending audio system** — generate new audio while listening; press play to switch
- **Time estimates** — range-based estimates for clone and design modes
- **Dark/light theme** — with system preference detection
- **Download as WAV or MP3** — for any project
- **Responsive design** — works on desktop and mobile
- **Keyboard shortcuts** — `⌘+Enter` to generate

## Getting Started

### Quick Start

1. **Get an API key** from [MiMo TTS](https://platform.xiaomimimo.com/docs/en-US/welcome) — free tier available with 50 credits
2. **Open the app** at [wsamuelw.github.io/mimo-reader](https://wsamuelw.github.io/mimo-reader/)
3. **Add your API key** in Settings (top-right corner)
4. **Enter text**, pick a voice, and hit Generate

### Voice Design

1. Select **Voice Design** mode
2. Choose a voice from the list (or use the search/filter)
3. Type or paste your text
4. Click **Generate** or press `⌘+Enter`
5. Download as WAV or MP3

### Voice Clone

1. Select **Voice Clone** mode
2. Upload an audio file or record directly
3. Type or paste your text
4. Click **Generate**
5. Download the cloned voice output

### Voice Preview

- Click the **play icon** on any voice to hear a sample
- Use the **Random** button to generate new voice descriptions

## Local Development

No build step required. Simply open `index.html` in your browser, or serve with a local server:

```bash
# Option 1: Open directly
open index.html

# Option 2: Local server
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## API Reference

The app uses the MiMo TTS API with the following models:

| Model | Use Case |
|-------|----------|
| `mimo-v2.5-tts-voicedesign` | Custom voices via description |
| `mimo-v2.5-tts-voiceclone` | Voice cloning from audio sample |
| `mimo-v2.5-tts` | Preset voices with dialect tags |

### Endpoints

| Region | URL |
|--------|-----|
| Singapore | `https://token-plan-sgp.xiaomimimo.com/v1/chat/completions` |
| China | `https://token-plan-cn.xiaomimimo.com/v1/chat/completions` |
| Standard | `https://api.xiaomimimo.com/v1/chat/completions` |

### Example API Call

```bash
curl -X POST https://token-plan-sgp.xiaomimimo.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "mimo-v2.5-tts-voicedesign",
    "messages": [
      {"role": "user", "content": "A warm, friendly female voice"},
      {"role": "assistant", "content": "Hello, this is a test."}
    ],
    "audio": {"format": "wav"}
  }'
```

## Troubleshooting

- **"API key rejected"** — Check your key in Settings. Ensure it starts with `tp-`.
- **"Rate limit hit"** — Wait a minute and try again. The API has rate limits.
- **"Request timed out"** — Try shorter text or check your connection.
- **Audio won't play** — Try a different browser. Some mobile browsers block autoplay.
- **Voice clone is slow** — This is normal. Server processing varies (10-60 seconds).

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `⌘+Enter` | Generate speech |
| `Escape` | Cancel generation |
| `Space` | Play/pause audio |

## Privacy

This app sends text and audio samples directly to the MiMo TTS API. No data is stored on any server. Your API key is stored locally in your browser (sessionStorage).

## Tech Stack

- **Frontend:** Vanilla HTML, CSS, JavaScript (single-file app)
- **API:** MiMo TTS v2.5 (OpenAI-compatible endpoint)
- **Audio:** Web Audio API for processing, lamejs for MP3 conversion
- **Fonts:** JetBrains Mono

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

The app is a single `index.html` file (~100KB). All logic, styles, and markup are in this one file.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- [MiMo TTS](https://platform.xiaomimimo.com/docs/en-US/welcome) for the TTS API
- [JetBrains Mono](https://www.jetbrains.com/mono/) for the font
- [lamejs](https://github.com/zhuker/lamejs) for client-side MP3 encoding
