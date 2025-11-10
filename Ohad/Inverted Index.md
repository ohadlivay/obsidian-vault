Data structure where each key is a word (or lemma, stem, kgram,.. ) from the corpus, and the values are the documents (or document id) that contain this index word. 
{Haifa -> 33342, 1410, 140650 , 1039492,....}

for boolean models, we can index (use key) a certain logic condition between the words.
e.g.
{Haifa AND Tel Aviv -> 62246, 121773, 196}
{Haifa AND NOT Jaffa -> 7171, 6322, 8244}