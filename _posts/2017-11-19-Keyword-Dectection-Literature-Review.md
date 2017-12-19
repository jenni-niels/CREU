Summaries of a few of the papers I've found on existing keyword spotting (KWS) are below:

* Chen, Guoguo, Carolina Parada, and Georg Heigold. "Small-footprint keyword spotting using deep neural networks." Acoustics, Speech and Signal Processing (ICASSP), 2014 IEEE International Conference on. IEEE, 2014.
    * They use a deep neural network to spot keywords instead of the traditional Hidden Markov Model.  They found that it is a smaller implementation that has reduced computation time/space, and preforms at least as well.
    * Feature Extraction:
        * They use VAD as to only run the neural network on audio regions containing speech.
        * The audio features are captured in frames every 10 ms, and each encapsulate a 25 ms window.
        * The neutral net is given the 30 previous frames, and the future 10 frames at each instance.
    * Training
        * To train the network they had 2.3K instances of each keyword and 133K negative examples.
        * Keywords examined: answer call, ok google, take a picture, etc.

* Hout, Julien van, et al. "Recent Improvements in SRI's Keyword Detection System for Noisy Audio." Fifteenth Annual Conference of the International Speech Communication Association. 2014.
    * They use a series of noise-robust features to improve the accuracy of their KWS in noisy conditions.
    * Noise Robust Features:
        * Damped Oscillator Coefficients
        * Normalized Modulation Coefficients
        * Modulation of Medium Duration Speech Amplitudes
        * Gammatone Filter Coefficients
        * Log-spectrally Enhanced Power Normalized Cepstral Coefficients
        * Gabor-MFCC
    * Results:
        * They found that the phoneme level search missing fewer keywords, than the word level search, but often has more false positives as a result.
        * They determined that a fusion of the features was most accurate for their tests.


* Gales, Mark JF, et al. "Speech recognition and keyword spotting for low-resource languages: Babel project research at CUED." SLTU. 2014.
    * They examine a zero resource acoustic model for languages with little to no transcribed audio.
    * They aim to build a language independent acoustic model, using features such as pitch, plp, and context dependent HMMs.
    * Their results were inconclusive and they found that although this idea
    is likely still possible there is more work to be done in the area.