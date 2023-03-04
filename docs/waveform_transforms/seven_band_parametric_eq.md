# `SevenBandParametricEQ`

_Added in v0.24.0_

Adjust the volume of different frequency bands. This transform is a 7-band
parametric equalizer - a combination of one low shelf filter, five peaking filters
and one high shelf filter, all with randomized gains, Q values and center frequencies.

Because this transform changes the timbre, but keeps the overall "class" of the
sound the same (depending on application), it can be used for data augmentation to
make ML models more robust to various frequency spectrums. Many things can affect
the spectrum, for example:

* the nature and quality of the sound source
* room acoustics
* any objects between the microphone and the sound source
* microphone type/model
* the distance between the sound source and the microphone

The seven bands have center frequencies picked in the following ranges (min-max):

* 42-95 hz
* 91-204 hz
* 196-441 hz
* 421-948 hz
* 909-2045 hz
* 1957-4404 hz
* 4216-9486 hz


## SevenBandParametricEQ API

[`min_gain_db`](#min_gain_db){ #min_gain_db }: `float` • unit: Decibel
:   :octicons-milestone-24: Default: `-12.0`. Minimum number of dB to cut or boost a band

[`max_gain_db`](#max_gain_db){ #max_gain_db }: `float` • unit: decibel
:   :octicons-milestone-24: Default: `12.0`. Maximum number of dB to cut or boost a band

[`p`](#p){ #p }: `float` • range: [0.0, 1.0]
:   :octicons-milestone-24: Default: `0.5`. The probability of applying this transform.
