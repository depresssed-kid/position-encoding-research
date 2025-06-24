# position-encoding-research
mini research about position encoding in swin transformer v2


In the original swin transformer article, a two-layer mlp is used for positional encoding in window attention, although the use of convolution is self-evident.


The training dataset is too small to train these models, but it was chosen to speed up learning.
So it is better to consider the results only in the context of comparison with each other.

# results
All further results use the pre-trained swin v2 from transformers, where only the crucial heads and positional embeddings are unfrozen.


mlp block changed on 2 layers with conv1d with kernel 1: accuracy on test dataset: 0.24300699300699302, Passage time of 100 epochs: 4799.942727088928 sec

mlp block changed on 2 layers with conv1d with kernel 3: accuracy on test dataset: 0.23295454545454544, Passage time of 100 epochs: 5224.737064123154 sec

the original mlp block has been saved (pretrained): accuracy on test dataset: 0.26005244755244755, Passage time of 100 epochs: 4901.8214321136475 sec

the original mlp block with newly initialized weights: accuracy on test dataset: 0.22027972027972031, Passage time of 100 epochs: 6084.1148018836975 sec
