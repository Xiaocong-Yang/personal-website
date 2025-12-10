---
title: 'Decentralized Computation: The Hidden Principle Behind Deep Learning'
date: 2025-11-05
author: 'Xiaocong Yang'
reviewer: 'Daniel Elliott and TDS editors'
permalink: /posts/2025/11/decentralization/
excerpt: 'This post explores how decentralized information processing plays a key role in Deep Neural Networks, and what is missing compared to other Complex Systems.'
description: "Explores how decentralized information processing shapes complex systems in biology, economics, and modern AI."
keywords: "decentralization, complex systems, AI interpretability, Xiaocong Yang"
tags:
  - Complex System
  - AI
  - Philosophy
references:
  - "Aristotle. (1998). Politics (C. D. C. Reeve, Trans.). Hackett Publishing Company."

  - "Plato. (2004). Republic (C. D. C. Reeve, Trans.). Hackett Publishing Company."

  - "Smith, A. (1776). An inquiry into the nature and causes of the wealth of nations. W. Strahan & T. Cadell."

  - "Arrow, K. J., & Debreu, G. (1954). Existence of an equilibrium for a competitive economy. Econometrica, 22(3), 265–290."

  - "Rozell, C. J., Johnson, D. H., Baraniuk, R. G., & Olshausen, B. A. (2008). Sparse coding via thresholding and local competition in neural circuits. Neural Computation, 20(10), 2526–2563."

  - "Sudhir, A. P., & Tran-Thanh, L. (2025). Market-based architectures in RL and beyond."

  - "Hebb, D. O. (1949). The organization of behavior: A neuropsychological theory. Wiley."

  - "Vapnik, V. N. (1998). Statistical learning theory. Wiley."

  - "Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep learning. MIT Press."

  - "Wolfram, S. (2002). A new kind of science. Wolfram Media."

  - "Smith, A. (1776). An inquiry into the nature and causes of the wealth of nations. W. Strahan and T. Cadell."

  - "Lasry, J.-M., & Lions, P.-L. (2007). Mean field games. Japanese Journal of Mathematics, 2(1), 229–260."

  - "Hayek, F. A. (1945). The use of knowledge in society. American Economic Review, 35(4), 519–530."
share: true
comments: true
---

Most breakthroughs in deep learning — from simple neural networks to large language models — are built upon a principle that is much older than AI itself: **decentralization**. Instead of relying on a powerful “central planner” coordinating and commanding the behaviors of other components, modern deep-learning-based AI models succeed because many simple units interact locally and collectively to produce intelligent global behaviors.

This article explains why decentralization is such a powerful design principle for modern AI models, by putting them in the context of general **Complex Systems**. If you have ever wondered:
- *Why internally chaotic neural networks perform much better than most statistical ML models that are analytically clear?*
- *Is it possible to establish a unified view among AI models and other natural intelligent systems (e.g. insect colonies, human brains, financial market, etc.)?*
- *How to borrow key features from natural intelligent systems to help design next-generation AI systems?*

… then the theories of Complex Systems where decentralization is a key property provides a surprisingly useful perspective.

## Decentralization in Natural Complex Systems ##

A Complex System can be very roughly defined as a system composed of many interacting parts, such that **the collective behavior of those parts together is more than the sum of their individual behaviors**. Across nature and human society, many of the most intelligent and adaptive systems belong to the Complex System family and operate without a central controller. Whether we look at human collectives, insect colonies, or mammalian brains, we consistently see the same phenomenon: complicated, coherent behavior emerging from simple units following local rules.

Human collectives provide one of the earliest documented examples. Aristotle observed that *“many individuals, though each imperfect, may collectively judge better than the best man alone”* (*Politics*, 1281a). Modern instances — from juries to prediction markets — confirm that decentralized aggregation can outperform centralized expertise. The natural world offers even more striking demonstrations: a single ant has almost no global knowledge, yet an ant colony can discover the shortest route to a food source or reorganize itself when the environment changes. The human brain represents this principle at its most sophisticated scale. Roughly 86 billion neurons operate with no master neuron in charge; each neuron simply responds to its inputs from very few other neurons. Still, memory, perception, and reasoning arise from distributed patterns of activity that no individual neuron encodes.

Across these domains, the common message is clear: **intelligence often emerges not from top-down control, but from bottom-up coordination**. And we'll see the principle provides a powerful lens for understanding not only natural systems but also the design and behavior of modern AI architectures.

## AI’s Journey: From Centralized Learning to Distributed Intelligence ##

One of the most striking shifts in AI world in the past years, is the transition from a mostly centralized, hand-designed approach to a more distributed, self-organizing approach. Early statistical learning methods often resembled a top-down design: human experts would carefully craft features or rules, and algorithms would then optimize a single model, usually with *strong structural assumptions*, against a small set of data. Whereas today’s most successful AI systems – Deep Neural Networks – look very different. They involve lots of simple computational units (“artificial neurons”) connected in networks, learning collaboratively from a large amount of data with minimal human intervention in feature and structural design. In a sense, AI has moved from a paradigm of “let’s have one smart algorithm figure it all out” to “let’s have many simple units learn together, and let the solution emerge.”

### Ensemble Learning ###

One bridge between traditional statistical learning and modern deep learning approaches in AI is the rise of ensemble learning. Ensemble methods combine the predictions of multiple models (“base learners”) to make a final decision. Instead of relying on a single classifier or regressor, we train a collection of models and then aggregate their outputs – for example, by voting or averaging. The idea is straightforward: even if each individual model is imperfect, their errors may be uncorrelated and can be cancelled. Ensemble algorithms like Random Forest and XGBoost have leveraged this insight to win many machine learning competitions since the late 2000s, and they remain competitive in some areas even today.

### Statistical Learning v.s. Deep Learning: A Battle between Centralization and Decentralization ###

Now let’s look at both sides of this bridge. Traditional statistical learning theory, as formalized by Vapnik, Fisher, and others, explicitly targets at **analytical tractability** — both in the model and in its optimization. In these models, parameters are analytically separable: they interact directly with the loss function, not through one another; models such as Linear Regression, SVM, or LDA admit closed-form parameter estimators that can be written down in the form of $ \widehat{\theta} = \arg\min_{\theta} L(\theta) $. Even when closed forms are not available, as in Logistic Regression or CRF, the optimization usually remains convex and thus theoretically well-characterized.

In contrast, Deep Neural Networks admit no analytically tractable relationship between input and output. The mapping from input to output is a deep composition of nonlinear transformations where parameters are sequentially coupled; to understand the model’s behavior, one must perform a *full forward simulation* of the entire network. In the meantime, the learning dynamics of such networks are governed by iterative, non-convex optimization processes that lack analytical guarantees. In this dual sense, deep networks exhibit **computational irreducibility** — their behavior can only be revealed through computation itself, not derived through analytical expressions.

If we explore the root cause of the difference above, you'll find it's due to the model structures -- as we might well expect to see. In statistical learning methods, the computational graphs are single-layer: $\theta \longrightarrow f(x;\theta) \longrightarrow L$ without any intermediate variables, and a "central planner" (the optimizer) passes the global information directly to each parameter. However, in Deep Neural Networks, parameters are organized in layers which are stacked on top of each other. For example, an MLP network without bias terms can be expressed as $y = f_L(W_L f_{L-1}(W_{L-1} \dots f_1(W_1 x)))$ where each $W_l$ affects the next layer’s activation. When calculating the gradient to update parameters $\theta = \lbrace W_i \rbrace_{i=1}^L$, it is inevitable that you'll rely on **backpropagation** to update parameters layer by layer:

$$ \nabla_{W_l} L = \frac{\partial L}{\partial h^{(L)}} \frac{\partial h^{(L)}}{\partial h^{(L-1)}} \dots \frac{\partial h^{(l)}}{\partial W_l} $$

This structural coupling makes direct, centralized optimization infeasible — **information must propagate along the network’s topology, forming a non-factorizable dependency graph that must be traversed both forward and backward during training**.

It's worth noticing that most real-world Complex Systems, such as those we mentioned above, are decentralized and computationally irreducible, as solidly supported in Stephen Wolfram's book *A New Kind of Science*.

| |Statistical Learning | Deep Learning |
|----------------------|---------------|
| **Decision-Making** | Centralized | Distributed |
| **Information Flow** | Global feedback; all parameters get informed simultaneously | Local feedback; signals propagate layer-by-layer |
| **Parameter Dependence** | Computationally separable | Dynamically interdependent |
| **Inference Nature** | Evaluate explicit formula | Simulate the dynamics of the network |
| **Interpretability** | High — parameters have global, often linear meaning | Low — distributed representations |

## Signal Propagation: The Invisible Hand of Coordination ##

A natural question about decentralized systems is: how do these systems coordinate the behavior of their inner components? Well, as we showed above, in Deep Neural Networks it’s via the propagation of gradients (gradient flow). In an ant colony, it’s via the spread of pheromone. And you must have heard the famous “*Invisible Hand*” coined by Adam Smith: price is the key to coordinating the agents in an economic system. These are all specific cases of **signal propagation**.

Signal propagation lies at the heart of Complex Systems. **A signal proxy compress the landscape of the system, and is taken by each agent in this system to determine its optimal behavior**. Take the competitive economic system as an example. In such an economic system, the price dynamics $p(t)$ of a commodity is used as the signal proxy and transmitted to the agents in this system to coordinate their behaviors. The price dynamics $p(t)$ *compresses and encapsulates key information of other agents*, such as their marginal believes of value and cost on the commodity, to impact the decision of each agent. Compared to spreading the full information of all agents, there are two major advantages:

- **Better Propagation Efficiency.** Instead of transmitting high-dimensional information variable — such as each agent’s willingness-to-pay function — only a scalar is propagated at a time. This drastic reduction in information bandwidth makes decentralized convergence to a market-clearing equilibrium feasible and stable.
- **Proper Signal Fidelity.** Price provides a proxy with a just-right fidelity level of the raw information that could lead to a *Pareto Optimum* state at the system level in a competitive market, formalized and proven in the [foundational work](https://www.jstor.org/stable/1907353?seq=1) by Arrow & Debreu (1954). The magic behind is that, with this public signal being the *only* one available, each agent regards itself as a **price-taker** at the current price level, not an influencer, so that there's no room for *strategic behavior*.

It's surprising that access to full information of all agents won't result in a better state for the market system, even without the consideration of propagation efficiency. It introduces **strategic coupling**: each agent’s optimal action depends on others’ actions, which is observable under full information. From the perspective of each agent, it is no longer solving an *optimization problem* with the form of

$$\max_{a_i \in A_i(p, e_i)} \; u_i(a_i), \qquad A_i(p, e_i) = \{ a_i : Cost(a_i, p) \le e_i \}$$

Instead, its behavior is guided by the following *strategy*:

$$\max_{a_i \in A_i(e_i)} u_i(a_i, a_{-i}),\qquad A_i(e_i) = \{ a_i : \text{Feasible}(a_i; e_i)\}$$

here $a_i$ and $e_i$ are action and endowment of agent $i$ respectively, $a_{-i}$ are the actions of other agents, $p$ is the price of a commodity independent of the action of any single agent, and $u_i$ is the utility of agent $i$ to be maximized. With full information accessible, each agent is able to speculate the behaviors of other agents and so $a_{-i}$ enters the utility of agent $i$, creating strategic coupling. The economic system, therefore, eventually converges to a *Nash equilibrium* and suffers from inefficiencies inherent in non-cooperative behaviors (e.g. The Prisoner's dilemma).

Technically, the signal propagation mechanism in markets is structurally equivalent to a **Mean-Field model**. Its steady-state corresponds to a Mean-Field equilibrium, and the framework can be interpreted as a special instance of a Mean-Field Game. Many Complex Systems in nature can be described with a specific Mean-Field model, such as *Volume Transmission* in brains and *Pheromone Field Model* in insect colonies.

## The Missing Part in Neural Networks ##

Similar to the above areas, the dynamics of neural network training are well characterized by mean field models in many previous works. However, there’s a vital difference between the training of neural networks and the evolution of most other Complex Systems: **the structure of objectives**. In Deep Neural Networks, the update dynamics of all modules is driven by a centralized, global loss $L(\theta)$; while in other complex systems, system updates are usually driven by *heterogeneous, local* objectives. For example, in economic systems, agents change their behaviors to maximize their own utility functions, and there’s no such “global utility” covering all agents that plays a role.

The direct consequence of this difference is the missing of **competition** in a trained Deep Neural Network. Different modules in a model form a *production network* that contributes to a single final product — the next token, in which the relationship between different modules is purely upstream-downstream collaboration (proposed in [Market-based Architectures in RL and Beyond](https://arxiv.org/abs/2503.05828); refer to [Section 4](https://interpretability.web.illinois.edu/tutorial-materials/#sec4) of my lecture slides for a simplified derivation). However, as we know, competitive pressures induce **functional specialization** for agents in an economic system, which further gives the potential for a *Pareto Improvement* for the system via well-functioning exchanges. Similar logics has also been found when manually introducing competition in neural networks: **a sparsity penalty induces local competition among units for being activated, which suppresses redundant activations, drives functional specialization, and empirically improves representation quality**, as demonstrated in Rozell et al. (2008) where competitive LCAs produce more accurate representations than non-competitive baselines. *Intra-modular competition modeling, in this sense, would be an important direction for the design of next-generation AI systems*.

## Decentralization Contributes to AI Democracy ##

At the end of this article, one more thing to talk about is the ethical meaning of decentralization. Decentralized structure of Deep Neural Networks provides a technical foundation for collaboration between models. When intelligence is distributed across many components, it becomes possible to assemble, merge or coordinate different models to build a more powerful system. Such an architecture naturally supports a more democratic form of AI, where ideally no single model monopolizes influence. This is surprisingly consistent with the belief from Aristotle that "*every human, though imperfect, is capable of reason*", though the "humans" here are built from silicon.