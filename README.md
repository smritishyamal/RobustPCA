# Robust PCA

In this repo, I have implemented an optimization algorithm from a given paper.
The task is to implement: Algorithm 1 (Principal Component Pursuit by Alternating Directions) described on page 29 in
https://statweb.stanford.edu/~candes/papers/RobustPCA.pdf
Although the paper is filled with complex proofs, the concept is straight forward and the algorithm can be implemented with a reasonable amount of code.

## Background
Electricity prices tend to vary smoothly in response to supply and demand signals, but are subject to intermittent price spikes that deviate substantially from normal behaviour.
Forming the price data from one commerical trading hub into a matrix $M$ with each day as a row and each hour as a column, we can consider $M$ as the combination of a low-rank matrix $L$ consisting of the normal daily market behaviour, and a sparse matrix $S$ consisting of the intermittent price spikes.
$M$ = $L + S$
Since we can only measure the market prices $M$, we wish estimate $L$ and $S$ by solving the Robust PCA problem:
$\min{\|L\|_* + \lambda |S|_1}$
subject to $L + S = M$
