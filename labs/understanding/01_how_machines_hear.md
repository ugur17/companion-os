

The first speech to text experiment worked, but I realized that I do not understand what is actually happening behind it.

## Questions

(August 25, 2026):
What is sound physically?
Sound is a form of energy. When i speak, the energy that my vocal cord produces using air in my lungs vibrates the air molecules. It creates a air pressure difference and that way each molekul transfers this energy to each other.
UPDATE:
Sound is wave form that carroes energy using air molecules as medium.

How does a microphone convert sound into numbers?
Microphone takes this pressure difference (energy), vibrates the bobin according to the pattern it receives, then the movement of the bobin creates potential difference (voltage) and it creates electric current. That way microphone takes mechanic energy, convert it to magnetic energy and then electric energy. Then it creates a continuous analog electric values. 
UPDATE:
We dont convert mechanical energy to magnetic energy. We use electromagnetic induction to convert mechanical energy to electric energy.

What is analog and digital?
Analog is continuous but digital values are discrete values. Computers only accept digital values since it uses bits to represent values.
UPDATE:
Sampling discretes the time
Quantization discretes the amplitude

Why we need ADC (Analog to Digital Converter)?
Because computers only can take digital values which is discrete.

What is a sample?
sample is how many takes we get in a waveform per second
UPDATE: 
What i wrote above was sample rate. Sample is a value at  any t moment.

Why did we use 16,000 samples per second?
because using 16000 sample, we can represent voices up to 8 kHz and it involves most range a human can hear. Nyquist says we should have at least the sample of 2 times of frequency. It is because we should have at least 2 sample per cycle. 
UPDATE:
A human can hear in a range between 20 Hz and 20kHz. Why we choose 16kHz as a sample is we are not trying to produce a song with high quality, this is enough to represent a voice as a text.

What is sample rate?
Sample rate means how many instant values we get per second from voice waves(analog signal).

What is bit depth?
bit depth is how sensitive we represent each sample. It means how many bits we are using to represent each sample value


(August 26, 2026):
What is mono?
Mono means 1 channel. It means there is only 1 sound source.

What is stereo?
Stereo means 2 channels. For example, in stereo headsets, while watching a movie, i hear things with direction. If the man talks in rigth side of the scene, i feel it was coming from right, like in real life.

How can stereo contain spatial information?
Because there are two different sound source. Sound source means channel here.

Why did Whisper need mono audio?
I am not sure if we have to use mono audio in whisper or can we also use stereo channel, but i think it is beacuse we chosed like this. Because it will be enough for our companion project.

What is frequency?
Frequency is how tight the signal cycles to each other. Calculates the cycle amount per second.

What is fundamental frequency?
I am not sure yet, but i think some fundamental frequency amount to represent the rest of the sound frequency.

What is a waveform?
Waveform is a representation of a sound.

What is PCM?
ADC is taking analog signal and convert it to digital signal. PCM is representation of this result. One example is signed 16 bit little endian, it gives the rules to represent the result of this transition.

What does `16 kHz, 16 bit PCM` actually mean?
It means 16kHz sampled 16 bit represented form of sound.

What is M4A?
This is a compressed representation of sound. So it seizes less room in the memory.

What is a WAV file?
WAV is also a format with header. In the header part we tell which representation we use, and in the body there can be PCM. We need header to tell computer how to read below.

Why did we convert our M4A recording to WAV to use Whisper?
Whisper model does not recognize which representation we use. But whisper.cpp file takes wav as input. If it would take m4a, we would not need to.

Speaker — Reversing the Journey?
Speaker reverse the things we talked about microphone. It takes digital numbers turns into analog values using DAC (Digital to analog converter). Then using electrical power, moves the bobin and creates air pressure difference. We call it electromagnetic force instead of electromagnetic induction. Then this mechanical energy is keeping the pattern and being transferred with air molecules into our ear.

What does an amplifier do?
Amplifier takes the sound and increase the amplitude.

How does my voice reach another person's phone?
It does the same thing what microphone does, then send the information which means pattern to cellular tower using electromagnetic wave. Then cellular towel sends this information to destination's cellular towel. It sends the information the destination device using electromagnetic wave. Then the rest is the same what speaker does. In the transferring process, there are some encoding and decoding to represent information and pattern. What physically transfers is electromagnetic waves.

What is FFmpeg?
It is a tool to convert video or audio to any form we want.

What does "ffmpeg -i test.m4a -ar 16000 -ac 1 test.wav" mean?
-i takes the input test.m4a which is compressed audio file
-ar audio rate, use 16kHz sample rate
-ac audio channel, use mono channel
creates test.wav file
It takes the .m4a file, decode it to original version, resampling the sound using values we described
QUESTION: What do we mean by original version? How do we resample if we have digital representation since we can not have analog values in computer?

What is a spectrogram?

What is Fourier Transform and why do we need it here?

What is a Mel spectrogram?

Why did Whisper print n_mels = 80?

What is a vector in this context?

What are neural network weights?

What is actually stored inside ggml-base.bin?

Why was the model 141 MB?

What does n_audio_layer = 6 mean?

What does n_text_layer = 6 mean?

What is an attention head?

Why did Whisper show 8 attention heads?

What does n_vocab = 51865 mean?

What is a token?

How does Whisper choose the next token?

Why can a bigger model understand the same audio better?

How is all of this related to Transformers and LLMs?

Actions: (August 4, 2026)
I have watched 3B1B Neural networks video, i had a sense on how it works but not very clear for now. When i give hand written number to the computer, it does not see it as an image, instead it sees it as pixels. Then gives weights between 0 and 1 to each pixel depends on the brightness of that pixel.(This is wrong, will be corrected in the next sections.) To be able to fit values between 1 and 0, we use sigmoid function which makes a lot of sense.
There are hidden layers between the first and the last step. Each neuron in a layer has a connection with each neuron in the next layer. To represent them, we use matrix multiplication which also makes sense. But those connections and how does function them are very unclear for now. Will continue by understanding the logic behind of linear algebre first, then will go back to neural networks. 
(August 8, 2026)
I rewatched it after linear algebra recap. 
W.a + b
bias makes the equation affine transformation here, so it is not linear anymore. When we have a sigmoid function or ReLu function, we are able to things that we can not do with linear transformation. 
As an architecture, we decide how many layers will be used, and network will learn itself weights and biases according to the training data. Weights describes how much and in what way each neuron will affect the next layer. Bias means the threshold before we decide which affect we will be taken into account and which one has meaningful affect.


(August 5, 2026):
I started linear algebra of 3B1B, and learned that the span of two vectors is the all possible combinations you can get by using scalar multiplication and adding of each vector. If they are not in the same line, you can get the whole 2D dimensional vectors by doing that. (av + bw)

If you have two vectors that is not in the same line in 3 dimension, span will be a plane. If you have 3 different vectors that has different span, you can get the whole 3 dimension.

If you have different vectors, and if you can remove one of them without reducing the total span, we call it linearly dependant. Vice versa is linearly independent. 
(av + bw ?= u)

IMPORTANT: The 'basis' of a vector space is a set of 'linearly independent' vectors that 'span' the full space.

LINEAR TRANSFORMATION:
If we want to have a function which transforms each point or vectors in a space, we use matrices. (Correction: matrices only represent linear transformations)When we multiply any point with a matrix, we basically get the transformed point of that point. To be linear for a transformation, origin should stay same, parallels should stay parallel. 
The most important thing I understood is that a linear transformation preserves linear combinations.
T(av+bw)=aT(v)+bT(w)
We represent any vector in a space using i and j basis vectors. A matrix is a represent of transformed i and transformed j. 

MATRIX MULTIPLICATION:
If i want to make two transformations consecutively, i will need to multiply two matrices, and each matrix symbolize each transformation. Order matters here, because which transformation i did first, changes the result. 

3D MATRIX MULTIPLICATION:
We have i, j and k here, everything else is the same with 2D matrix. 

August 11, 2026:
I have started to watch calculus series of 3B1B, because while learning gradient descent, i came across to the multi variable derivative and i realized i needed to understand it first. The notation of derivative d shows the change while the range is approaching zero, the notation of integral is coming from SUM and integral represent the addition of infinite number pieces in a graph. We are dealing with changes here. 
Derivative is not only a slope of the graph. It is how sensitive is the output according to very tiny changes in the input. The tangent line appears naturally when the interval between to point approaches zero. 


Questions / Things I Still Don't Understand:
What is fundamental frequency?
What is a harmonic?
Does every frequency in human speech have to be a harmonic?
What is pitch?
What is timbre?
