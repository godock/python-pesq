# python-pesq

PESQ (Perceptual Evaluation of Speech Quality) Wrapper for Python Users

# Requirements

    gcc compiler
    numpy
    cython

# Build and Install
```bash
$ git clone https://github.com/ludlows/python-pesq.git
$ cd python-pesq/pypesq
$ python setup.py build_ext --inplace
$ cd ..
```


# Example for narrow band and wide band

```python
from scipy.io import wavfile
from pypesq import pypesq

rate, ref = wavfile.read("./audio/speech.wav")
rate, deg = wavfile.read("./audio/speech_bab_0dB.wav")

print(pypesq(rate, ref, deg, 'wb'))
print(pypesq(rate, ref, deg, 'nb'))
```

# Note

 Sampling rate (fs|rate) - No default. Must select either 8000Hz or 16000Hz.
 
 Note there is narrow band (nb) mode only when sampling rate is 8000Hz.