# **Text-to-LipSync: Convert Text to Speech and Sync with Lip Movements**

This project **converts text to Vietnamese speech using Microsoft Edge-TTS**, then **syncs the generated speech with a static image or video** using the Wav2Lip model. The result is a **realistic talking face video**.

---

## **🛠 Features**
- Convert **text to speech (TTS)** using **Microsoft Edge-TTS**.
- Convert **MP3 to WAV** using **Librosa** for further processing.
- Generate **lip-synced videos** with **Wav2Lip**.
- Supports **CPU and CUDA (GPU acceleration)** for fast processing.
- **Automatic file conversion** and caching for efficiency.

---

## **📦 Installation**
### **1️⃣ Clone the Repository**

git clone https://github.com/your-username/Text-to-LipSync.git
cd Text-to-LipSync

2️⃣ Install Dependencies
Ensure you have Python 3.8+ installed, then install required libraries:

pip install edge-tts nest_asyncio pydub librosa soundfile lipsync

3️⃣ Install FFmpeg (If Not Installed)
FFmpeg is required for processing audio/video.

4️⃣ Download Pretrained Wav2Lip Model
Download the Wav2Lip GAN model weights and place it in the project folder



