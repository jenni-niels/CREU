I've been continuing to verify participant data with team and help organize
volunteer participants.

In addition I'm further analysis the result of a study preformed last semester.
It appears that in the prior study, many of the most common words in the transcripts are articles, conjunctive phrases, and pronouns (both personal and not).  For example, the top 6 are "the, like, and, that, to, i".  This felt like a fairly typical breakdown of English word frequency, so in order to reduce that noise, the top 100 English words were filtered from the list before generating the results.

This produced results were the top words more apparently aligned with the study.  (see. "um, pieces, uumm, sort, ok, think").  However, we still see a lot of hesitation markers, simple verbs, and adjectives that can't give us cognitive content with out their context.  Consequentially we decided to focus first on recognizing top nouns ("pieces, guess, baxter, tool, wheels"), specifically key ones of interest, as they provide a more concrete self-contained semantic content.

As such I'm working to modify the analysis code I had written to filter for nouns and have been researching libraries that may help with that. So far the [NLTK](www.nltk.org) module looks promising.