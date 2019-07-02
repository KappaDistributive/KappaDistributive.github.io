---
title: Machine Learning Golf 
layout: single
mathjax: true
category: Data-Science 
tags: [machine learning, neural networks, ml golf]
---

For the last 5 years or so, I've been lurking on the [Code Golf Stackexchange](https://codegolf.stackexchange.com/). Code Golf is the art of solving a given problem, under specified rules, with as little written code as possible. And if you have never encountered 'golfed code', I highly recommend taking a look. Not sure about other people but to my nerdy brain, reading the ingenious approaches these incredibly talented and passionate coders come up with, is pure entertainment gold!

For various reasons, I've never gotten into the hobby myself -- until last week. While walking my dog, I thought about [this article on the carbon footprint of machine learning](https://www.newscientist.com/article/2205779-creating-an-ai-can-be-five-times-worse-for-the-planet-than-a-car/) and it occurred to me that the neural networks I've designed and trained are super wasteful in terms of their parameter efficiency -- basically the number of free variables during training to adapt them to a given task. So, I thought to myself, what would happen if I added parameter efficiency as an additional metric? 

# Machine Learning Golf

Here's the elevator pitch for ML Golf: The challenger provides

- a public training set,
- a performance goal that needs to be met on the (unmodified!) training set,
- [additional, optional performance goals for bragging rights],
- a set of rules that all entries must satisfy and
- a scoring system to judge the entries by.

For logistics and visibility reasons, I suggest posting any such challenge on https://codegolf.stackexchange.com/ under the tag 'machine-learning', once that tag exists. [^1] 

Challengers then design and train their models according to the stated rules. Once their model meets the mandatory performance goal, they may submit their model (in a suitable form) and all code necessary to verify their results. As per usual in Code Golf, peers will then vote/comment on their and other submissions, suggest improvements and challengers may update their entries at any point and are free to enter multiple models.

# What's the point?

The initial motivation of ML Golf was to find out how to design machine learning models that are much more parameter efficient. However, I don't think that this is the most convincing or even relevant argument for you to consider participating. 

Instead, the motivation for ML Golf is pretty much the same as for any other programming competition: My initial trial runs of ML Golfs proved to be highly entertaining, got me thinking about aspects of machine learning I previously hadn't considered, encourage out-of-the-box thinking and, should the community decide to participate in them, spark the spirited exchange with like-minded people in a casual and safe environment.

# The First Challenge

To kick things off, I'll propose the first, very simple challenge.

In the language and framework of your choice, design and train a neural network that, given $$(x_1, x_2)$$ calculates their product $$x_1 \cdot x_2$$ for all integers $$x_1, x_2$$ between (and including) $$-10$$ and $$10$$. 

## Performance Goal

To qualify, your model may not deviate by more than $$0.5$$ from the correct result on any of those entries.

## Bonus Goal

Achieve a maximal deviation (measured by the Euclidean norm) of $$0.5$$ for the multiplication of all complex numbers with integer components $$c_1 = (a_1, b_1) = a_1 + b_1 \cdot i, c_2 = (a_2, b_2) = a_2 + b_2 \cdot i$$ of Euclidean norm $$\le 10$$. 

## Rules

Your model

- must be a 'traditional' neural network (a node's value is calculated as a weighted linear combination of some of the nodes in the previous layer followed by an activation function),
- may only use activation functions listed as such [in Keras](https://keras.io/activations/),
- must take $$(x_1, x_2)$$ either as a tuple/vector/list/... of integers or floats as its only input,
- return the answer $$\hat{y}$$ as an integer, float (or a suitable container, e.g. a vector or list, that contains this answer).

## Scoring

The neural network with the *smallest number of weights* (including bias weights) wins.


My best attempt so far uses 43 weights and achieves a maximal deviation of $$0.04786$$ as witnessed by $$8 \cdot -8 \mapsto -63.521423$$. I'm sure there's plenty of room for improvements and am looking forward to your entries!

If you want to participate or check my submission, hop over to this [challenge on Code Golf Stackexchange](https://codegolf.stackexchange.com/questions/187562/machine-learning-golf-multiplication).

[^1]: This, of course, doesn't mean that ML Golf is limited to this platform -- feel free to post your challenges and submissions wherever you want. 
