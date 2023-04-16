# signal_correlated_noise
Add noise to speech without changing the signal amplitude envelope.  The main function is sigcor_noise() which is in the iPython notebook sigcor.ipynb along with some demonstrations of how to use it.

**sigcor_noise()** -- add signal correlated noise to an audio file by flipping the polarity of samples randomly.
        
        inputs:
            filename - is a string containing the full path to an audio file (wav or mp3)
            flip_rate(0.5) - determines the proportion of samples to flip (0.5 gives maximum noise)
            start(0) - time (in seconds) at which to start adding noise (default is 0)
            end(-1) - time (in seconds) at which to stop adding noise (default is -1, go the end of the file).
            
        outputs:
            signal - a 1D array that has the altered audio from filename
            fs - the sampling rate of the signal (will be 22050)

- flip_rate = 0, no change, 
- flip_rate = 1, flip the polarity of all of the samples, 
- flip_rate = 0.5,  means flip 1/2 of the samples 
        
For flip_rate = 0.5, imagine flipping a coin for each sample in the audio, heads leave it as it was, tails multiply it by -1.  
        
So, the maximum "noise" is with flip_rate = 0.5.
        


Note that librosa.load() is used to open the audio file.  The audio is resampled to a sampling rate of 22050Hz, and converted to mono (if not mono already) by adding the left and right channels.
