# ML에서의 오디오 신호 처리 영역

## 어떤 문제를 해결 할 수 있는가
ML에서 Audio digital signal processing은 어떻게 쓰일까?  
- Audio classification
- Speech recognition / speaker verification
- Audio denoising / audio upsampling
- Music Information Retrieval
    - Music Instruemnt Classification
    - Mood classification
    - ...
- ...

## 먼저 알아야 할 것
이러한 문제해결을 위해서는 Sound Wave와 Digital to Analog converters 등의 지식이 필요하다.
- Sound Waves
- DAC / ADC
- Time- and frequency-domain audio features (rns, spectral centroid)
- Audio transformations
    - 푸리에 변환 / STFT
    - Constant-Q Transform
    - Mel Spectrogram
    - Chromograms

## 필요한 기술 스택
- python
- librosa


# [Input Representation] Sound와 Waveforms

# Sound
소리가 잘 들리는 것은 물체를 진동시켜 소리가 생성되므로 이러한 물체가 진동하고 진동으로 인해 공기 분자가 진동하고 서로 부딪히면서 기압의 상태를 변화시켜 파동을 만들어 낸다. Air molecules를 통해 한 지점에서 다른 지점으로 에너지를 전달한다. Sound wave나 Mechanical wave가 있을 때, 매개는 형태를 가지며 그 형태는 소리에서 어떤 일이 일어나는 것처럼 보인다.
-> Pressure plot을 사용하여 이 모든 것을 **시각화**할 수 있다.


# Waveform
Pressure plot로 Waveform 이용한 복잡한 Sound를 표현할 수 있다.
- 어떤 노이즈가 있더라도 음악 전체를 나타낼 수 있다.

## Waveform 정보
- 주파수 Frequency
- 강도 Intensity
- 음색 Timbre


# Cents
![Alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Music_intervals_frequency_ratio_equal_tempered_pythagorean_comparison.svg/1920px-Music_intervals_frequency_ratio_equal_tempered_pythagorean_comparison.svg.png)
![Alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/4Octaves.and.Frequencies.Ears.svg/1920px-4Octaves.and.Frequencies.Ears.svg.png)
- Octave divided in 1200 cents
- 100 cents in a semitone
- Noticeable pitch difference: 10-25 cents


# Sound Intensity 사운드 강도

- 사람의 가청 범위
$TOH = 10^{-12}W/M^2$
 
- The Threshold of Hearing and the Decibel Scale (청력의 임계값과 데시벨 척도)

| Source |	Intensity |	Intensity Level |
|--------|--------|--------|
| Threshold of Hearing (TOH)	| 1*10-12 W/m2	| 0 dB |
|Rustling Leaves	| 1*10-11 W/m2	| 10 dB |
| Whisper	| 1*10-10 W/m2	| 20 dB |
| Normal | Conversation |	1*10-6 W/m2	60 dB |

## Intensity level
- Logarithmic scale
- Measured in decibels (dB)
- Ration between two intensity values
- Use an intensity of reference (TOH)
$dB(I) = 10 * log_10$

# Loudness 음량
인간 청각의 지각 정도에 의해 느끼는 소리의 크기(심리량)

# Timbre 음색
바이올린과 트럼펫은 비슷한 Intensity로 연주하지만 우리가 두 악기의 소리가 다르다고 느끼는 건 음색이 다르기 때문이다.

## 음색의 특징
- Timbre is multidimensional
- Sound envelope
- Harmonic content
- Amplitude / frequency modulation

## Sound envelope
![Alt text](https://kr.mathworks.com/help/signal/ref/movingrmsenvelopesofaudiorecordingexample_01_ko_KR.png)
- Attack-Decay-Sustain-Release Model
![Alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/ADSR_parameter.svg/1920px-ADSR_parameter.svg.png)

## Amplitude modulator
- 현악기 트레몰로 (주파수가 아닌 진폭의 변화)
- Periodic variation in amplitude
- In music, used for expressive purposes

# Reference
* [MATLAB - 음성 신호의 피크 포락선](https://kr.mathworks.com/help/signal/ref/envelope.html)
* [musikalkemist/AudioSignalProcessingForML
](https://github.com/musikalkemist/AudioSignalProcessingForML)
