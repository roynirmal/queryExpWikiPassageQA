# queryExpWikiPassageQA

Replication [**"Query Expansion with Locally-Trained Word Embeddings"**](http://www.aclweb.org/anthology/P16-1035) by Diaz et. al. for ECIR 2019 on the [**WikiPassageQA dataset**]( https://arxiv.org/pdf/1805.03797.pdf)

Retireval System - Indri 5.13, command used in ipynb using shlex, subprocess

Evaluation System - trec_eval 9.0, implemented in cygwin terminal

Stopword List = [SMART](http://www.lextek.com/manuals/onix/stopwords2.html)
## Experiment Paths
1. Baseline Retrieval on WikiPassageQA - ```./Lemur/WikiPassageQA/```
2. Retrieval using query expansion with Global Embedding - ```./glove.6B/```
3. Retrieval using query expansion with Local Embedding - ```./word2vec/```

## Sanity Check
Performed Sanity Check of all three previous pipline on [**Robust 2004 dataset**](https://trec.nist.gov/data/t13_robust.html) since the original paper also uses them.

Find Sanity Check of the pipelines in ```./aquaint/ ```


