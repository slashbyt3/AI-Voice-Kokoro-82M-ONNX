# 🎙️ AI Voice – Kokoro-82M ONNX

**Generate cinematic, realistic voiceovers** using the Kokoro-82M ONNX model – perfect for documentary narration. Creates `.wav` files from a script, ready for video editing or use with **AI Animate**.

__Output sample:__
<img width="523" height="228" alt="image" src="https://github.com/user-attachments/assets/be5f30a3-f8bd-4321-9b94-688cf3ae440f" />


## ✨ Features
- **Natural, dramatic voice** (`am_michael` at 0.9x speed for true‑crime tone)
- **Offline execution** after one‑time model download (no recurring API fees)
- **Resume support** – skips already generated audio files
- **Easy customisation** – change voice, speed, language, or the entire script

## 📦 Requirements

- Python 3.8+
- ~4 GB free RAM (for the ONNX model)
- Terminal / command line

## 🚀 Complete setup – step by step

### 1. Clone or create your project folder

```bash
mkdir AI-Voice-Kokoro-82M-ONNX
cd AI-Voice-Kokoro-82M-ONNX
```
### 2. Download the required model files (using terminal)
You need kokoro-v1.0.onnx and voices-v1.0.bin.
Run these two commands in your terminal (one after the other):

# Download the main ONNX model (~340 MB)
```
curl -L -o kokoro-v1.0.onnx \
  https://huggingface.co/kokoro-ai/kokoro-82m-onnx/resolve/main/kokoro-v1.0.onnx
```
# Download the voices file (~70 MB)
```
curl -L -o voices-v1.0.bin \
  https://huggingface.co/kokoro-ai/kokoro-82m-onnx/resolve/main/voices-v1.0.bin
```

# 3. Install Python dependencies
```
pip install soundfile kokoro-onnx
```
(If kokoro-onnx fails, try pip install kokoro – the import in the script is from kokoro_onnx import Kokoro, so the package name may vary. The correct package is kokoro-onnx.)

### 4. Save the voice generation script
Download the file named generate_voice.py 

### 5. Run the generator
```bash
python generate_voice.py
```
What happens:
The model loads (10–20 seconds first time).
Five .wav files are created (01_the_fortress.wav … 05_the_ashes.wav).
If a file already exists, it is skipped automatically.

### 6. Use the audio
The generated .wav files are ready to be used as narration tracks in AI Animate (or any video editor).

# Customisation
### Change voice or speed
Edit the kokoro.create() line:
```python
samples, sample_rate = kokoro.create(text, voice="af_bella", speed=1.0, lang="en-us")
Known voices: am_michael, af_bella, am_adam, af_nicole.
```
### Modify the script
Edit the audio_script dictionary. Keys = output filenames, values = spoken text.

# 🔗 Related projects
AI Animate – sync these voiceovers with images to produce a full documentary video.

# 🧠 Built with Kokoro ONNX, soundfile, Python
