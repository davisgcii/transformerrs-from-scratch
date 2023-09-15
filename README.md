# transformerrs-from-scratch

 In which I implement the Transformers paper from scratch with as little help as possible.

## Introduction

This was inspired by [this post](https://www.lesswrong.com/posts/2kyzD5NddfZZ8iuA7/implementing-a-transformer-from-scratch-in-pytorch-a-write) on Lesswrong where the author, Mislav Juric, implemented the Transformers paper from scratch in PyTorch. I've done this before in my CS231n class at Stanford, but lots of boilerplate and instruction was provided and we had just gone over the architecture and several code snippets in class.

As of starting this short project, I still remember the overarching concepts and (somewhat) how they fit together -- positional encoding; key, query, and value tensors; multiple attention heads; the encoder-decoder structure, etc.

## The Rules

But now I want to try to implement it using as few resources as possible, following the same rules as the blog post above:

1. I was allowed to read only the original paper and start writing code from there. If I got stuck, I was allowed to go to step number 2.
2. I was allowed to consult blog posts and/or articles containing explanations for the things I didn’t understand. If it contained code by any chance, I wouldn’t look at it. If I got stuck here as well, I was allowed to go to step number 3.
3. I was allowed to ask questions on particular things I didn’t understand or about a particular bug in my code, after I tried to solve the misunderstanding or the bug by myself for some reasonable amount of time. Here I want to extend a big thank you to Louis Bradshaw, who helped me clear up some conceptual misunderstandings and also gave me advice on how to best approach finding the bugs I had in my code and solving some specific ones I found. Finally, if none of this worked, I was allowed to go to step 4.
4. I was allowed to look at existing Transformer implementations. Also, I was allowed to copy/paste certain parts of code. I never got to this step.

All of this means turning off copilot and spending lots of time in PyTorch documentation!

## The Goals

Again, I'm using the same goals as the blog post:

1. Ensure that the model was training properly by getting to 0 loss (or near 0 loss) on a very small training set.
2. Ensure that the trained model worked better than the baseline (which was an untrained Transformer model).
3. Ensure that a saved trained model worked properly after being loaded and that it worked when generating sequences token-by-token.
