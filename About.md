# Sentence-Similarity-

High-performance semantic similarity with BERT

![image](https://miro.medium.com/max/1190/1*wvcA77k94ImM0n_7ysijEQ.png)

BERT is the MVP of NLP. And a big part of this is down to BERTs ability to embed the meaning of 
words into densely packed vectors.
We call them dense vectors because every value within the vector has a value and has a reason for 
being that value — this is in contrast to sparse vectors, such as one-hot encoded vectors where the 
majority of values are 0.
BERT is great at creating these dense vectors, and each encoder layer (there are several) outputs a set 
of dense vectors.
For BERT base, this will be a vector containing 768. Those 768 values contain our numerical 
representation of a single token — which we can use as contextual word embeddings.
Because there is one of these vectors for representing each token (output by each encoder), we are 
actually looking at a tensor of size 768 by the number of TOKENS.

![image](https://miro.medium.com/max/1190/1*KOwZLqjbuxqMJAcjHzFuDA.png)
We can take these tensors — and transform them to create semantic representations of the input 
sequence. We can then take our similarity metrics and calculate the respective similarity between 
different sequences.
The simplest and most commonly extracted tensor is the LAST_HIDDEN_STATE tensor — which is 
conveniently output by the BERT model.
Of course, this is a pretty large tensor — at 512x768 — and we want a vector to apply our similarity 
measures to it.
To do this, we need to convert our LAST_HIDDEN_STATES tensor to a vector of 768 dimensions.
