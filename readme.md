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
Download the Wav2Lip GAN model weights and place it in the project folder Weights


## Pre-Trained Weights

`lipsync` works with two different pre-trained models:

### Wav2Lip  
[📥 Download wav2lip.pth](https://drive.google.com/file/d/1qKU8HG8dR4nW4LvCqpEYmSy6LLpVkZ21/view?usp=sharing)

- More accurate lip synchronization  
- Lips in the result may appear somewhat blurred  

### Wav2Lip + GAN  
[📥 Download wav2lip_gan.pth](https://drive.google.com/file/d/13Ktexq-nZOsAxqrTdMh3Q0ntPB3yiBtv/view?usp=sharing)

- Lips in the result are clearer  
- Synchronization may be slightly less accurate  
