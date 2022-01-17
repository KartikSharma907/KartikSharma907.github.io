---
title: 'Wake-up Word Detection'
date: 2014-08-14
permalink: /posts/wakeup_word/
tags:
  - Gated Recurrent Units
  - Attention based sequence
  - Synthesized dataset
  - Spectogram
  - Dense Layers
---

I constructed a synthesized speech dataset and implemented an Attention based Sequence Network to build a trigger word / keyword detection model using GRU (Gated Recurrent Units) Network.


## Overview
A Trigger word is a word that you use to wake up a virtual voice assistant, for example “Hey Siri” or “Hey Alexa”. The Trigger Word also called Hot Word, is a brick, a module, of speech recognition in the global sense of the term. It is rather a word or a series of words which will be used to trigger the recording of the user’s voice of a speech recognition system.

A deep learning model can be used to build a very effective trigger word detection system if it follows an end-to-end approach. A Deep Learning model prediction takes time because it processes the audio data asynchronous from the input audio streaming.



## Methodology
Data synthesis is an effective way to create a large training set for speech problems, specifically trigger word detection. Using a spectrogram and a 1D conv layer is a common pre-processing step needed to pass audio data to an RNN, GRU or LSTM. The synthesized dataset is trained on an Attention based sequence model. We use a unidirectional RNN rather than a bi-directional RNN, since we want to be able to detect the trigger word almost immediately after it is said. The performance of the model is further improved by implementing GRU (Gated Recurrent Units) Network.



## Technical Details
○ We use audio sampled at 44100 Hz. Thus, a 10 second audio clip is represented by 441000 numbers.

○ The spectrogram tells how many different frequencies are present in an audio clip at a moment in time. The number of timesteps of the spectrogram are 5511.

○ 1375 = Ty (the number of steps in the output of the GRU layer).

○ Model architecture (The model uses 1-D convolutional layers, GRU layers, and dense layers):


○ The 1D convolutional step inputs the 5511 step spectrogram, and outputs a 1375 step output, which is then further processed by multiple layers to get the final Ty = 1375 step output.



Results
We obtained an accuracy of 92.39% on the synthesized dataset. However the testing on real-world dataset still remains.
