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

![CoverVsStego](https://github.com/user-attachments/assets/d4d4c936-35d3-403c-b5a5-cd999bea2df9)

![WaveformOverlay](https://github.com/user-attachments/assets/398d9e40-4959-44b6-94f8-248bb02df925)


**Spectrograms:** Show the frequency distribution of both audios.

![CoverSpectrogram](https://github.com/user-attachments/assets/b016ace9-b868-41cf-bb82-6b0dda9e50f5)

![StegoSpectrogram](https://github.com/user-attachments/assets/dd3263f6-eb73-4b4a-a7af-081f66c529f5)


**RMS Comparison and Histograms:** Highlight energy and amplitude differences between the original and extracted audios.

![RMSComp](https://github.com/user-attachments/assets/be3860aa-ce62-4568-be67-bd1a99ece1a1)

![CoverHistogram](https://github.com/user-attachments/assets/bcf62bbd-a7de-44f4-8bfd-1ff691671442)

![StegoHistogram](https://github.com/user-attachments/assets/a58b8d0d-ad4d-4323-b84f-401bb94e96c3)


## Results
After running the model, the following metrics were obtained to evaluate the performance of embedding and extraction:

- MSE (Cover vs Stego): 0.000003

- SNR (Cover vs Stego): 40.92 dB

## Conclusion
This project demonstrates a robust method for audio steganography using DWT. The quality of embedding is high, with minimal distortion to the cover audio, and the secret audio can be reliably extracted. The visualizations further support the effectiveness of the embedding process.

## Future Improvements

- Multi-Level Embedding: Currently, the system uses a single-level DWT for embedding the secret audio. By using multi-level decomposition, we could potentially hide larger secrets or improve the imperceptibility of the stego audio.
- Embedding in Frequency Domain: Exploring embedding techniques in other frequency domains, such as Short-Time Fourier Transform (STFT) or Mel-Frequency Cepstral Coefficients (MFCC), could enhance the system’s ability to conceal secret audio in challenging audio environments.
- Susceptibility to Attack: While the system embeds audio imperceptibly, advanced steganalysis techniques could potentially detect anomalies in the stego audio. Attackers using frequency or statistical analysis might be able to identify traces of hidden data.
- Extraction Accuracy in Noisy Conditions: If the stego audio undergoes significant alterations (e.g., through noise or compression), the extraction process may not fully recover the secret audio. Introducing error-correcting codes could help maintain data integrity.






