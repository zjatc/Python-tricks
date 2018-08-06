1. Preprocessing
* Stemming using nltk
```python
from nltk.stem.porter import *

stemmer = PorterStemmer()
stemmer.stem(word)
```

* tokenize and detokenize
```python
tokenized_text = nltk.word_tokenize(text) # used to separate punctuations and words

from nltk.tokenize.moses import MosesDetokenizer
detokenizer = MosesDetokenizer()
detokenizer.detokenize(words_lst, return_str=True) # concat puntuactions and words, recover original string
```

2. Visualization & Data analysis
* used matplotlib and seaborn
```python
import matplotlib.pyplot as plt
import seaborn as sns
```

* most common words in training dataset using word cloud
and analysis positive and negative instances respectively
```python
all_words = ' '.join([text for text in train_dataset]) # in positive_dataset | in negative_dataset
from wordcloud import WordCloud
wordcloud = WordCloud(width=800, height=500, random_state=21, max_font_size=110).generate(all_words)

plt.figure(figsize=(10, 7))
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis('off')
plt.show()
```
