---
layout: post
title: Learning to Communication with Strangers
categories: [Research, Machine Learning]
excerpt: Blog post about our research presented at the 4th Emergent Communication Workshop at NeurIPS 2020.
image: https://github.com/DylanCope/LaTex-Presentation-Learning-to-Communicate-with-Strangers/raw/main/figures/teacher_student_cartoon.png
---

### Introduction

In this post I am going to give a high-level overview of a paper that I wrote with my colleague [Nandi Schoots](https://safeandtrustedai.org/person/nandi-schoots/) titled "Learning to Communication with Strangers via Channel Randomisation Methods". 
This work was presented at the 4th Emergent Communication Workshop at NeurIPS 2020, so we will start this article with a quick overview of the nascent field of emergent communication. 
The full paper can be found [here](https://sites.google.com/view/emecom2020/accepted-papers) alongside the other accepted papers at the workshop, and the source code for the project can be found on [this Github repository](https://github.com/DylanCope/zero-shot-comm).
Citation information can be found at the bottom of this page.


### Emergent Communication

The field of emergent communication studies how learning agents in a shared environment may develop strategies involving communication to solve their tasks.
This may involve the signalling of information, relaying instructions, deception, etc. In a typical environment where we would see emergent communication the agents involved have been given the ability to send "messages" to each other across a private *communcation channel*. These messages, which can refer to as "words", or "symbols", or "utterances", are simply elements from a predefined set. But while the set is predefined in the sense that there are a fixed number of symbols to choose from, the meaning ascribed to these symbols (or combinations of symbols) is not given. It is for the learning process to assign the semantics, and thus for the communication to "emerge" from training.

A powerful example of this is OpenAI's work (Mordatch & Abbeel, 2018) in training agents to communicate with a "grounded and compositional" learned language (see their blog post on the work [here](https://openai.com/blog/learning-to-communicate/). 
A grounded language is one in which the meanings of words (communicated utterances) is tied to the environment in which the speakers and listeners are working within.
Compositionality is to do with how words can be arranged together in order to construct more complex communications. For instance, if I have words for "red-ball", "green-ball", and "go-to", I could _compose_ "go-to" with either of the ball words to construct a new and valid sentence.

The following video show's Mordatch and Abbeel's work in action!

<p align="center">
<iframe width="640px" height="360px" src="https://www.youtube.com/embed/liVFy7ZO4OA" display="block" margin-left="auto" margin-right="auto" class="center"></iframe>
</p>

### Communicating with Strangers

<p align="center">
<img src="https://github.com/DylanCope/LaTex-Presentation-Learning-to-Communicate-with-Strangers/raw/main/figures/teacher_student_cartoon.png" width="400px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

The usual set-up for emergent communication looks a lot like Mordatch and Abbeel's environment, and agents are controlled via a neural network where either either: (1) a single network is trained and reinstantiated multiple times per each agent (called *self-play*), or (2) unique networks trained are from scratch for each agent. In both these cases the training process will arbitrarily choose a communication protocol (think of this as the language that the agents communicate with) for the agents to use. A useful analogy can be made with human languages. English represents one way of organising the set of symbols in the Latin alphabet, but German is an alternative that works equally well. Similarly, on one run of training the agents to learn to communicate one semantics may be applied to the set of communication symbols, but in another run there is no reason for the same semantics to emerge. In fact, the analogy to human languages doesn't stress the point enough because English and German have much shared history, and thus shared semantics. For the AI agents in our experiments there is complete independence between different training runs.   


### Channel Randomisation Methods

WIP


### Citing This Work

Cope, Dylan R. & Schoots, Nandi (2020), 'Learning to Communicate with Strangers via Channel Randomisation Methods', Emergent Communication Workshop at the 34th Conference on Neural Information Processing Systems

### Acknowledgements

This work was done at the UKRI Centre for Doctoral Studies in Safe and Trusted Artificial Intelligence.
