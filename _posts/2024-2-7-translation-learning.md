---
layout: post
title: Translation Learning for Cooperative Language Acquisition
categories: [Research, Emergent Communication, Reinforcement Learning]
excerpt: We propose a novel AI challenge called a Cooperative Language Acquisition Problem (CLAP) in which a 'joiner' agent learns from a dataset of interactions between agents in a target community. We propose and compare two methods for solving CLAPs; Imitation Learning (IL), and Emergent Communication pretraining and Translation Learning (ECTL) for solving CLAPs.
---

<p align=center>
<a href="https://www.ijcai.org/proceedings/2024/5">IJCAI Paper</a> | <a href="https://drive.google.com/file/d/1ATobmkk8MDDiV3zH7c3BHGgW9KURemvz/view?usp=drive_link">Slides</a>
</p>

**Abstract.**
In Emergent Communication (EC) agents learn to communicate with one another, but the protocols that they develop are specialised to their training community. This observation led to research into Zero-Shot Coordination (ZSC) for learning communication strategies that are robust to agents not encountered during training. However, ZSC typically assumes that no prior data is available about the agents that will be encountered in the zero-shot setting. In many cases, this presents an unnecessarily hard problem and rules out communication via preestablished conventions. We propose a novel AI challenge called a Cooperative Language Acquisition Problem (CLAP) in which the ZSC assumptions are relaxed by allowing a 'joiner' agent to learn from a dataset of interactions between agents in a target community. We propose and compare two methods for solving CLAPs: Imitation Learning (IL), and **Emergent Communication pretraining and Translation Learning** (ECTL), in which an agent is trained in self-play with EC and then learns from the data to translate between the emergent protocol and the target community's protocol.

---

Citing this work:

Dylan Cope & Peter McBurney, 2024, _Proceedings of the Thirty-Third International Joint Conference on Artificial Intelligence
Main Track._ Pages 40-48. https://doi.org/10.24963/ijcai.2024/5

```bibtex
@inproceedings{ijcai2024p5,
  title     = {Learning Translations: Emergent Communication Pretraining for Cooperative Language Acquisition},
  author    = {Cope, Dylan and McBurney, Peter},
  booktitle = {Proceedings of the Thirty-Third International Joint Conference on
               Artificial Intelligence, {IJCAI-24}},
  publisher = {International Joint Conferences on Artificial Intelligence Organization},
  editor    = {Kate Larson},
  pages     = {40--48},
  year      = {2024},
  month     = {8},
  note      = {Main Track},
  doi       = {10.24963/ijcai.2024/5},
  url       = {https://doi.org/10.24963/ijcai.2024/5},
}
```

An early version of this work was presented at the Workshop on <a href="https://sites.google.com/view/ad-hoc-teamwork/home">Ad Hoc Teamwork at AAAI-24</a>

---
