Goal:
I want my companion to hear my voice and convert it to text without any paid api.

What i have used:
MacBook Air
whisper.cpp
Whisper base model
Ffmpeg
MacBook microphone

What i have built:
I recorded my voice using QuickTime
I converted it to 16 kHz mono WAV with FFmpeg.
Then I gave the WAV file to whisper.cpp with the Whisper base model. The whole process worked locally

Result:
System successfully worked with 38 seconds of voice
Results were terrible, could not recognize most of words i said, it means system works but model needs improvement
[00:00:00.000 --> 00:00:10.000]   İstedi bir negaba beklettiği ise kendi bir hoşuna bitmişlerin yapamaz.

[00:00:10.000 --> 00:00:16.000]   Bilgisayarın, onu biline girelim de ses çalışıyorsunuz.

[00:00:16.000 --> 00:00:18.000]   Hazırlatacak.

[00:00:18.000 --> 00:00:20.000]   Ne oldu? Katmanlarını.

[00:00:20.000 --> 00:00:22.000]   Anlısı da terkine ver.

[00:00:22.000 --> 00:00:24.000]   Matrix, multiplicationlarını.

[00:00:24.000 --> 00:00:27.000]   Nasırla saklayacak.

[00:00:27.000 --> 00:00:31.000]   Sanıçları nasıl yapalım?

[00:00:31.000 --> 00:00:37.000]   Bir şeyleri, cennetleri, siktirde atsın, pili, konulata yazalım.

Next:
Use better model and test again.