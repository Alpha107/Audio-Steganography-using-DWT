# Audio-Steganography-using-DWT

## Overview
This project implements an audio steganography system using Discrete Wavelet Transform (DWT) to hide secret audio inside a cover audio. The process involves embedding a secret audio file into a cover audio, then extracting it back from the stego audio. The system allows secure communication of audio information by embedding data imperceptibly into another audio signal. The implemented techniques ensure minimal distortion to the cover audio, providing both privacy and robustness.

## Features
- Audio Embedding with DWT: The secret audio is embedded into a cover audio signal using DWT and a user-defined strength factor (alpha).
- Audio Extraction with DWT: The secret audio can be extracted from the stego audio using inverse DWT.
- Metrics Calculation: Mean Squared Error (MSE) and Signal-to-Noise Ratio (SNR) are calculated to evaluate the quality of the embedding and extraction.
- Visualization: Various waveforms, spectrograms, and histograms are plotted for better visualization and comparison of cover, stego, and secret audios.

## Steps Involved
## **1. Loading Audio Files:**
The first step is to load the cover and secret audio files using the load_audio function. This function reads audio data from files and resamples it to the target sample rate, which ensures uniformity across all audio files used. Audio files can be loaded as mono or stereo based on the requirements.

## **2. Audio Preprocessing:**
Once the audio files are loaded, both the cover and secret audio undergo preprocessing. This includes adjusting the number of channels (mono/stereo) and trimming them to the same length. If the cover and secret audios differ in channels or length, the system adjusts them to be compatible for embedding.

## **3. Embedding Secret Audio Using DWT:**
The core of the process is embedding the secret audio into the cover audio using Discrete Wavelet Transform (DWT) via the embed_dwt function. DWT breaks down the audio into different frequency bands. The secret audio’s details are embedded into the cover’s high-frequency components, as these are less perceptible to human ears.

## **4. Saving Stego Audio:**
After embedding the secret audio into the cover, the resulting stego audio is saved using the save_audio function. This is the audio that contains the hidden secret information but appears nearly identical to the original cover audio.

## **5. Evaluating Stego Audio Quality:**
Once the stego audio is generated, metrics such as Mean Squared Error (MSE) and Signal-to-Noise Ratio (SNR) between the cover and stego audios are calculated using the calculate_metrics function. These metrics help evaluate how much the stego audio differs from the original cover audio.

## **6. Visualizing Cover vs Stego Audio:**
Several visualization techniques are applied to compare the cover and stego audio:

**Waveform Comparison:** Compares the shape of the original secret and extracted secret waveforms.

**Spectrograms:** Show the frequency distribution of both audios.

**RMS Comparison and Histograms:** Highlight energy and amplitude differences between the original and extracted audios.


## Results
After running the model, the following metrics were obtained to evaluate the performance of embedding and extraction:

- Cover vs Stego MSE: {Insert value here}
- Cover vs Stego SNR: {Insert value here} dB
- Original Secret vs Extracted Secret MSE: {Insert value here}
- Original Secret vs Extracted Secret SNR: {Insert value here} dB
These metrics show how imperceptible the embedding is (MSE, SNR between cover and stego), and how well the secret audio can be recovered (MSE, SNR between original secret and extracted secret).

## Conclusion
This project demonstrates a robust method for audio steganography using DWT. The quality of embedding is high, with minimal distortion to the cover audio, and the secret audio can be reliably extracted. The visualizations further support the effectiveness of the embedding process.

## Future Improvements

- Multi-Level Embedding: Currently, the system uses a single-level DWT for embedding the secret audio. By using multi-level decomposition, we could potentially hide larger secrets or improve the imperceptibility of the stego audio.
- Embedding in Frequency Domain: Exploring embedding techniques in other frequency domains, such as Short-Time Fourier Transform (STFT) or Mel-Frequency Cepstral Coefficients (MFCC), could enhance the system’s ability to conceal secret audio in challenging audio environments.
- Susceptibility to Attack: While the system embeds audio imperceptibly, advanced steganalysis techniques could potentially detect anomalies in the stego audio. Attackers using frequency or statistical analysis might be able to identify traces of hidden data.
- Extraction Accuracy in Noisy Conditions: If the stego audio undergoes significant alterations (e.g., through noise or compression), the extraction process may not fully recover the secret audio. Introducing error-correcting codes could help maintain data integrity.






