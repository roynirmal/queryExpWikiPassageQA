# Proposal for the final part of my thesis

While reproducing [Diaz et al.](http://www.aclweb.org/anthology/P16-1035)'s query expansion pipeline in the question answering task
we came across the following error types:

1. **Complex Inference** - when a question's semantics is complicated
2. **Missing Keywords** - when a question term is missing from the (small) vocabulory
3. **Ambiguous Relevant Passages** - this is a shortcoming of the dataset
4. **Incorrect tokenization** - presence of word's like *ahimsa* or *tech* instead of technology
5. **Wrong Expansion Terms** - completely wrong expansion terms
6. **Unknown**


So far we have used word2vec and Glove as our word embedding for query expansion. These representations have a few short comings:
- As input, they only have one-hot encoding of words, missing out important features of words
- They learn context-independent embedding of words. *Bank* will have the same representation in ```bank deposit``` and ```river bank```


### ***Goal*** - to learn better representation of words :space_invader: 
> We want to reduce error 1 and 4. Error 2 can be reduced, as we have already seen, by training our local embedding on an external corpora.
 Error 3 is a dataset shortcoming. So we look to obtain representations that leads to better understanding of terms and queries.


[Cao et al.](https://aaai.org/ocs/index.php/AAAI/AAAI17/paper/view/14724) use subword features followed by a CNN to learn word representations
and structural information using Convolutional Learning. 

**Hypothesis** - Convolutional Learning of context for word representation will help in better semantical understanding. Hence,  we 
 will find better expansion terms to questions which requires complex inference. Having better contextual understanding tpgether with sunword information, 
leads to better understanding of complex questions.

**How** - We will replicate [Cao et al.](https://aaai.org/ocs/index.php/AAAI/AAAI17/paper/view/14724)'s architecture and run experiments 
to test our hypothesis. If we prove it right, we will see how the embeddings are different from word2vec. If not, further error analysis.

**Next Step** - We will try to include other features, upon better understanding of how these networks work, and try to improve the above word embedding model.
Improvement options:
- character based input and the loss is calculate against pre-trained word embeddings 
- word or word + character based input and output representation
- learning character level/trigram level representation to handle out of vocabulary words. There will be a matrix for character and trigram vectors. Each word can be the summation of its character/trigram representation
- multitask learning ? 

**A long shot** - I would really like to include BERT/ELMO as the final step of the project. To see, the effect of pre-trained BiLM's on word embeddings and query expansion. I just need a bit of help/time to fully understand how they work.
Can we use them as a word similarity finding task?



### Other Experiments that I plan to perform/performing right now
- [ ] Ground Truth vs Generated Embedding Experiment
- [ ] Mask Query Term experiment: Have to think about the metrics?
- [ ] What about the weights of the expansion?
- [ ] Comparison of RM3 expansion terms with expansion terms obtained from the local embedding model 
- [ ] Expeirments showing ***query expansion false positives*** how many expansion terms are present in non correct passages
- [ ] Write about QE in QA in related work section? 
- [ ] Visualisation of local and global embedding in the 2D space using tsne, and if they do not work understanding why they do not work.
- [ ] Obersving which questions are most difficult to answer (Why/What/How etc..)
- [ ] If the new embedding works, comparing and visualising the new embedding with word2vec
- [ ] Experiment with speed of our models
