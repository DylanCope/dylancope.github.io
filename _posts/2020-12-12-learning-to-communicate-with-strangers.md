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
This may involve the signalling of information, relaying instructions, deception, etc. In a typical environment where we would see emergent communication the agents involved have been given the ability to send "messages" to each other across a private *communcation channel*. These messages, which we can also refer to as "words", or "symbols", or "utterances", are simply elements from a predefined set. But while the set is predefined in the sense that there are a fixed number of symbols to choose from, the meaning ascribed to these symbols (or combinations of symbols) is not given. It is for the learning process to assign the semantics, and thus for the communication to "emerge" from training.

A powerful example of this is OpenAI's work (Mordatch & Abbeel, 2018) in training agents to communicate with a "grounded and compositional" learned language (see their blog post on the work [here](https://openai.com/blog/learning-to-communicate/). 
A grounded language is one in which the meanings of words/utterances is "tied" to the environment in which the speakers and listeners are working within.
Compositionality is to do with how words can be arranged together in order to construct more complex communications. For instance, if I have words for "red-ball", "green-ball", and "go-to", I could _compose_ "go-to" with either of the ball words to construct a new and valid sentence.

The following video show's Mordatch and Abbeel's work in action!

<p align="center">
<iframe width="640px" height="360px" src="https://www.youtube.com/embed/liVFy7ZO4OA" display="block" margin-left="auto" margin-right="auto" class="center"></iframe>
</p>

### Communicating with Strangers


<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/taking_to_stranger.png?raw=true" width="400px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

The usual set-up for emergent communication looks a lot like Mordatch and Abbeel's environment, and agents are controlled via a neural network where either either: (1) a single network is trained and reinstantiated multiple times per each agent (called *self-play*), or (2) unique networks trained are from scratch for each agent. In both these cases the training process will arbitrarily choose a communication protocol (think of this as the language that the agents communicate with) for the agents to use. A useful analogy can be made with human languages. English represents one way of organising the set of symbols in the Latin alphabet, but German is an alternative that works equally well. Similarly, on one run of training the agents to learn to communicate one semantics may be applied to the set of communication symbols, but in another run there is no reason for the same semantics to emerge. In fact, the analogy to human languages doesn't stress the point enough because English and German have much shared history, and thus shared semantics. For the AI agents in our experiments there is complete independence between different training runs.   

This introduces the problem of "communicating with strangers", i.e. how do we train AI agents that can learn to communicate with another agent that they have never encountered before.

### Our Test Environment

<p align="center">
<img src="https://github.com/DylanCope/LaTex-Presentation-Learning-to-Communicate-with-Strangers/raw/main/figures/teacher_student_cartoon.png" width="400px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

In our work we propose two methods for this, called *message mutation* and *channel permutation*. Each method results in agents that are able to establish a new communication protocol with a language on the fly and then use this to send information to one another and solve a task. The task we test on is as simple as it could possibly be to demonstrate the efficacy of our proposals: one agent is given a "feature vector", i.e. a binary representation of a number, and the other agent is supposed to produce the "classification" for the feature vector, which is a one-hot encoding of the number in question. We call the former agent "the teacher", and the latter we call "the student", for reasons that will become apparent. Thus, the first agent must somehow communicate enough infomation for the latter agent to be successful. Agents trained together will trivially solve this task, but when paired with a stranger they perform no better than random chance. 

So how do we achieve communication with strangers? Firstly, the environment that I have described thus far is slightly too limited. There is simply no time for the agents to establish a shared language if they immediately have produce the answer. To ammend this we allow for a "protocol establishment phase" where both agents are shown the set of possible feature vectors, and the teacher may send utterances to the student while this occurs. Imagine this like the teacher and student are walking around a room filled with objects, and the teacher is teaching the student the word that they will use to denote each object. However, of course this teaching behaviour will need to be learned, we are simply supplying a minimal set-up for such a process to be possible. We can see the architecture of the set-up in the following diagram:

<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/arch_diagram.png?raw=true" width="620px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

So with the environment outlined, let us move on to the two proposals.

### Channel Randomisation Methods

Our proposals are extensions to the self-play paradigm, hence everything stays the same except these changes:

**Message Mutation:** The key idea here is to simply randomly change some of the messages that a teacher sends to the student. We call such random changes "mutations". The intuition is a familiar one to people interested in making machine learning systems more robust; random variation during the learning process forces the system to be adaptable to change. Thus, when the student sees an unfamiliar language being used they are able to connect the dots.

<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/msg_mutation_cartoon.png?raw=true" width="550px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

**Channel Permutation:** In this method, during training, each time the game is played a random "permutation map" is defined an inserted into the communication channel between the teacher and the student. This map swaps around all the symbols for the duration of that particular game (e.g. an analogous example would be if in English all the characters of the alphabet got randomly swapped around).

<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/chan_perm_cartoon.png?raw=true" width="550px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

### Results

Firstly, for message mutation we compared the "zero-shot performance" (the performance with a stranger) for different probabilities of mutation (the higher, the more frequent mutations are) and found the following results:

<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/p_mutate_and_zs_coordination.png?raw=true" width="620px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

In this graph we see an orange line representing "self-play", which represents the performance reached when an agent was trained with message mutation at a particular level of message mutation probability. The blue line represents the performance when we paired two agents trained in the same manner, but in different training runs. 

We can do the same for channel permutation, here the variable that we adjust along the x-axis is the size of the subset of symbols that we permute. In other words, if we only permute 2 symbols in a set of 5 symbols, 3 symbols are guaranteed to not be effected by the map.

<p align="center">
<img src="https://github.com/DylanCope/dylancope.github.io/blob/master/assets/learning-to-communication-with-strangers/permutation_subset_and_zs_coordination.png?raw=true" width="620px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

### Citing This Work

Cope, Dylan R. & Schoots, Nandi (2020), 'Learning to Communicate with Strangers via Channel Randomisation Methods', Emergent Communication Workshop at the 34th Conference on Neural Information Processing Systems

### Acknowledgements

This work was done at the UKRI Centre for Doctoral Studies in Safe and Trusted Artificial Intelligence.
