## Second Week

This week we discussed the time-line/projectory of the project, especially in regards to data collection.  Now that the details have be established I will begin to help in data collection starting next week.

In addition I continued to explore the existing code and my literature review.  Summaries for a few of the papers are shown below.

* T.Drugman, Y. Stylianou, "Voiced Activity Detection: Merging Source and Filter-based Information", IEEE Signal Processing Letters, 2014.
    * They propose source-related filters and merge them with filter-based features to produce VAD results.  They found that their proposed method worked better than previous ones, with an average F1 score of 93%.  They attribute this to the fact that filter based feature (especially ones based on power spectral density) tend to not deal well with “sporadic impulsive noise”.
    * filter based features:
      * spectral envelope
      * MFCC
      * PLP
      * low-computational cost
    * source-related features:
      * harmonics: SRH (summation of residual harmonics)
      * Cepstral Peak Prominence (CPP)
    * Information Fusion and Classification
      * Artificial Neural Network (ANN)

* Martin, Rainer. "Spectral subtraction based on minimum statistics." power 6 (1994): 8
    * They propose a spectral subtraction algorithm for the enhancement of noise speech signals.  To limit the suppression of low energy phonemes they use less over subtraction for high frequencies and SNR conditions.  They found that this method “eliminates the need for a speech activity detector” and has an advantage at removing non-stationary noise over other methods.

* Kinnunen, Tomi, and Padmanabhan Rajan. "A practical, self-adaptive voice activity detector for speaker verification with noisy telephone and microphone data." ICASSP. 2013.
    * They exhibit a Unsupervised VAD algorithm that trains models based on MFCCs.  They found that this outperforms energy VAD although accuracy still drop with decreasing SNR.

Plan for next week:

* Begin data collection
* Record ground-truth to determine accuracy
* Search for existing applications
* Continue literature review
