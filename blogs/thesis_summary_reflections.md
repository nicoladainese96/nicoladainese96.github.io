---
layout: default
title: "What is the subject of my doctoral thesis?"
---
# What is the subject of my doctoral thesis?

This post is the first of a series that I will write at the same time of my doctoral thesis, with the aim of documenting the process of writing the thesis and explaining to myself and others the bigger picture of my PhD journey.

## Incipit

At the time of writing, May 2025, I have submitted my last article for the PhD ([preprint available here](https://arxiv.org/abs/2505.13180)) and it is finally time to get started in writing the summary part of the doctoral thesis. This is meant to be a standalone piece of the thesis, which explains in reasonable detail all my publications, giving the necessary background to understand them and explaining what original contributions they added to the field relative to the pre-existing related works.

The first task I'm facing is to come up with a title and a narrative that would encompass all the publications at the same time. This is easier said than done, as having such a coherent narrative of my work was not high in the list of my priorities these years. My guiding principle has always been to learn as much as possible from each publication, and especially learn not to stick to ideas that are not promising, after having explored them in depth. So the question now is: "Is there a common thread throughout all my works over these years?"

## Brainstorming research threads

As I stare at the titles of the five publications I want to include in my thesis, I start to note down on my tablet some ideas on how to fit such diverse topics under the same umbrella. While this strikes me as a very complicated combinatorial problem, I have some hope, as after all I know there's my touch in all these works and this in itself is a common thread. To simplify the rest of the post, here are the publications with their reference number:

- [1] Nicola Dainese, Pekka Marttinen, Alexander Ilin, ["Reader: Model-based language-instructed reinforcement learning"](https://aclanthology.org/2023.emnlp-main.1032/), EMNLP 2023.
- [2] Nicola Dainese, Alexander Ilin, Pekka Marttinen, ["Can docstring reformulation with an LLM improve code generation?"](https://aclanthology.org/2024.eacl-srw.24/), EACL Student Research Workshop 2024.
- [3] Matteo Merler\*, Katsiaryna Haitsiukevich\*, Nicola Dainese\*, Pekka Marttinen, ["In-context symbolic regression: Leveraging large language models for function discovery"](https://aclanthology.org/2024.acl-srw.49/), ACL Student Research Workshop 2024.
- [4] Nicola Dainese\*, Matteo Merler\*, Minttu Alakuijala, Pekka Marttinen, ["Generating Code World Models with Large Language Models Guided by Monte Carlo Tree Search"](https://arxiv.org/abs/2405.15383), NeurIPS 2024.
- [5] Matteo Merler\*, Nicola Dainese\*, Minttu Alakuijala, Giovanni Bonetta, Pietro Ferrazzi, Yu Tian, Bernardo Magnini, Pekka Marttinen, ["ViPlan: A Benchmark for Visual Planning with Symbolic Predicates and Vision-Language Models"](https://arxiv.org/abs/2505.13180), ArXiv, 2025.

Without further ado, let's start with the easiest element: **language**. All my works deal with using language to solve some task, or benchmark approaches that do that. So much so that 3 out of 5 works [1,2,3] are published at computational linguistics venues.

Next in line, a bit more tricky to fit: **Large Language Models (LLMs)**. Except for [1], I always used LLMs in my works, and the main reason why this is not the case in the first, is that simply there were no modern open-source LLMs at the time (most of the work was done before ChatGPT came out). However, this is complicated by the fact that the usage of language in that work was very rudimental and it was not making use of any pre-trained model available at the time (e.g., BERT). Furthermore, [5] strictly speaking used Vision-Language Models (VLMs) and not LLMs, but that's not too far of a stretch as the output is still language.

Coming in third, but maybe the most original aspect of the thesis (and the one I personally care the most about): **world modeling**. This is meant in a model-based reinforcement learning fashion, like a causal, action-conditioned model of the environment dynamics and reward function. In my main three publications I made use of really advanced world modeling approaches, from discrete stochastic world modeling [1], to world models made of code [4] and finally action-dependent symbolic world models for planning [5]. Throughout these works I learned how complex it is to have some rudimental model of the world and with how many baked-in assumptions world models usually come to life. However, this keyword alone does not fit at all the remaining two papers, which are applications of LLMs as optimizers for code generation and symbolic regression. Also, in the last work, I didn't build symbolic world models strictly speaking, but I rather benchmarked the ability of VLMs to ground such world models.

Another thread of research is the fascination with **formal languages**, such as code, math equations and symbolic planning languages. In a way, all my applications of LLMs have always been aimed at producing something that supports a clear definition of correctness (e.g., passes all unit tests in the case of code [2], or minimizes some loss over the data in case of math equations [3] and so on). Correctness is always (as far as I can tell) linked to a formal structure, needed to analyze the content of some text, in contrast with "natural language", and this rigid structure makes it possible to turn text into a predictive model. While I don't know if some kind of formal language will be useful or necessary to achieve human-like general intelligence, I did find it worth it to pose the question. Although I cannot say that I have an answer about it, I do feel wiser out of these research experiences and find it meaningful to write and communicate about it.

## Open questions and edge cases
As clearly there isn't one-size-fits-all label for my research, I know set to question whether I can stretch some of the labels to include more papers in them. 

For example, while [1] doesn't use LLMs, it does use a model that receives (and, to a certain degree, understands) language, even if its job is to predict the next reward. So that loosely speaking could count as a language model, which is neither large nor pretrained. I think I will re-lable "language" in "language models", to make it less generic and still sort of applicable to all my works.

Then [3] doesn't concern "world models" as intended in RL, but equations do provide a model of the "world", where the world is the specific, ground-truth phenomenon that generated the data on which we perform the symbolic regression.

[2] is not ticking many boxes, as it's basically trying to do a very specific kind of prompt engineering for code generation with LLMs. I regard it as a shy and incomplete attempt at getting the pulse of topics like exploration, optimization and learning in LLMs, while upskilling myself. I would say that exploration and optimization were important also in [3] and [4], as the setup of these works is similar in that a prerained and frozen LLM needs to iteratively get better at a task without additional training, by leveraging a dynamic context in the prompt. I think adding the label "optimization" to the list would help.

Although there is nothing conclusive in this section, it helped me keeping an open mind on the possible narratives and connections between my works.

## Putting it all together

Here's a little table to summarise what we have said so far:

| Publication | Language models | LLMs | World Model | Formal Language  | Optimization |
|-------------|-----------------|------|-------------|------------------|--------------|
| [1]         |    ~            |  ✗   |      ✓      |        ✗         |       ✗      |
| [2]         |    ✓            |  ✓   |      ✗      |        ~         |       ✓      |
| [3]         |    ✓            |  ✓   |      ✗      |        ✓         |       ✓      |
| [4]         |    ✓            |  ✓   |      ✓      |        ✓         |       ✓      |
| [5]         |    ✓            |  ✓   |      ~      |        ✓         |       ✗      |


Looking at which pair of labels (excluding the generic "language") the following title hit me:
**"World modeling and optimization with language models"**.

While there is no strict logical connection between the two applications "world modeling" and "optimization", all papers fit in at least one of the two bins, and language models can be stretched to include [1] with a little bit of mental gymnastics. So for now I'll run with this title and ask my supervisor some feedack!

## Thesis narrative

Here's a sketch of how the narrative of the thesis could looks like in a condensed, abstract-like version:

*"The thesis focuses on tackling world modeling and optimization tasks through the usage of language models.*
*First, the thesis introduces a language-instructed model-based reinforcement learning method, demonstrating how to successfully learn a stochastic world model of an environment exhibiting novel dynamics, accompanied by language descriptions at test time. This approach improves over the previous model-free state of the art in terms of performance, sample efficiency, and interpretability.*
*Second, two methods for optimizing the generation of Python code via reformulation of the program specification (docstring) with a Large Language Model (LLM) are studied. The findings highlight an unexpected insensitivity of current open-source LLMs to the details of the docstrings.*
*Third, the thesis outlines a method to use an LLM to propose and optimize the analytical formulas that describe some observed data. The method matches or outperforms the overall performance of classic symbolic regression state-of-the-art baselines, while recovering simpler expressions with better out-of-distribution generalization.*
*Fourth, a framework to generate world models written in code via LLMs is presented, together with an advanced method for code generation with LLMs guided by Monte Carlo Tree Search. The thesis demonstrates both the superior performance of the code generation algorithm over strong baselines and successful synthesis of code world models that enable planning agents for RL tasks with greatly improved sample efficiency, interpretability and inference speed.*
*Finally, the thesis proposes a benchmark based on two visual domains, to assess the abilities of Vision-Language Models either as planning agents or as visual grounders of a classic planner based on a symbolic action-dependent world model. The findings show that symbolic planning outperforms direct VLM planning in the domain where accurate image grounding is crucial, whereas the opposite is true in the other domain, where commonsense knowledge and the ability to recover from errors are beneficial.*

*Overall, this thesis advances research in world modeling and task optimization with language models by presenting several methods and a benchmark. The proposed methods offer several benefits, including improved performance, greater sample efficiency, and enhanced interpretability, while the benchmark presented helps track progress and comparing different methods on the task of visual planning."*

Thanks for sticking with me until the end of this article!

Next in my to-do list for this blog series - stay tuned!
- [ ] Produce overview figure of the publications included in the thesis.
- [ ] Draft research questions and corresponding answers.

[Back to blogs](../blog.md).