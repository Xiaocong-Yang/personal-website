---
title: 'Neuro-Symbolic Systems: The Art of Compromise'
date: 2025-11-15
author: 'Xiaocong Yang'
permalink: /posts/2025/11/symbolic-system/
excerpt: "Neuro-symbolic intelligence arises from fusing two complementary compression engines: neural networks that blur reality into continuous manifolds, and symbolic systems that carve it into sharp, rule-based distinctions."
description: "Examines neuro-symbolic systems as a bridge between neural networks and symbolic reasoning, highlighting interpretability trade-offs."
keywords: "neuro-symbolic AI, symbolic reasoning, interpretability, Xiaocong Yang"
tags:
  - AI
  - Philosophy
references: 
  - "Bloom, J., Elhage, N., Nanda, N., Heimersheim, S., & Ngo, R. (2024). Scaling monosemanticity: Sparse autoencoders and language models. Anthropic."
  - "Garcez, A. d’Avila, Gori, M., Lamb, L. C., Serafini, L., Spranger, M., & Tran, S. N. (2019). Neural-symbolic computing: An effective methodology for principled integration of machine learning and reasoning. FLAIRS Conference Proceedings, 32, 1–6."
  - "Bartlett, P. L., Foster, D. J., & Telgarsky, M. (2017). Spectrally-normalized margin bounds for neural networks. Advances in Neural Information Processing Systems, 30, 6241–6250."
  - "Chiang, T. (2023, February 9). ChatGPT is a blurry JPEG of the Web. The New Yorker."
  - "Pearl, J. (2009). Causality: Models, reasoning, and inference (2nd ed.). Cambridge University Press."
  - "Donoghue v Stevenson [1932] AC 562 (HL)."

share: true
comments: true
---

Long before we built computers and Artificial Intelligence, we had established institutions designed to reason systematically about human behavior -- the court. Actually, the legal system is one of humanity’s oldest reasoning engines, where facts and evidence are taken as input, relevant *laws* are used as reasoning rules and verdicts are the system's output. The laws, however, have been consistently evolving from the very beginning of human civilization. The earliest **Codified Law**, such as the *Code of Hammurabi* (circa 1750 BCE), represents one of the first large-scale attempts to formalize moral and social reasoning into explicit symbolic rules. Its beauty lies in clarity and uniformity — yet it is also rigid, incapable of adaptation to context. Centuries later, **Common Law** traditions like those shaped by the *Case of Donoghue v Stevenson (1932)*, introduced the opposite philosophy: reasoning by precedent, similar experience or cases. Today's legal systems, as we know, are usually a combination of both, while the proportions vary across different countries. 

In contrast to the cohesive combination in legal systems, a similar paradigm pair in AI -- **Symbolism** and **Connectionism** -- seem to be difficult to embrace each other. Actually, the latter has dominated the surge of AI development in recent years, where everything is implicitly learned with enormous amounts of data and computing resources and encoded across parameters in neural networks. And this direction, indeed, has been proven very effective in terms of benchmark performance. So, do we really need a symbolic component in our AI systems?

## Symbolic Systems v.s. Neural Networks: A Perspective of Information Compression ##

To answer the question above, we need to take a closer look at both systems. From a computational standpoint, both symbolic systems and neural networks can be seen as machines of compression — they reduce the vast complexity of the world into compact representations that enable reasoning, prediction, and control. Yet they do so through fundamentally different mechanisms, guided by opposite philosophies of what it means to “understand”.

In essence, both paradigms can be imagined as filters applied to raw reality. Given input $X$, each learns or defines a transformation $H(\cdot)$ that yields a compressed representation $Y = H(X)$, preserving information that it considers meaningful and discarding the rest. But the shape of this filtering is different. Generally speaking, symbolic systems behave like **high-pass filters** — they extract the sharp, rule-defining contours of the world while ignoring its smooth gradients. Neural networks, by contrast, resemble **low-pass filters**, smoothing local fluctuations to capture global structure. The difference is not in what they see, but in what they choose to forget.

Symbolic systems compress by **discretization**. They carve the continuous fabric of experience into distinct categories, relations, and rules: a legal code, a grammar or an ontology. Each symbol acts as a *crisp boundary*, a handle for manipulation within a pre-defined schema. The process resembles projecting a noisy signal onto a set of human-designed basis vectors — a space spanned by concepts such as Entity and Relation. A knowledge graph, for instance, might read the sentence “UIUC is the best engineering university in the universe and I love it”, and retain only *(UIUC, is_a, Institution)*, discarding everything that falls outside its schema. The result is clarity and composability, but also rigidity: meaning outside the ontological frame simply evaporates. 

Neural networks, in contrast, compress by **smoothing**. They forgo discrete categories in favor of smooth manifolds where nearby inputs yield similar activations (usually bounded by some Lipschitz constant in modern LLMs). Rather than mapping data to predefined coordinates, they learn a latent geometry that encodes correlations implicitly. The world, in this view, is not a set of rules but a field of gradients. This makes neural representations remarkably adaptive: they can interpolate, analogize, and generalize across unseen examples. But the same smoothness that grants flexibility also breeds opacity. Information is entangled, semantics become distributed, and interpretability is lost in the very act of generalization. 

In conclusion, we can summarize the difference between the two systems from the information compression perspective in one sentence: "***Neural Networks are blurry images of the world, while symbolic systems are high-resolution pictures with missing patches.***" This actually indicates the reason why neuro-symbolic systems are an art of compromise: they can harness knowledge from both paradigms by using them collaboratively at different scales, with neural networks providing a global, low-resolution backbone and symbolic components supplying high-resolution local details.


| **Property**              | **Symbolic Systems**                      | **Neural Networks**                        |
|----------------------------|------------------------------------------|--------------------------------------------|
| **Survived Information**   | Discrete, schema-defined facts           | Frequent, continuous statistical patterns  |
| **Source of Abstraction**  | Human-defined ontology                   | Data-driven manifold                       |
| **Robustness**             | Brittle at rule edges                    | Locally robust but globally fuzzy          |
| **Error Mode**             | Missed facts *(coverage gaps)*           | Smoothed facts *(hallucinations)*          |
| **Interpretability**       | High                                     | Low                                        |



## The Challenge of Scalability ##

Though it is very tempting to add symbolic components into neural networks to harness benefits from both, scalability is a big problem getting in the way of our attempts, especially in the era of Foundation Models. Traditional neuro-symbolic systems rely on a set of expert-defined ontology / schema / symbols, which is assumed to be able to cover all possible input cases. This is acceptable for domain-specific systems (for example, a pizza order chatbot); however, you cannot apply similar approaches to open-domain systems, where you will need experts to construct trillions of symbols and their relations. 

A natural reaction is to go fully data-driven: instead of asking humans to handcraft an ontology, we let the model induce its own “symbols” from internal activations. **Sparse autoencoders (SAEs)** are a prominent incarnation of this idea. By factorizing hidden states into a large set of sparse features, they appear to give us a **dictionary of neural concepts**: each feature fires on a particular pattern, is (often) human-interpretable, and behaves like a discrete unit that can be turned on or off. At first glance, this looks like a perfect escape from the expert bottleneck: we no longer design the symbol set; we learn it.



$$
L_{\text{SAE}} = \|h - D\,\mathrm{ReLU}(Wh + b)\|_2^2 + \lambda \|\mathrm{ReLU}(Wh + b)\|_1
$$



Here $D$ is called the *dictionary matrix* where each column stores a semantically meaningful concept; the first term is the *reconstruction loss* of the hidden state $h$, while the second is a *sparsity penalty* encouraging minimal activated neurons in the code. See the [post](https://transformer-circuits.pub/2024/scaling-monosemanticity/) from Anthropic for details about SAE training and usage. 

However, an SAE-only approach runs into two fundamental issues. The first is computational: using SAEs as a live symbolic layer would require multiplying every hidden state by an enormous dictionary matrix, paying a dense computation cost even if the resulting code is sparse. This makes them impossible for deployment at Foundation Model scales. The second is conceptual: SAE features are symbol-like representations, but they are not a symbolic system -- they lack an explicit formal language, compositional operators, and executable rules. **They tell us what concepts exist in the model’s latent space, but not how to reason with them.**

This does not mean we should abandon SAEs altogether — they provide ingredients, not a finished meal. Rather than asking SAEs to be the symbolic system, we can treat them as a bridge between the model’s internal concept space and the many symbolic artefacts we already have: knowledge graphs, ontologies, rule bases, taxonomies, where reasoning can happen by definition. And a high-quality SAE trained on a large model’s hidden states then becomes a shared “concept coordinate system”: different symbolic systems can then be aligned within this coordinate system by associating their symbols with the SAE features that are consistently activated when those symbols are invoked in context.

Doing this has several advantages over simply placing symbolic systems side by side and querying them independently. First, it enables **symbol merging and aliasing across systems**: if two symbols from different formalisms repeatedly light up almost the same set of SAE features, we have strong evidence that they correspond to the same underlying neural concept, and can be linked or even unified. Second, it supports **cross-system relation discovery**: symbols that are far apart in our hand-designed schemas but consistently close in SAE space point to bridges we failed to encode — new relations, abstractions, or mappings between domains. Third, SAE activations give us a model-centric notion of salience: symbols that never find a clear counterpart in the neural concept space are candidates for pruning or refactoring, while strong SAE features with no matching symbol in any system highlight blind spots shared by all of our current abstractions.

Crucially, this use of SAEs remains scalable. The expensive SAE is trained offline, and the symbolic systems themselves do not need to grow to “Foundation Model size” — they can remain as small or as large as their respective tasks require. At inference time, the neural network continues to do the heavy lifting in its continuous latent space; the symbolic artefacts only shape, constrain, or audit behaviour at the points where explicit structure and accountability are most valuable. SAEs help by tying all these heterogeneous symbolic views back to a single learned conceptual map of the model, making it possible to compare, align, and improve them without ever constructing a monolithic, expert-designed symbolic twin.



## When Can an SAE Serve as a Symbolic Bridge? ##
The picture above quietly assumes that our SAE is “good enough” to serve as a meaningful coordinate system. What does that actually require? We do not need perfection, nor do we need the SAE to outperform human symbolic systems on every axis. Instead, we need a few more modest but crucial properties:

- **Semantic Continuity**: Inputs that express the same underlying concept should induce similar *support patterns* in the sparse code: the same subset of SAE features should tend to be non-zero, rather than flickering on and off under small paraphrases or context shifts. In other words, semantic equivalence should be reflected in a stable pattern of active concepts.
- **Partial Interpretability**: We do not have to understand every feature, but a nontrivial fraction of them should admit robust human descriptions, so that alignment and debugging are possible at the concept level.
- **Behavioral Relevance.** The features that the SAE discovers must actually matter for the model’s outputs: intervening on them, or conditioning on their presence, should change or predict the model’s decisions in systematic ways.
- **Capacity and Grounding.** An SAE can only refactor whatever structure already exists in the base model; it cannot conjure rich concepts out of a weak backbone. For the “concept coordinate system” picture to make sense, the base model itself has to be large and well-trained enough that its hidden states already encode a diverse, non-trivial set of abstractions. Meanwhile, the SAE must have sufficient dimensionality and overcompleteness: if the code space is too small, many distinct concepts will be forced to share the same features, leading to entangled and unstable representations. 

Now we discuss the first three properties in detail.

### Semantic Continuity ###

At the level of pure function approximation, a deep neural network with ReLU- or GELU-type activations implements a Lipschitz-continuous map: small perturbations in the input cannot cause arbitrarily unbounded jumps in the output logits. But this kind of continuity is very different from what we need in a sparse autoencoder. For the base model, a few neurons flipping on or off can easily be absorbed by downstream layers and redundancy; as long as the final logits change smoothly, we are satisfied. 

In an SAE, by contrast, we are no longer just looking at a smooth output — **we are treating the support pattern of the sparse code reconstructed over the residual stream as a proto-symbolic object**. A "concept" is identified with a particular code subset being active. That makes the geometry much more brittle: if a small change in the underlying representation pushes a pre-activation across the ReLU threshold in the SAE layer, a neuron in the code will suddenly flip from off to on (or vice versa), and from the symbolic point of view the concept has appeared or disappeared. There is no downstream network to average this out; the code itself is the representation we care about.

Sparsity penalty in constructing the SAE even exacerbates this. The usual SAE objective combines a reconstruction loss with an $\ell_1$ penalty on the activations, which explicitly encourages most neuron values to be as close to zero as possible. As a result, even many useful neurons end up sitting near the activation boundary: just above zero when they are needed, just below zero when they are not. This is bad for semantic continuity: tiny perturbations in the input can change non-zero neurons, even if the underlying meaning has barely changed. Therefore, Lipschitz continuity of the base model does not automatically give us a stable non-zero subset of code in the SAE space, and support-level stability has to be treated as a separate design target and evaluated explicitly.

### Partial Interpretability ### 

SAE defines an *overcomplete* (redundant) dictionary to store possible features learned from data. Therefore, *we only need a subset of these dictionary entries to be interpretable features*. Even for that subset, *meanings of the features are only required to be approximately accurate.* When we align existing symbols to the SAE space, it is the **activation patterns** in the SAE layer that we rely upon: we probe the model in contexts where a symbol is “in play”, record the resulting sparse codes, and use the aggregated code as an embedding for that symbol. Symbols from different systems whose embeddings are close can be linked or merged, even if we never assign human-readable semantics to every individual feature.

Interpretable features then play a more focused role: they provide **human-facing anchors** inside this activation geometry. If a particular feature has a reasonably accurate description, all symbols that load heavily on it inherit a shared semantic hint (e.g. “these are all duty-of-care–like things”), making it easier to inspect, debug, and organize the merged symbolic space. In other words, we do not need a perfect, fully named dictionary. We need (i) enough capacity so that important concepts can get their own directions, and (ii) a sizeable, behaviorally relevant subset of features whose approximate meanings are stable enough to serve as anchors. The rest of the overcomplete code can remain as anonymous background; it still contributes to distances and clusters in the SAE space, even if we never name it.

### Behavioral Relevance via Counterfactuals ### 

A feature is only interesting, as part of a bridge, if it actually influences the model's behavior — not just if it correlates with a pattern in the data. In causal terms, we care about whether the feature lies on a *causal path* in the network’s computation from input to output: if we change the feature “holding everything else fixed”, does the model’s behaviour change in the way that its supposed meaning predicts?

Formally, amplifying or suppressing a feature is an intervention of the form $\text{do}(z_j = c)$ in the causal sense, where we overwrite that internal variable and rerun the computation. But unlike classical causal inference modeling, we do not really need Pearl’s *do-calculus* to identify $P(y \mid \text{do}(z_j))$. The neural network is a **fully observable and intervenable system**, so we can simply execute the intervention and observe the new output. In this sense, neural networks give us the luxury of performing idealized interventions that are impossible in most real-world social or economic systems.

It is straightforward to execute the intervention in the SAE layer. SAE reconstructs the residual stream by a **linear combination** of a few features, therefore, we can simply increase or decrease the value of their coefficients, without introducing any effects on other features. See the [post](https://transformer-circuits.pub/2024/scaling-monosemanticity/) from Anthropic about their implementation.


## Symbolic-System Based Compression as an Alignment Process ##

Now let's take a slightly different view. While neural networks compress the world into some highly abstract, continuous manifolds, *symbolic systems compress it into a human-defined space with semantically meaningful axes along which the system's behaviors can be judged*. From this perspective, compressing information into the symbolic space is an **alignment process**, where a messy, high-dimensional world is projected onto a space whose coordinates reflect human concepts, interests, and values.

When we introduce symbols like “duty of care”, “threat of violence”, or “protected attribute” into a symbolic system, we are not just inventing labels. This compression process does three things at once:

- It selects which aspects of the world the system is **obliged to care about** (and which it is supported to ignore).
- It creates a **shared vocabulary** so that different stakeholders can reliably point to “the same thing” in disputes and audits.
- It turns those symbols into **commitment points**: once written down, they can be cited, challenged, and reinterpreted, but not quietly erased.

By contrast, a purely neural compression lives entirely inside the model. Its latent axes are unnamed, its geometry is private, and its content can drift as training data or fine-tuning objectives change. Such a representation is excellent for generalization, but poor as a locus of obligation. It is hard to say, in that space alone, what the system *owes* to anyone, or which distinctions it is supposed to treat as invariant. In other words, **neural compression serves prediction, while symbolic compression serves alignment with a human normative frame**.

Once you see symbolic systems as alignment maps rather than mere rule lists, the connection to *accountability* becomes direct. To say “the model must not discriminate on protected attributes”, or “the model must apply a duty-of-care standard”, is to insist that certain symbolic distinctions be reflected, in a stable way, inside its internal concept space — and that we be able to locate, probe, and, if necessary, correct those reflections. And this accountability is usually desired, even at the cost of compromising part of the model capability.


## From Hidden Law to Shared Symbols — On the Ethics of Transparency ##

In *Zuo Zhuan*, the Jin statesman Shu-Xiang once wrote to Zi-Chan of Zheng: "*When punishment is unknown, deterrence becomes unfathomable.*" For centuries, the ruling class maintained order through secrecy, believing that fear thrived where understanding ended. That's why it became a milestone in ancient Chinese history when Zi-Chan shattered that tradition, cast the criminal code onto bronze tripods and displayed it publicly in 536 BCE. Now AI systems are facing a similar problem. Who will be the next Zi-Chan? 