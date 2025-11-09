---
title: 'The Power of Decentralization'
date: 2025-11-05
author: 'Xiaocong Yang'
reviewer: 'Daniel Elliott'
permalink: /posts/2025/11/decentralization/
excerpt: 'This post explores how decentralized information processing plays a key role in almost any Complex Systems, including Neural Networks, Multi-Agent Systems and beyond.'
tags:
  - Complex System
  - AI
  - Philosophy
references:
  - "Aristotle. (1998). Politics (C. D. C. Reeve, Trans.). Hackett Publishing Company."
  - "Plato. (2004). Republic (C. D. C. Reeve, Trans.). Hackett Publishing Company."
  - "Hebb, D. O. (1949). The organization of behavior: A neuropsychological theory. Wiley."
  - "Vapnik, V. N. (1998). Statistical learning theory. Wiley."
  - "Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep learning. MIT Press."
  - "Wolfram, S. (2002). A new kind of science. Wolfram Media."
  - "Smith, A. (1776). An inquiry into the nature and causes of the wealth of nations. W. Strahan and T. Cadell."
  - "Zhang, K., Yang, Z., & Başar, T. (2018). Fully decentralized multi-agent reinforcement learning with networked agents. PMLR 80:5872-5881."
  - "Lasry, J.-M., & Lions, P.-L. (2007). Mean field games. Japanese Journal of Mathematics, 2(1), 229–260."
  - "Hayek, F. A. (1945). The use of knowledge in society. American Economic Review, 35(4), 519–530." 
share: true
comments: true
---

Complex systems – from ant colonies and financial markets to the human brain and modern AI – usually succeed not because of one dominant genius calling the shots, but because of many components working in concert. In these systems, information is processed across numerous simple agents or modules, yet the collective outcome can be remarkably intelligent, robust, and efficient. Think of a swarm of bees choosing a new nest site, a crowd accurately guessing the weight of an ox, or a neural network’s “neurons” jointly recognizing a face. In each case, decentralization underlies the system’s power. This post takes a deep dive into how decentralization makes complex systems work, drawing on examples from daily life to scientific areas.

## Wisdom of the Crowd

"Many, though not individually good men, yet when they come together may be better, not individually but collectively, than those who are so, ..." This was the answer that the Greek "Father of Science" Aristotle gave to the perennial question of *aristocracy versus democracy* in his work *Politics*. It is extraordinarily advanced at his time both politically and epistemically. In 4th century BCE, the dominant political view in Greek philosophy was *elitist*. For example, Aristotle's teacher Plato argued that only philosopher-kings — a small, enlightened group consisting of elites  — should rule, because ordinary citizens were governed by appetites rather than reason. Even in democratic Athens, political participation was limited to free male citizens (~10% of the population), and “the mob” was often portrayed as impulsive or corruptible. On the other hand, probability theory and statistics were still underdeveloped in his era: he did not have powerful tools like Central Limit Theorem as we have to predict the aggregated behavior, but still managed to recognize three key conditions that centuries later became the mathematical basis of “Wisdom of Crowds”: Independence, Diversity and Aggregation. When taking a closer look at his work, there are many clues scattered at different paragraphs about such conditions. He emphasizes that citizens should deliberate individually and bring distinct experiences from “different walks of life”, each person should possess a fragment of virtue, and finally their partial judgments could be combined into a more complete collective judgment as "a potluck meal". 

Well, this sounds like typical Aristotle — the young genius who upheld "Plato is dear to me, but dearer still is truth". We have no way to reconstruct the scene where the master and his disciple debated this topic, but it shouldn't have turned into a quarrel. Assuming, however, that their debate was "combative but cordial"; the key is, they might never realize that their debates had propelled human civilization to an entirely new level of thought. The "Wisdom of the Crowd" principle has been applied to many areas and through many forms over the past two millennia. Juries in legal trials rely on multiple independent jurors to reach fair verdicts, rather than a single "smart" judge – akin to taking a “majority vote” on truth. Prediction markets and polls aggregate many perspectives to forecast elections or sporting events. Even the everyday “ask the audience” lifeline in game shows capitalizes on crowd wisdom – more often than not, the audience’s majority answer is correct. The key ingredients for crowd wisdom are diversity of thought and independence of members. When those are present, distributed human decision-making can outperform centralized decisions by any single person.


## Collective Intelligence in Nature

Nature is replete with examples of decentralized decision-making that give rise to complex, adaptive behavior. Social insects like ants and bees are a case in point. A single ant is a very simple creature with limited knowledge, yet ant colonies can accomplish sophisticated feats like finding the shortest path to a food source or efficiently dividing labor among nest tasks. How? Through local interactions and simple rules followed by thousands of ants without any ant in charge.

For example, when ants are seeking food, they engage in a decentralized trial-and-error exploration. If there are two paths from the nest to some food, initially individual ants choose paths at random. Ants deposit pheromone on the ground as they walk. Critically, ants taking the shorter path reach the food and return to the nest faster, so they end up making more trips (and thus laying more pheromone per unit time) than ants on the longer path. Over time, the shorter path builds up a much stronger pheromone trail. More and more ants arriving at the junction will sense the stronger pheromone on that shorter route and follow it, reinforcing the good path further with their own pheromones. This positive feedback loop continues until almost the entire colony is using the optimal route. Remarkably, the colony as a whole has solved a shortest-path problem without any ant knowing the full map – **a collective decision emerges from many local decisions**. If the environment changes (say a path is blocked), the ants will eventually find a new route through the same self-organizing process. This robustness and adaptability illustrate why distributed decision-making is so powerful in complex, ever-changing environments.

## The Brain: An Orchestra of Neurons Without a Conductor

Moving from colonies and flocks outside us to the one inside our heads: the human brain is one of the most complex systems known, and it too relies on distributed decision-making at a neuronal level. The brain is composed of around 86 billion neurons, none of which individually “thinks” in any human-understandable sense. Each neuron is a simple cell that either fires an electrical impulse or not, based on inputs from other neurons. There is no single neuron or central processor directing the others – cognition emerges from the collective firing patterns of many neurons interacting in parallel. In other words, intelligence in the brain is distributed: no single neuron holds a memory or an idea; those are stored in the patterns of activity across huge networks of neurons.

Neuroscientists emphasize that no neuron acts alone: even a simple concept or memory involves networks of neurons acting together. For instance, when you recall a friend’s face, countless neurons across different brain regions participate in representing that memory. If a few of those neurons die or get noisy, it’s not catastrophic – other neurons carrying overlapping pieces of the memory ensure you still recognize your friend. This is analogous to a crowd where no single person’s opinion is decisive, but the aggregate is. The brain’s distributed architecture makes it remarkably robust. There is evidence that even after significant brain damage, people can often re-learn or recover functions, because the remaining neurons reorganize to take over tasks – something a centrally wired system could hardly do. In computing terms, the brain has no single point of failure; it’s more like the Internet (distributed, redundant) than a top-down factory line.


## AI’s Journey: From Centralized Learning to Distributed Intelligence

Let's switch our attention from biology to technology. Perhaps one of the most striking shifts in technology – and one that AI researchers know intimately – is the evolution of Artificial Intelligence from a mostly centralized, hand-designed approach to a more distributed, self-organizing approach. Early AI and machine learning methods often resembled a top-down design: human experts would carefully craft features or rules, and algorithms would then optimize a single model against data. Whereas today’s most successful AI systems -- Deep Neural Networks -- look very different. They involve lots of simple computational units ("artificial neurons") connected in networks, learning collaboratively from data with minimal human intervention in feature design. In a sense, AI has moved from a paradigm of “let’s have one smart algorithm figure it all out” to “let’s have many simple units learn together, and let the solution emerge.”



### Ensemble Learning ###

One bridge between traditional statistical learning and modern deep learning approaches in AI is the rise of ensemble learning. Ensemble methods combine the predictions of multiple models (often called “base learners”) to make a final decision. Instead of relying on a single classifier or regressor, we train a diverse collection of models and then aggregate their outputs – for example, by voting or averaging. The idea is straightforward: even if each individual model is imperfect, their errors may be uncorrelated and can be cancelled. Ensemble algorithms like Random Forest and XGBoost have leveraged this insight to win many machine learning competitions since the late 2000s, and they remain competitive in some areas even today.

### Statistical Learning v.s. Deep Learning: A Battle between Centralization and Decentralization  ###

Now let’s look at both sides of this bridge. Traditional statistical learning theory, as formalized by Vapnik, Fisher, and others, explicitly targets at **analytical tractability** — both in the model and in its optimization. In these models, parameters are analytically separable: they interact directly with the loss function, not through one another; models such as Linear Regression, SVM, or LDA admit closed-form parameter estimators that can be written down in the form of $\hat{\theta} = \arg\min_{\theta} L(\theta)$. Even when closed forms are not available, as in Logistic Regression or CRF, the optimization usually remains convex and thus theoretically well-characterized.

In contrast, Deep Neural Networks admit no analytically tractable relationship between input and output. The mapping from input to output is a deep composition of nonlinear transformations where parameters are sequentially coupled; to understand the model’s behavior, one must perform a full forward simulation. The learning dynamics of such networks are governed by iterative, non-convex optimization processes that lack analytical guarantees. In this dual sense, deep networks exhibit **computational irreducibility** — their behavior can only be revealed through computation itself, not derived through symbolic analysis.

If we explore the root cause of the difference above, you'll find it's due to the model structures - as we might well expect to see. In statistical learning methods, the computational graphs are single-layer: $\theta \longrightarrow f(x;\theta) \longrightarrow L$ without any intermediate variables, and a "central planner" (the optimizer) passes the global information directly to each parameter. However, in Deep Neural Networks, as we know, parameters are organized in layers which are stacked on top of each other: For example, an MLP network without bias terms can be expressed as $y = f_L(W_L f_{L-1}(W_{L-1} \dots f_1(W_1 x)))$ where each $W_l$ affects the next layer’s activation. When calculating the gradient to update parameters $\theta = \lbrace W_i \rbrace_{i=1}^L$, it is inevitable that you'll rely on backpropagation to update parameters layer by layer: $\nabla_{W_l} L = \frac{\partial L}{\partial h^{(L)}}
\frac{\partial h^{(L)}}{\partial h^{(L-1)}}
\dots
\frac{\partial h^{(l)}}{\partial W_l}$ . This structural coupling makes direct, centralized optimization infeasible — information must propagate along the network’s topology, forming a non-factorizable dependency graph that must be traversed both forward and backward during training.

It's worth noticing that most real-world systems, such as those we mentioned above, are decentralized and computationally irreducible, as solidly supported in Stephen Wolfram's book *A New Kind of Science*.

| | **Statistical Learning** | **Deep Learning** |
|----------------|--------------------------------|------------------------|
| **Decision-Making** | Centralized| Distributed |
| **Information Flow** | Global feedback; All parameters get informed simultaneously | Local feedback; Signals propagate layer-by-layer |
| **Parameter Dependence** | Computationally separable | Dynamically interdependent |
| **Inference Nature** | Evaluate explicit formula | Simulate the dynamics of the network |
| **Interpretability** | High — Parameters have global, often linear meaning | Low — Distributed representations |


## Signal Propagation: The Invisible Hand of Coordination

A natural question about decentralized systems is: How do these systems coordinate the behavior of their submodules? Well, as we showed above, in Deep Neural Networks it's via the propagation of gradients (gradient flow). In an ant colony, it's via the spread of pheromone. If you know some basic Economics, you must have heard the "Invisible Hand" coined by Adam Smith: price is the key to coordinating the agents in an economic system. These are all concrete cases of **signal propagation**.

Signal propagation lies at the heart of complex systems. Whether it’s a neurotransmitter spread, a gradient flowing, or a price adjusting, information moves locally through a web of interactions. These micro-level transmissions create macro-level order: cognition, learning, or equilibrium. 

What desiderata should such signal propagations satisfy? Among the most important ones are *signal fidelity* and *propagation efficiency*. It is similar to the case of a multi-node distributed model training where you need to avoid asynchrony and floating-point drift during All-Reduce operations, and minimize the propagation delay (This is not a complex system; but a good example for the convenience of understanding). In a competitive economic system, it would be intractable to transmit all information of other agents (such as marginal beliefs about value, cost, and scarcity of a commodity) to the target agent to derive its optimal behavior; instead, only the price dynamics $p(t)$ is transmitted to the target for reference -- a special case of a *Mean Field* where the information from other agents is encapsulated by some proxy for the ease of computing. While in a pretrained LLM where signal propagations happen between layers, these two desiderata trade off against each other, leading to quasi-orthogonality among semantically meaningful directions in residual streams; see [Section 3](https://interpretability.web.illinois.edu/tutorial-materials/#sec3) of my tutorial for more details. 

However, there's a vital difference between the training of Deep Neural Networks and the evolution of most other complex systems: the **driving force**. In Deep Neural Networks, the update dynamics of all modules is driven by a centralized, global loss $L(\theta)$; while in other complex systems, module updates are usually driven by heterogeneous, local utilities. For example, in economic systems, agents are regarded as rational: the goal of their behavior is to maximize their own utility, and there's no such "global utility" among all agents that plays a role. This is further abstracted and modeled as *Multi-Agent Reinforcement Learning (MARL)* problems, and Zhang et al. (2018) proved that a fully decentralized multi-agent reinforcement learning framework in which each agent updates its own policy based only on local rewards can reach collective optimality. 

The direct consequence of this difference is the lack of **competition** in a trained Deep Neural Network. Different modules in a model form a *production network* that contributes to a single final product — the next token, in which the relationship between modules is purely upstream-downstream collaboration without competition; see [Section 4](https://interpretability.web.illinois.edu/tutorial-materials/#sec4) of my tutorial for details. 

But what would the Deep Neural Networks benefit from inter-module competition if we can model it? Well, there have been many years of debates over the role that competition has in an economic system, and some conclusions have become consensus (see the [wikipedia page](https://en.wikipedia.org/wiki/Competition_(economics)#Role_in_market_success) for some brief intuition). 

|  | **Deep Neural Networks** | **Multi-Agent Reinforcement Learning (MARL) System** |
|-------------|----------------------------------|-------------------------------------------------------------|
| **Optimization Goal** | Single, global loss function $L(\theta)$ explicitly defined by designer | Each agent $i$ optimizes its own local reward  $R_i(s, a_i)$ |
| **Coordination Mechanism** | Implicit coordination via gradient coupling | Emergent coordination through communication, imitation, or shared environment dynamics |
| **System Structure** | Computationally distributed but functionally centralized | Fully decentralized |
| **Convergence Target** | Local minimum $\theta^* = \arg\min_{\theta \in \mathcal{N}(\theta^*)} L(\theta)$ | Nash equilibrium $(\pi_1^* , \pi_2^* , ... , \pi_n^*)$ |



## Decentralization is a Humanistic Stance ##

Back to the debates between Aristotle and Plato: In *Republic*, Plato viewed democracy as a degeneration of rational order and asserted the privilege of aristocracy. This was a systemic stance rooted in holism, where individuals are **passive receivers**. On the contrary, his student, Aristotle, believed in the value of humanism and individualism: he rejected the illusion of an ideal central optimizer designed to dictate value and to plan the distribution of resources, and instead affirmed that knowledge, meaning, and intelligence emerge from the interaction among **autonomous individuals**. Decentralization, in this sense, is not merely a pragmatic systemic design — it is a humanistic commitment. It reflects the belief that every human, though imperfect, is capable of reason, and that the wisdom of a community arises not from the dominance of one mind, but from the dialogue among many. This idea, or value in essence, was one of the major driving forces of social progress since the Renaissance when the monopoly of divine truth was dissolved, and the sources of knowledge, value and cognition were redistributed to human individuals. The question to take away from this is: would AI systems appreciate such individualism? 