SP-224 Pitch Shifter 📁
A GK Ultra / Alpha Slider Utility

The SP-224 is a browser-based sample-warper built for the Chromebook workflow. I built this because I needed a fast way to shift pitch and calculate BPM without opening a heavy DAW. It’s built on the Web Audio API and styled with a classic Win98 "Teal" aesthetic to keep the UI clean and distraction-free.

🛠 Technical Vibe-Check
Frontend: Hand-coded CSS by the CSS Ninja to mimic the Windows 98 box model and 3D borders.

Engine: Gecko Ultra handled the OfflineAudioContext for the high-quality WAV export.

Logic: Built using vibe-coded prompts to bridge the gap between simple HTML and complex audio processing.

📖 User Manual
1. Loading Samples
Drop your audio file into the Source Audio slot. The SP-224 supports .wav, .mp3, and .ogg. Once loaded, the engine will attempt to "guess" the BPM based on the file duration.

2. BPM Calibration
If the detected BPM feels off, adjust the Sample Bars input.

Most loops are 4 bars.

If it’s a short one-shot or a long loop, change the bar count to recalibrate the math.

3. Shifting the Pitch
Use the Down/Up buttons to shift the sample.

This is a "Resampling" shifter: as the pitch goes up, the speed increases (and vice versa).

The Final BPM display updates in real-time so you know exactly how it will fit in your sequence.

4. The Loop Test
Hit PLAY (LOOP) to hear the shift. This uses the browser's live audio buffer to ensure there’s no lag before you commit to a save.

5. Exporting (The "Save As" Move)
Click Save As WAV.... The SP-224 renders the audio in the background and triggers a browser download. The file is saved as a 16-bit PCM WAV, ready to be dropped into the Omikuji Sequencer or the MK2 Mixer.



Win98 Pitch Shifter Utility (v1.0)A high-fidelity, browser-based audio utility designed with a classic Windows 98 aesthetic. This tool allows users to import loops, automatically detect BPM based on bar length, and perform real-time pitch/tempo shifting with a high-quality WAV export.🎹 FeaturesRetro UI Engine: Fully themed CSS architecture mimicking the Windows 98 "Teal" desktop, complete with 3D inset controls, MS Sans Serif typography, and Post-it note documentation.BPM Intelligence:Auto-Guessing: Analyzes audio duration to predict if a sample is 1, 2, 4, or 8 bars long.Manual Override: Fine-tune the "Sample Bars" parameter to correct BPM detection for irregular loops.Real-Time Pitch Engine:Shifts audio playback rate using the Web Audio API playbackRate parameter.Dynamic Calculation: $BPM_{final} = BPM_{orig} + \Delta BPM$.WAV Export: Renders the shifted audio into a new 16-bit PCM WAV file using an OfflineAudioContext for sample-accurate results.🛠 Technical ImplementationAudio Context & ProcessingThe utility initializes a WebAudioContext on user interaction to handle decoding and playback. Audio is processed through AudioBufferSourceNode, allowing for seamless looping and variable playback rates without digital artifacts.BPM MathThe relationship between duration ($d$), bars ($b$), and BPM is handled via the following logic:$$BPM = \frac{240 \times b}{d}$$Export PipelineUnlike standard recording, this utility uses Offline Rendering. It creates a virtual audio environment to "fast-forward" the render at the adjusted pitch, then reconstructs a RIFF/WAVE header and data chunk from the resulting buffer.🚀 How to UseLoad: Select any .mp3, .wav, or .ogg file.Verify: Check if the "Original BPM" matches your loop. Adjust "Sample Bars" if necessary.Shift: Use the Up/Down buttons to change the tempo in increments of 1 BPM.Preview: Use PLAY (LOOP) to hear the transformation in real-time.Save: Click Save As WAV... to download the processed loop. 
