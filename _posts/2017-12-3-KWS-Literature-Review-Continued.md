Some more literature review of keyword detection:

* Chen, Guoguo, Carolina Parada, and Tara N. Sainath. "Query-by-example keyword spotting using long short-term memory networks." Acoustics, Speech and Signal Processing (ICASSP), 2015 IEEE International Conference on. IEEE, 2015.
    * They use a long short-term memory (LSTM) neural netowrk for KWS.
    * This allows for training new keywords, beyond just those where we have prior knowledge.
    * Feature Extraction:
        * VAD used to reduce computation st. KWS only run on voiced regions.
            * 13-dimensional PLP features
    * The found that this approach reduces the false rejection rate by 86%.

* Chen, et al.  "Low-Resource Keyword Search Strategies for Tamil."  2015 IEEE International Conference on. IEEE, 2015.
    * They propose three strategies for low-research KWS.
        * Submodular Optimization to Select Audio to Transcribe
            * for-each utterance, s, in a set S they measure the degree to with s contains some feature u.  This can be used to determine the probability distribution of that feature.
        * Keyword Aware Language Modeling
        * Word Morph Interpolated Language Model
            * 3 language models are constructed
                * Word based LM, which is trained on all word entries
                * Morph (automatically parsed morphemes) based LM, which is trained by parsing word entries into morphs
                * Hybrid Word-Morph LM, where words with more than one occurrence are retained and words with one occurrence are parsed into morphs.
