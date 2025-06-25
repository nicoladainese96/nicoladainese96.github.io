---
layout: default
title: "What are the research questions of my thesis?"
---

# What are the research questions of my thesis?

This post is the third of a series that I will write at the same time of my doctoral thesis, with the aim of documenting the process of writing the thesis and explaining to myself and others the bigger picture of my PhD journey.

## Incipit

Research questions are a funny thing. Most of the time, especially in the beginning, researchers will say "let's try to do X", which is definitely not a research question. Also, in ML and AI, there's a sort of stygma around negative results, thus when you read some questions being asked in a paper, you can sort of imagine them being rethorical questions made up at the final stage of the writing process, more than real genuine questions people were wondering about *before* starting the research. 

Before going further, what is a research question? Well, nobody really ever bothered explaing me that, but in its simplest form is a question that a research work poses and hopefully addresses, at least partially. Ideally, I guess one would take a fair look at the existing scientific literature, be puzzeled or curious about something, *formulate a research question*, and set out to answer it, for example by designing and carrying out some experiments. 

As answers need to be verifiable by the scientific community, this really poses a lot of constraints on the kind of questions you can ask. Let's say that you want to prove that method A (likely your new fancy method) is better than method B for some task X. Well, to do that you need to implement both methods and evaluate them fairly on some common benchmarks that are designed to measure the ability in solving task X. However, this can only prove you that "method A is better than method B in the selected benchmarks", which does not prove that "method A is better than method B in solving task X", although it certainly *"provides some evidence"* towards that hypothesis. So by design, you will never be able to definitively answer questions like "Is method A better than method B in solving task X?" Yet, as nobody likes to be reminded how limited the validity of the results is, it's standard practice to ask the more general research question and tacitly keep in mind that in most cases we can never fully answer them, and this is also what I'm going to do in my case.

So in summary, while I have my reservations over both how natural it is to ask research questions and how possible it is to answer them properly, I do think it's a useful abstract concept to make us take a step back and look at our research in a more systematic and theoretical way. With this out of the way, let's dive into which research questions I happened to ask during my PhD!

## Research questions done the quick way

To get a first draft of the research questions the procedure seems quite simple: for every paper, take the main conclusion and ask a question that is answered by that conclusion. This should answer the question "What do I do if I didn't have any clear research question in mind while doing my research?"

I'll refer to my publications as [1] to [5] and you can find them referred at the end of this page.

For [1], I did proposed a model-based RL method for a given RL environment (which in RL automatically defines a task through its reward function) and compared it to the model-free RL method that was proposed together with the environment, finiding it more performing, sample efficient and interpretable.
As all experiments were done on this environment, obviously any conclusions I obtained are true only in this context, and this needs to be clear when posing the question. For example, it's fair to refer to this class of problems as RL tasks with novel goals and dynamics described in language. Hence, the first research question would be:

**RQ1:** *Can we solve RL tasks with novel goals and dynamics by leveraging language descriptions of them in a more sample efficient way than previously done?*

For [2], I tried to use one LLM to optimise the input of another to improve its code generation abilities, but it didn't work. However, for this one I did have a question in mind, or many, sort of. My question was something along the lines of "Is it possible to optimize functions’ docstrings to increase the probability of sampling a correct code solution from any code LLM?", in expectation over problems, models and the possible solutions that can be sampled by a model prompted with a reformulation of the problem.
Anyway, the title itself is a research question, so I guess I can just use that one:

**RQ2:** *Can docstring reformulation with an LLM improve code generation?*

This time is not a rethoric question, as my answer would basically be no! In retrospective I have to say that I am impressed in how well the task is defined mathematically speaking, and how by just reading the paper multiple variants of the research question naturally emerge. Good job on this one!

For [3], I would say that we investigated the application of LLMs to symbolic regression and what advantages they might bring, so:

**RQ3:** *Can LLMs be used to perform symbolic regression? What advantages does this bring with respect to existing methods?*

For [4], we wanted to see two things I'd say: if we could generate code to simulate a world model (we got partial success on that, so I wouldn't say it's a full yes, but neither a full no) and then if we could devise a more performant/efficient algorithm to design code with LLMs in sequential attempts than what was available at the time.

So:

**RQ4:** *Can we use code rather than a neural network to simulate a RL world model?*

and

**RQ5:** *Can we devise a more performant algorithm to design code with LLMs in sequential attempts than what currently available?*

This makes me realise that it would have been interesting to see how well a model-based neural world model would have done in the tasks we focused on. I guess I have the same feeling about so many things in that work, it was super interesting, but also super intense as a timeline and unfortunately we could not have squeezed more into it even if we wished and went back in time.

Finally, for [5], I guess we have 2 questions: is it better to use VLM directly as planners or to use them to ground existing symbolic planners? And then, how good are VLMs at either of these tasks?

























**References:**
- [1] Nicola Dainese, Pekka Marttinen, Alexander Ilin, ["Reader: Model-based language-instructed reinforcement learning"](https://aclanthology.org/2023.emnlp-main.1032/), EMNLP 2023.
- [2] Nicola Dainese, Alexander Ilin, Pekka Marttinen, ["Can docstring reformulation with an LLM improve code generation?"](https://aclanthology.org/2024.eacl-srw.24/), EACL Student Research Workshop 2024.
- [3] Matteo Merler\*, Katsiaryna Haitsiukevich\*, Nicola Dainese\*, Pekka Marttinen, ["In-context symbolic regression: Leveraging large language models for function discovery"](https://aclanthology.org/2024.acl-srw.49/), ACL Student Research Workshop 2024.
- [4] Nicola Dainese\*, Matteo Merler\*, Minttu Alakuijala, Pekka Marttinen, ["Generating Code World Models with Large Language Models Guided by Monte Carlo Tree Search"](https://arxiv.org/abs/2405.15383), NeurIPS 2024.
- [5] Matteo Merler\*, Nicola Dainese\*, Minttu Alakuijala, Giovanni Bonetta, Pietro Ferrazzi, Yu Tian, Bernardo Magnini, Pekka Marttinen, ["ViPlan: A Benchmark for Visual Planning with Symbolic Predicates and Vision-Language Models"](https://arxiv.org/abs/2505.13180), ArXiv, 2025.

[Previous post](overview_figure.md)
[Back to blogs](../blog.md).