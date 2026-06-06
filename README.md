# MiMo TTS Reader

A web-based text-to-speech app powered by [MiMo TTS](https://platform.xiaomimimo.com/docs/en-US/welcome). Design custom voices, clone any voice, and generate natural speech — all in your browser.

https://github.com/user-attachments/assets/5bd1c4ec-60b7-4899-a73b-d29ac71049c5

**[Live Demo →](https://wsamuelw.github.io/mimo-reader/)**

## Features

- **100 preset voices** across 6 categories (Conversational, Professional, Expressive, Youthful, Character, Accent)
- **Voice cloning** from audio file or microphone recording
- **Voice design** with editable descriptions for fine-tuned control
- **Dark/light theme** with system preference detection
- **Download as WAV or MP3** for any project
- **Non-interrupting generation** — keep listening while generating new audio
- **Responsive design** — works on desktop and mobile
- **Keyboard shortcuts** — `⌘+Enter` to generate

## Getting Started

1. **Get an API key** from [MiMo TTS](https://platform.xiaomimimo.com/docs/en-US/welcome)
2. **Open the app** at [wsamuelw.github.io/mimo-reader](https://wsamuelw.github.io/mimo-reader/)
3. **Add your API key** in Settings (top-right corner)
4. **Enter text**, pick a voice, and hit Generate

## Usage

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
- Edit the voice description to fine-tune tone, accent, or pace
- Use the **Random** button to generate new voice descriptions

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

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `⌘+Enter` | Generate speech |
| `Escape` | Cancel generation |
| `Space` | Play/pause audio |

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- [MiMo TTS](https://platform.xiaomimimo.com/docs/en-US/welcome) for the TTS API
- [JetBrains Mono](https://www.jetbrains.com/mono/) for the font
- [lamejs](https://github.com/zhuker/lamejs) for client-side MP3 encoding
