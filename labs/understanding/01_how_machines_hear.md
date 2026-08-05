

The first speech to text experiment worked, but I realized that I do not understand what is actually happening behind it.

## Questions

What is sound physically?

How does a microphone convert sound into numbers?

What is analog and digital?

What is a sample?

Why did we use 16,000 samples per second?

What is sample rate?

What is bit depth?

What is mono?

What is stereo?

Why did Whisper need mono audio?

What is frequency?

What is a waveform?

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
I have watched 3B1B Neural networks video, i had a sense on how it works but not very clear for now. When i give hand written number to the computer, it does not see it as an image, instead it sees it as pixels. Then gives weights between 0 and 1 to each pixel depends on the brightness of that pixel. To be able to fit values between 1 and 0, we use sigmoid function which makes a lot of sense.
There are hidden layers between the first and the last step. Each neuron in a layer has a connection with each neuron in the next layer. To represent them, we use matrix multiplication which also makes sense. But those connections and how does function them are very unclear for now. Will continue by understanding the logic behind of linear algebre first, then will go back to neural networks. 


(August 5, 2026):
I started linear algebra of 3B1B, and learned that the span of two vectors is the all possible combinations you can get by using scalar multiplication and adding of each vector. If they are not in the same line, you can get the whole 2D dimensional vectors by doing that. (av + bw)

If you have two vectors that is not in the same line in 3 dimension, span will be a plane. If you have 3 different vectors that has different span, you can get the whole 3 dimension.

If you have different vectors, and if you can remove one of them without reducing the total span, we call it linearly dependant. Vice versa is linearly independent. 
(av + bw ?= u)

IMPORTANT: The 'basis' of a vector space is a set of 'linearly independent' vectors that 'span' the full space.