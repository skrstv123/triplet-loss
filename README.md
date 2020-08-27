# triplet-loss
implementation of triplet loss in keras

## what is triplet loss?
A loss function that tries to pull the Embeddings of Anchor and Positive Examples closer, and tries to push the Embeddings of Anchor and Negative Examples away from each other.

Taking mean square difference between Anchor and Positive examples in a batch of N images is:
<img src="https://render.githubusercontent.com/render/math?math=d_p">

Taking mean square difference between Anchor and Negative examples in a batch of N images is:
<img src="https://render.githubusercontent.com/render/math?math=d_n">

For each example, we want:
<img src="https://render.githubusercontent.com/render/math?math=d_p \leq d_n">

Therefore,
<img src="https://render.githubusercontent.com/render/math?math=d_p - d_n \leq 0">


This condition is quite easily satisfied during the training.

**We will make it non-trivial by adding a margin (alpha):**
<img src="https://render.githubusercontent.com/render/math?math=d_p - d_n + \alpha \leq 0">

**thus making it necessary for dn to be more than dp by atleast alpha**

Given the condition above, the Triplet Loss L is defined as:
<img src="https://render.githubusercontent.com/render/math?math= L = max(d_p - d_n + \alpha, 0)">
