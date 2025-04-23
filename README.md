# AI Voice Agent (DeepSeek R1 + AssemblyAI + ElevenLabs)

A real-time conversational voice agent that listens, thinks, and speaks—powered by AssemblyAI for speech-to-text, DeepSeek R1 (7B) for LLM-powered responses, and ElevenLabs for text-to-speech synthesis.

---

## Features

- **Real-time transcription** using AssemblyAI  
- **Conversational intelligence** with DeepSeek R1 via Ollama  
- **Natural speech output** via ElevenLabs  
- Streamed audio output for ultra-smooth interaction  
- Lightweight and runs locally (no cloud LLM usage)

---

## Tech Stack

- **AssemblyAI** – For real-time speech-to-text  
- **DeepSeek R1** (via Ollama) – Local LLM for generating responses  
- **ElevenLabs** – For real-time text-to-speech  
- **Python** – Core programming language  
- **PortAudio / MPV** – For audio capture/playback  

---

## Setup Instructions

### 1. Install Dependencies

#### System-Level

**Debian/Ubuntu:**
```bash
sudo apt install portaudio19-dev
```

**macOS:**
```bash
brew install portaudio
brew install mpv
```

---

#### Python Packages

```bash
pip install "assemblyai[extras]"
pip install ollama
pip install elevenlabs
```

---

### 2. API Keys Setup

- **AssemblyAI**: [Sign up](https://www.assemblyai.com/?utm_source=youtube&utm_medium=referral&utm_campaign=yt_smit_28) to get your API key.
- **ElevenLabs**: [Create an account](https://www.elevenlabs.io/) and get your API key.

Then, replace the placeholders in the script:

```python
aai.settings.api_key = "ASSEMBLYAI_API_KEY"
self.client = ElevenLabs(api_key = "ELEVENLABS_API_KEY")
```

---

### 3. Download DeepSeek R1 Model via Ollama

Install [Ollama](https://ollama.com/) and pull the model:

```bash
ollama pull deepseek-r1:7b
```

---

## How It Works

1. **Real-time audio** is captured from your microphone.  
2. **AssemblyAI** transcribes your voice input into text.  
3. The transcribed **text is passed to DeepSeek R1** running locally via Ollama.  
4. The AI generates a response, which is then **converted to voice** using ElevenLabs.  
5. The response is **streamed back as audio** for real-time conversation.

---

## Example Conversation

```bash
User: What's the capital of Japan?
DeepSeek R1: The capital of Japan is Tokyo.
```

---

## Limitations

- DeepSeek responses are capped to ~300 characters per system prompt.
- Requires an internet connection for AssemblyAI and ElevenLabs APIs.
- Works best with clear audio input and minimal background noise.

---

## Acknowledgements

- [DeepSeek](https://deepseek.com/)
- [AssemblyAI](https://www.assemblyai.com/)
- [ElevenLabs](https://www.elevenlabs.io/)
- [Ollama](https://ollama.com/)

