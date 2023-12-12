---
layout: page
title: Home
---

## PhD Research

I am a PhD student at King's College London and Imperial College London studying Computer Science in the [Safe and Trusted AI Centre for Doctoral Training](https://safeandtrustedai.org). Previously, I was a reserach intern at the [Center for Human-Compatible AI (CHAI)](https://www.humancompatible.ai).
My doctoral research is focused on studying language and communication within the context of _Multi-Agent Reinforcement Learning_ (MARL).

**Overview.** A critical problem in Artificial Intelligence is creating computer agents that can collaborate as a member of a team. For many problems, communication is a vital part of a team's success. Yet, most treatments of language in AI focus on learning the statistical patterns of words (i.e. the _"language modelling"_ that underpins most AI chatbots). This is a far cry from the functional uses of language in everyday human cooperation. In this light, my research focuses on what I call the "Cooperative Language Acquisition Problem": here the task is to create an AI that learns the way a community uses language to accomplish some goal. Thereby the AI can join the community and help them achieve said goals."


### Background: Reinforcement Learning and Emergent Communication

In a typical (single-agent) Reinforcement Learning (RL) set-up, an agent interacts with an environment through taking actions based on its observations.
For example, imagine that the agent is a computer program playing a video game.
The observations that it receives could be just like the ones a human player would see, e.g. an image of the game's screen.
Similarly, the actions it could take would be the same as the human; this could correspond to pressing the arrow keys to move or the spacebar to jump.

To train the agent to play the game, we give it rewards when it does something good, and penalties if it does something bad.
We then use clever mathematics and algorithms to have it learn to maximise these rewards.

The multi-agent setting extends this basic set-up to the analogous case of a multiplayer game, where many people connect to a centralised server to cooperate or compete on different problems. For games that require well-executed coordination, communication between players is essential.
We can model this in the MARL framework by allowing agents to send discrete messages to one another at the same time that they take actions in the environment.
The overall setup looks like the following diagram:

<p align="center">
<img src="./assets/marl_communication.png" width="500px" display="block" margin-left="auto" margin-right="auto" class="center"/>
</p>

When we train a population of agents in this scenario, something quite interesting happens.
At the beginning of training, we as programmers have not assigned any meaning to the messages that the agents can send.
In contrast, with actions we have 'assigned meaning' in the sense that when the agent selection "action 0" we have mapped this to the "spacebar" action that a human would usually press.
And the designers of the game have assigned the spacebar the "meaning" of a jump for the player's character, or something like that depending on the game.

This means that the meaning of messages _emerges_ through the training process. Or in slightly over-anthropomorophic terms: the agents find for themselves a communication system that serves their goals.
We call the area of studying investigating this processes _Emergent Communication_, and since the rise of deep learning for MARL it has had a renewed interest.

### My Research: Cooperative Language Acquisition

So with emergent communication we can create a population of agents that solve some task by developing their own communication "language".
Studying the strategies and protolanguages that are developed is interesting in its own right, but an key issue here is that these languages are essentially private.
It is very difficult to decode what the messages mean to the agents, and the agents cannot adapt their communication strategies to new interlocutors.

Thus, my work aims to bridge the gap between language modelling - i.e. learning simply from observations of human language - and emergent communication.
This is where I have posed the challenge of _Cooperative Language Acquisition Problems_, or CLAPs.
In this setting, we are given a dataset of messages sent by a community of agents, actions that the agents took, and we know the problem that they are trying to solve.
Our task then is to build an agent that can _joining in_ with this community to help achieve a shared goal. 

## Other Interests

**Evolutionary Computation.** Evolution is the only process that we know of that can produce the wonderous complexities of the natural world.
From ant colonies to nervous systems, from bee waggle-dances to human language.
I have had a long standing interest in evolution, but it was intensified in early 2022 when I rewatched [Robert Sapolsky's Human Behavioural Biology](https://www.youtube.com/playlist?list=PL848F2368C90DDC3D) lectures and read Neil Shubin's [_Some Assembly Required_](https://www.amazon.com/Some-Assembly-Required-Decoding-Billion/dp/1101871334).
In particular, my renewed interest was focused on the role of _gene regulation_ in the evolution of complex multicellular systems.
Multicellularity is an interesting form of cooperation between individuals, in which their very individuality is given up.
But to coordinate this cooperative endeavour, cells take specialised roles in the organism.
So I revisted a simulation I start in 2016, during my undergraduate.
This side-project ended up becoming a lot more involved than I had original anticipated, and I created a [YouTube video](https://www.youtube.com/channel/UCNxxs-OEF_5xhM8iOX87NSg), wrote [a paper](https://direct.mit.edu/isal/proceedings/isal/35/77/116930) that I presented at ALIFE 2023, and started an Discord community of people interested in the project. You can also read more at this [blog post](https://dylancope.com/protoevo)!

**Science of Deep Learning.** Over the last decade, deep learning has emerged as one of the most powerful tools in building highly-capable AI systems.
Yet, while we understand the principles used to derive the gradient descent algorithm that powers deep learning, we still have a relatively shallow understanding of the learned models.
A fascinating branch of machine learning is in its infancy that aims to fix this, with various subdiscplines encompassing a new _science of deep learning_.
This motivated me and my colleage, Nandi Schoots, to try to understand how [internal representations of features relate to a model's robustness to distributional shift](https://domaingen.github.io/accepted).

## Publications

**Dylan Cope** and Peter McBurney, 2024, [_Learning Translations: Emergent Communication Pretraining for Cooperative Language Acquisition_](https://sites.google.com/view/ad-hoc-teamwork/home?authuser=0), The Ad Hoc Teamwork Workshop at the 38th Annual AAAI Conference on Artificial Intelligence (WAHT@AAAI-24)

Ole Jorgenson, **Dylan Cope**, Nandi Schoots, and Murray Shanahan, 2024, [_Improving Activation Steering in Language Models with Mean-Centring_](https://arxiv.org/abs/2312.03813), Human-Centric Representation Learning Workshop at the 38th Annual AAAI Conference on Artificial Intelligence (HCRL@AAAI-24)

**Dylan Cope**, Justin Svegliato, and Stuart Russell, 2023, [_Learning to Plan with Tree Search via Deep RL_](https://prl-theworkshop.github.io/prl2023-ijcai/), Bridging the Gap Between AI Planning and Reinforcement Learning at the International Joint Conference on Artificial Intelligence (PRL@IJCAI23)

**Dylan Cope**, 2023, [_Real-time Evolution of Multicellularity with Artificial Gene Regulation_](https://arxiv.org/abs/2305.12249), Proceedings of the 2023 Conference on Artificial Life (ALIFE23), MIT Press

Nandi Shoots and **Dylan Cope**, 2023, [_Low-Entropy Latent Variables Harm Out-of-Distribution Performance_](https://domaingen.github.io/accepted), International Conference on Learning Representations Domain Generalization Workshop (DomainGen@ICLR23)

**Dylan Cope** and Peter McBurney, 2022, [_Joining the Conversation: Towards Language Acquisition for Ad Hoc Team Play_](https://openreview.net/forum?id=SLqgf7ZCQbq), the 5th Emergent Communication Workshop at the International Conference on Learning Representations (EmeCom@ICLR22)

**Dylan Cope** and Peter McBurney, 2021, _A Measure of Explanatory Effectiveness_, 1st International Workshop on Trusted Automated Decision-Making

**Dylan Cope** and Nandi Schoots, 2020, [_Learning to Communicate with Strangers via Channel Randomisation Methods_](https://drive.google.com/file/d/1FaBSE8jcuf6hGIbbp34Dxu7jPjh0iJl0/view?usp=sharing), 4th NeurIPS Workshop on Emergent Communication

## News

_Dec 12, 2023:_ Alongside Nandi Schoots and Murray Shanahan, I supervised Ole Jorgenson for his Masters project at Imperial College London.
We continued the project and turned it into a [workshop paper](https://arxiv.org/abs/2312.03813) that has been accepted to the [Human-Centric Representation Learning Workshop](https://hcrl-workshop.github.io/2024/index.html) at AAAI-24.
Come check out the results in Language Model activation steering.

_Dec 11, 2023:_ My paper "Learning Translations: Emergent Communication Pretraining for Cooperative Language Acquisition" has been accepted to [Ad Hoc Teamwork Workshop](https://sites.google.com/view/ad-hoc-teamwork/home?authuser=0) at AAAI-24. I'll be in Vancouver at end of Feb 2024.

_Aug 20, 2023:_ I presented my work with Justin Svegliato and Stuart Russell, ["Learning to Plan with Tree Search via Deep RL"](https://openreview.net/forum?id=IP5kPfDu3w) at the [Bridging the Gap Between AI Planning and Reinforcement Learning (PRL @ IJCAI 2023)](https://prl-theworkshop.github.io/prl2023-ijcai/) Workshop at IJCAI 2023!

_June 6th, 2023:_ I will be at the CHAI Workshop on the 17th of June, 2023, presenting a poster on my work on applying Deep Reinforcement Learning to Tree Search, done in collaboration with Justin Svegliato and Stuart Russell.

_May 5, 2023:_ My paper ["Real-time Evolution of Multicellularity with Artificial Gene Regulation"](https://direct.mit.edu/isal/proceedings/isal/35/77/116930) has been accepted to the [2023 Conference on Artificial Life](https://2023.alife.org/) for an oral presentation and publication in the proceedings. The conference will be hosted at Hokkaido University on July 24th to July 28th, 2023.

_May 4, 2023:_ Nandi Schoots presented our paper ["Low-Entropy Latent Variables Harm Out-of-Distribution Performance"](https://domaingen.github.io/accepted) at the International Conference on Learning Representations (ICLR) Domain Generalization Workshop. 

_September 22, 2022:_ I am helping a group of fellow London-based PhD students to organise the [Safe and Trustworthy AI Workshop](https://www.doc.ic.ac.uk/~chs219/stai-workshop/) on the 2nd of November, 2022, aimed at bringing together early-career researchers. Submit abstracts by the **28/09/2022**.

_April 13, 2022:_ I am excited to announce that I will be joining Stuart Russell's group the [Center for Human Compatible AI](https://humancompatible.ai/) at U.C. Berkeley this summer for a four month internship! I will be working with [Justin Svegliato](https://justinsvegliato.com/) on a project in "AI metareasoning".

_April 7, 2022:_ I have won a "Best Reviewer Award" for my work reviewing papers for [EmeCom@ICLR22](https://sites.google.com/view/emecom2022/home)! Thank you to the organisers for this recognition, and the gift of Fuji Sencha tea :)

_April 1, 2022:_ My paper ["Joining the Conversation: Towards Language Acquisition for Ad Hoc Team Play"](https://openreview.net/forum?id=SLqgf7ZCQbq) written with my PhD supervisor [Peter McBurney](https://nms.kcl.ac.uk/peter.mcburney/) has been accepted to the [the Emergent Communication Workshop at the International Conference on Learning Representations (EmeCom@ICLR22)](https://sites.google.com/view/emecom2022/home). I will lead a discussion group on the topic of the paper at the workshop.

_July 22, 2021:_ My team has won the Safe and Trusted AI Hackathon! We analysed stop-and-search data from the London metropolitan police in terms of disproportionality of stops for minority groups.

_March 27, 2021:_ My paper "A Measure of Explanatory Effectiveness" written with my PhD supervisor [Peter McBurney](https://nms.kcl.ac.uk/peter.mcburney/) has been accepted to the [1st International Workshop on Trusted Automated Decision-Making](https://3drationality.com/TADM2021/). I gave a talk at the workshop on the paper.

_Dec 31, 2020:_ My paper ["Learning to Communicate with Strangers via Channel Randomisation Methods"](https://drive.google.com/file/d/1FaBSE8jcuf6hGIbbp34Dxu7jPjh0iJl0/view?usp=sharing) written with [Nandi Schoots](https://safeandtrustedai.org/person/nandi-schoots/) was accepted to [the Emergent Communication Workshop at the Conference on Neural Information Processing Systems (EmeCom@NeurIPS2020)](https://sites.google.com/view/emecom2020/home). You can find the source code [on my GitHub](https://github.com/DylanCope/zero-shot-comm).

## Teaching

2021/22:

* 6CCS3ML - Machine Learning GTA

2022/23:

* 6CCS3ML - Machine Learning GTA

---

<div itemscope itemtype="https://schema.org/Person"><a itemprop="sameAs" content="https://orcid.org/0000-0003-1147-8010" href="https://orcid.org/0000-0003-1147-8010" target="orcid.widget" rel="me noopener noreferrer" style="vertical-align:top;"><img src="https://orcid.org/sites/default/files/images/orcid_16x16.png" style="width:1em;margin-right:.5em;" alt="ORCID iD icon">https://orcid.org/0000-0003-1147-8010</a></div>

[KCL Pure Research Profile](https://kclpure.kcl.ac.uk/portal/en/persons/dylan-cope)
