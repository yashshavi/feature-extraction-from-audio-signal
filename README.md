# feature-extraction-from-audio-signal
Line wise explaination of code ,written in featureExtraction.py file(attached).

# LIBRARIES IMPORTS:
Code lines(line no:3-line no:12)
librosa,scipy,wave,numpy,matplotlib.pyplot,pydub,math.


# data loading:
Sampling and loading of audio signal using "librosa" library .
Line no :15

# fourier traansform of sampled values(i.e converting in frequency domain)
(Line no:22)
The first basic step for audio signal processing taking the Furrier transform.
Used np.fft.rfft module.
It returns an array of fourier transformed values of the sampled values taken eariler.

# CALCULATED THE LENGTH OF AUDIO:
  duration
  CodeLine(19)

# Finding maximum, minimum and mean pitch
(Line no:27-39)
calculated frequencies from fourier tranform of data then now the indeices of array of frequencies are the actuall frequencies and then we have extracted the maximum,minimum and mean frequencies.



# ENERGY AND POWER CALCULATION
(LINE NO 44-49)
calculated the values. 


# Intensity
(LINE NO 52-64)
Intensity is calculated using "specgram"(Extracted the intensities from specgram plots using cbar.vmax and cbar.vmin functions).



# Silence detetcion and Speaking rate
(LINE NO 66-127)
splited the audio in words using pydub module's functions(Such as mentioned above) and then found out the speaking rate as words spoken  in one minute diveded by the words in total duration (I.e in full length of audio) ,calculated in wpm(words per minute). Pauses and breakes are extracted using pydub inbuilt function(split_on_silence,detect_silence etc).

# PEAK VALUES AND MAXRISING ,MAXFALLING
(LINE NO 131-135)
Extracted the peak values of a signal using "scipy.signal.find_peaks" function.


# jitter,shimmer,and other acustioc features:(LINE N0 139-166)

Jitter:
Jitter (absolute) is the cycle-to-cycle variation of fundamental frequency.

shimmer:
Shimmer (dB) is expressed as the variability of the peakto-peak amplitude in decibels, i.e. the average absolute base-10 logarithm of the difference between the amplitudes of consecutive periods, multiplied by 20.

Jitter (rap) is defined as the Relative Average Perturbation, the average absolute difference between a period and the average of it and its two neighbours, divided by the average period. 
