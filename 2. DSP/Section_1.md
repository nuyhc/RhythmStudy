# [DSP] Section 1
[[REF | AudioSignalProcessingForML]](https://github.com/musikalkemist/AudioSignalProcessingForML)
## 1. Overview
- 이미지 딥러닝에 대한 정보는 많지만, 오디오 관련된 정보는 적은 편임

### Main Q?
- 해당 기술(audio processing)을 어디에 적용할 수 있는가?
  1. Audio classification
  2. Speech Recognition / Speaker Verification
  3. Audio Denoising / Audio Upsampling
  4. Music Information Retrieval
     1. Music Intrument Classification
     2. Mood Classification
     3. ...
  5. ...

### Content
- Sound Waves
- DAC / ADC
- Time-and Frequency-domain audio featues (e.g., rms, spectral centroid, ...)
- Audio Transformaions
  - FT / STFT
  - Constant-Q
  - Mel Spectograms
  - Chromograms
- ...

### What you'll learn
- Get a deep understanding of audio data
- Familiarise with freq./time-domain audio featues
- Extract features from raw audio
- Recognise what audio features to use for ML applications
- Preprocess audio data for ML
- Understand math behind audio transformations
- Use `librosa` for audio projects

## 2. Sound and waveforms

### Sound
- Produced by vibration of an object
- Vibrations cause air molecules to oscillate
- Change in air pressure creates a wave

### Mechanical wave
- Oscillation that travels through space
- Energy travels from one point to another
- The medium is deformed

### Sound Wave
- Atmospheric Pressure
- Compression
- Rarefaction

### Waveform
- 소리의 압력 변화
- 오디오의 특징(features)를 결정하는 중요한 기본
  - Frequency
  - Intensity
  - Timbre

### Periodic and Aperiodic Sound
- All Waveforms
  - Periodic
    - Simple (Single SineWaves)
    - Complex (Multiple SineWaves)
  - Aperiodic
    - Continuous (Noise)
    - Transient (Pulse)

## 3. Intensity, loudness, and timbre (세기와 음색)
