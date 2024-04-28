# Whisper-Hindi-IIT-Bombay-Internship-Assignment-
Whisper is an automatic speech recognition (ASR) system trained on 680,000 hours of multilingual and multitask supervised data collected from the web.We show that the use of such a large and diverse dataset leads to improved robustness to accents, background noise and technical language.  It enables transcription in multiple languages, as well as translation from those languages into English. We are open-sourcing models and inference code to serve as a foundation for building useful applications and for further research on robust speech processing.

### Links
1. [Whisper](https://github.com/openai/whisper)
2. [Vistaar](https://github.com/AI4Bharat/vistaar)
3. [ASR Evaluation](https://github.com/belambert/asr-evaluation)
4. [Test Dataset](https://asr.iitm.ac.in/Gramvaani/NEW/GV_Eval_3h.tar.gz)

```bash
Hello,

Are you still looking for the internship at IIT Bombay for the Machine Learning Profile?
If Yes then Kindly do this task. we expect you to complete a short assignment that just takes one day. But we are providing 7 days to complete.  

You must implement the Whisper Hindi (Automatic Speech Recognition) ASR model. Also calculate the WER for Kathbath dataset.

Thanking You
Ayush
IIT Bombay
```

![](https://images.openai.com/blob/d9c13138-366f-49d3-b8bd-cb3f5a973a5b/asr-summary-of-model-architecture-desktop.svg?width=10&height=10&quality=50)

The Whisper architecture is a simple end-to-end approach, implemented as an encoder-decoder Transformer. Input audio is split into 30-second chunks, converted into a log-Mel spectrogram, and then passed into an encoder. A decoder is trained to predict the corresponding text caption, intermixed with special tokens that direct the single model to perform tasks such as language identification, phrase-level timestamps, multilingual speech transcription, and to-English speech translation.

![](https://images.openai.com/blob/18ff9c06-7853-4e3b-946f-508f0cd7ed13/asr-details-desktop.svg?width=10&height=10&quality=50)

## Whisper Model
Whisper is a general-purpose speech recognition model. It is trained on a large dataset of diverse audio and is also a multitasking model that can perform multilingual speech recognition, speech translation, and language identification.

![](https://raw.githubusercontent.com/openai/whisper/main/approach.png)

## Vistaar
Vistaar is a set of 59 benchmarks and training datasets across various language and domain combinations such as news, education, literature, tourism etc. The training datasets are avaialable for 12 Indian languages amounting to over 10,700 hours of labelled audio data. We also train IndicWhisper models by fine-tuning the Whisper models on the Vistaar train dataset and observe that it has the lowest WER on 39 out of 59 Vistaar benchmarks.

| Datasets      | bn       | gu       | hi       | kn       | ml       | mr       | or       | pa       | sa   | ta       | te       | ur       | avg   |
|---------------|----------|----------|----------|----------|----------|----------|----------|----------|------|----------|----------|----------|-------|
| Kathbath      | 16.6     | 17.8     | **10.3** | **19.3** | **34.8** | **19.9** | 24.7     | 16.9     | 45.6 | **24.2** | 25       | **11.9** | 22.3  |
| Kathbath Hard | 19.4     | **20.6** | **12.0** | **22.2** | **38.4** | **22.1** | 29.1     | 19.7     | 50.5 | **27.5** | 27.8     | **14.7** | 25.3  |
| CommonVoice   | 24.7     | -        | **11.4** | -        | **44.5** | 22.8     | **35.2** | 22.4     | -    | **29.2** | -        | 31.7     | 27.8  |
| FLEURS        | **20.9** | 23.5     | **15.0** | **18.6** | **22.6** | **20.5** | **32.9** | **23.1** | -    | **25.2** | **25.4** | **19.2** | 22.5  |
| IndicTTS      | **18.8** | **19.1** | **7.6**  | **13.2** | **21.4** | **11.4** | **15.0** | -        | -    | **17.2** | 33.8     | -        | 17.5  |
| MUCS          | -        | 33.2     | **12.0** | -        | -        | **12.8** | **27.5** | -        | -    | 28.3     | 32.1     | -        | 24.3  |
| Gramvaani     | -        | -        | **26.8** | -        | -        | -        | -        | -        | -    | -        | -        | -        | 26.8  |
| Average       | 20.1     | 22.8     | 13.6     | 18.3     | 32.3     | 18.2     | 27.4     | 20.5     | 48   | 25.3     | 28.8     | 19.4     | 24.6  |

| Model         | Kathbath | Kathbath-Hard | FLEURS   | CommonVoice | IndicTTS | MUCS         | Gramvaani | Average   |
|---------------|----------|---------------|----------|-------------|----------|--------------|-----------|-----------|
| Google STT    | 14.3     | 16.7          | 19.4     | 20.8        | 18.3     | 17.8         | 59.9      | 23.9      |
| IndicWav2vec  | 12.2     | 16.2          | 18.3     | 20.2        | 15       | 22.9         | 42.1      | 21        |
| Azure STT     | 13.6     | 15.1          | 24.3     | 14.6        | 15.2     | 15.1         | 42.3      | 20        |
| Nvidia-medium | 14       | 15.6          | 19.4     | 20.4        | 12.3     | 12.4         | 41.3      | 19.4      |
| Nvidia-large  | 12.7     | 14.2          | 15.7     | 21.2        | 12.2     | **11.8**     | 42.6      | 18.6      |
| IndicWhisper  | **10.3** | **12.0**      | **11.4** | **15.0**    | **7.6**  | 12           | **26.8**  | **13.6**  |


## Word Error Rate
Word Error Rate (WER) is a metric used to evaluate the performance of automatic speech recognition (ASR) systems. It measures the disparity between the transcribed output generated by the ASR system and the reference or ground truth transcription.

WER is calculated as the ratio of the total number of errors (insertions, deletions, and substitutions) required to align the transcribed text with the reference text, divided by the total number of words in the reference text.

WER provides a comprehensive assessment of the accuracy of ASR systems, taking into account both misrecognitions and omissions of words in the transcription. Lower WER values indicate higher accuracy, with a perfect score of 0 indicating an exact match between the transcribed and reference texts.

WER is a widely used evaluation metric in the field of speech recognition, providing valuable insights into the performance and quality of ASR models across different languages and applications.
