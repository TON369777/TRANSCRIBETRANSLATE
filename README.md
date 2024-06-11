# OVERVIEW

Exploration of modern technologies to allow user to enjoy non English videos without assistance of human transcription and translation services. The following script will allow the user to watch non English videos with the assistance of modern automated speech recognition and translation technology.

# BACKGROUND

Technologies explored included:
1) Google Speech Recognition API
2) OpenAI Whisper

OPENAI Whisper was ultimately chosen as it can be used offline after an initial download and is a model trained on 680,000 hours of multilingual and multitask supervised data (according to Open AI). The SpeechRecognition Python library requires connection to internet as it utilises a Google API.

```python
!pip install git+https://github.com/openai/whisper.git
```

Python has existing library to extract audio from video using Moviepy library.
# TOOLS REQUIRED

Computer requirements similiar to utilising AI technologies. Recommended were 16 gigs ram with 1 to 10 VRAM on GPU (depending on model selected) or run on Google Colab.

# PROCESS

The script will strip audio from desired video. The audio is then transcribed into the language detected or chosen, translated and a subtitle file is output which can be used with a video player capable of loading SRT files alongside the video. Examples: VLC Player or default Windows 11 'Film and TV' player.

# FINDINGS
```python
!whisper audio_file --model medium --language zh --task translate
```
![image](https://github.com/TON369777/TRANSCRIBETRANSLATE/assets/156875448/5f8408da-de16-4311-b8e0-7a041d44603b)


OpenAi Whisper was suprisingly accurate with their transcription and translation. A run based on Chinese TV series 'All Men Are Brothers' was completed and the show can be understood and followed with just using the medium model.
The large model did not offer any noticeable benefit for a signficantly longer run time and larger model size.

The final subtitle outputs still has issues, the technology is not quite there where AI can be relied entirely upon:

1) Instances of mistranslations
2) Mistiming of subtitles
3) Long periods of no speech in audio seems to confuse the model causing mistimings of subtitles

With that said though, there are use cases for this level of technology

1) Professional translators can use this technology to create an initial draft reducing turn over time for a translated script. The final SRT can simply be edited (timings and translations)
2) Technology can accompany users with limited knowledge of target language to understand non English videos

