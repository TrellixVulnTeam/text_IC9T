# text
Models, Datasets, Metrics and Utils for NLP.


## Installation
...


## Usage
<details>
<summary> <b> ModelCreator </b> </summary>
None

</details>


<details>
<summary> <b> Datasets </b> </summary>

- **The dataset module currently contains:**

    Language modeling:   WikiText2, WikiText103, PennTreebank
    
    Machine translation:   None
    
    Sequence tagging(e.g. POS/NER):    UDPOS, CoNLL2000Chunking 
    
    Question answering:   SQuAD1, SQuAD2
    
    Text classification:   AG_NEWS, SogouNews, DBpedia, YelpReviewPolarity, YelpReviewFull, YahooAnswers, AmazonReviewPolarity, AmazonReviewFull, IMDB

  
- **Load NLP related datasets, and build dataloader**
```python
from flowtext.datasets import AG_NEWS
train_iter = AG_NEWS(split='train')
next(train_iter)
# Or iterate with for loop
for (label, line) in train_iter:
    print(label, line)
# Or send to DataLoader
from oneflow.utils.data import DataLoader
train_iter = AG_NEWS(split='train')
dataloader = DataLoader(train_iter, batch_size=8, shuffle=False)
```

</details>


<details>
<summary> <b> Metrics </b> </summary>

- **The dataset module currently contains:**
    
    Bleu_score
    
    Ngram_counter

- **NLP related evaluation metrics**
```python
from flowtext.data.metrics import bleu_score
candidate_corpus = [['My', 'full', 'pytorch', 'test'], ['Another', 'Sentence']]
references_corpus = [[['My', 'full', 'pytorch', 'test'], ['Completely', 'Different']], [['No', 'Match']]]
bleu_score(candidate_corpus, references_corpus)
# 0.8408964276313782
```

</details>


<details>
<summary> <b> Utils </b> </summary>

- **Load tokenizer**
```python
>>> from torchtext.data import get_tokenizer
# The parameter ‘tokenizer’ can support spacy, moses, toktok, revtok, subword, jieba.
>>> tokenizer = get_tokenizer(tokenizer="basic_english", language="en")
>>> tokens = tokenizer("Today is a good day!")
>>> tokens
['today', 'is', 'a', 'good', 'day', '!']
```

</details>
