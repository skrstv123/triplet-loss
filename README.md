# triplet-loss
implementation of triplet loss in keras

## what is triplet loss?
A loss function that tries to pull the Embeddings of Anchor and Positive Examples closer, and tries to push the Embeddings of Anchor and Negative Examples away from each other.

Taking mean square difference between Anchor and Positive examples in a batch of N images is:
$
\begin{equation}
d_p 
\end{equation}
$

Taking mean square difference between Anchor and Negative examples in a batch of N images is:
$
\begin{equation}
d_n 
\end{equation}
$

For each example, we want:
$
\begin{equation}
d_p \leq d_n
\end{equation}
$

Therefore,
$
\begin{equation}
d_p - d_n \leq 0
\end{equation}
$

This condition is quite easily satisfied during the training.

**We will make it non-trivial by adding a margin (alpha):**
$
\begin{equation}
d_p - d_n + \alpha \leq 0
\end{equation}
$

**thus making it necessary for dn to be more than dp by atleast alpha**

Given the condition above, the Triplet Loss L is defined as:
$
\begin{equation}
L = max(d_p - d_n + \alpha, 0)
\end{equation}
$
