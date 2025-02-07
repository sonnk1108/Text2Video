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
```bash
git clone https://github.com/your-username/Text-to-LipSync.git
cd Text-to-LipSync
2️⃣ Install Dependencies
Ensure you have Python 3.8+ installed, then install required libraries:

bash
Copy
Edit
pip install edge-tts nest_asyncio pydub librosa soundfile lipsync
3️⃣ Install FFmpeg (If Not Installed)
FFmpeg is required for processing audio/video. Install it:

4️⃣ Download Pretrained Wav2Lip Model
Download the Wav2Lip GAN model weights and place it in the project folder:

bash
Copy
Edit
wget https://github.com/Rudrabha/Wav2Lip/releases/download/v1.0/wav2lip_gan.pth
🚀 Usage
Convert Text to Speech (TTS)
Run the script to generate an MP3 file and convert it to WAV:

python
Copy
Edit
import edge_tts
import asyncio
import nest_asyncio

# Fix event loop issue in Jupyter Notebook
nest_asyncio.apply()

async def generate_audio(text, output_file="output.mp3", voice="vi-VN-NamMinhNeural"):
    """
    Generates an audio file from the given text in Vietnamese using Microsoft Edge-TTS.
    """
    tts = edge_tts.Communicate(text, voice)
    await tts.save(output_file)
    print(f"Audio saved as {output_file}")

# Example usage
text = "Xin chào, đây là một đoạn văn bản được chuyển đổi thành giọng nói tiếng Việt."
asyncio.run(generate_audio(text))
Convert MP3 to WAV
python
Copy
Edit
from pydub import AudioSegment
import librosa
import soundfile as sf

def convert_mp3_to_wav(mp3_file, wav_file):
    """
    Converts an MP3 file to WAV using Librosa.
    """
    y, sr = librosa.load(mp3_file, sr=None)  # Load MP3
    sf.write(wav_file, y, sr)  # Save as WAV
    print(f"Converted {mp3_file} to {wav_file}")

# Example usage
convert_mp3_to_wav("output.mp3", "output.wav")
Perform Lip Synchronization
python
Copy
Edit
from lipsync import LipSync
import os

# Ensure FFmpeg is in PATH
os.environ["PATH"] += os.pathsep + r"C:\ffmpeg\bin"

# Initialize the LipSync object
lip = LipSync(
    model='wav2lip',  # Model type
    checkpoint_path='wav2lip_gan.pth',  # Path to the model weights
    nosmooth=True,  # Disable smoothing
    device='cuda',  # Device to run on ('cpu' or 'cuda')
    img_size=96,  # Image size
    save_cache=True,  # Save frames to cache
)

# Perform lip synchronization
lip.sync(
    'test.jpg',  # Path to the source video or image
    'output.wav',   # Path to the audio file
    'result.mp4'         # Path to save the output video
)
📌 Notes
Use CUDA for faster processing (device='cuda').
If you see FFmpeg errors, make sure it's installed and in the system PATH.
The input image (test.jpg) should be a clear frontal face for best results.
Ensure that wav2lip_gan.pth is in the same directory.
📜 License
This project is for educational and research purposes only. Please follow ethical guidelines when using AI-generated content.

"# Text2Video"  "# Text2Video" 
"# Text2Video" 
