---
permalink: /
title: "Man Is a Reed That Thinks. So Should AI."
author_profile: true
redirect_from: 
  - /about/
  - /about.html
description: "Homepage for Xiaocong Yang, CS PhD student at UIUC focusing on AI interpretability and symbolic reasoning."
keywords: "Xiaocong Yang, AI interpretability, symbolic reasoning, UIUC"
---

<style>
.page {
  position: relative;
  min-height: 100vh;
}

.page,
.page__inner-wrap,
.page__content {
  background: transparent !important;
  box-shadow: none !important;
}

.page::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('{{ site.baseurl }}/images/reed.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0.12;
  z-index: -2;
}

.page__content {
  position: relative;
  padding: 2em;
  z-index: 1;
}

/* Light mode styling */
.page__content h2,
.page__content p,
.page__content li,
.page__content blockquote,
.page__content strong,
.page__content a {
  color: #222;
}

/* Dark mode styling */
html[data-theme="dark"] .page__content h2,
html[data-theme="dark"] .page__content p,
html[data-theme="dark"] .page__content li,
html[data-theme="dark"] .page__content blockquote,
html[data-theme="dark"] .page__content strong,
html[data-theme="dark"] .page__content a {
  color: #fff;
}
</style>

> "Man is but a reed, the weakest thing in nature; but he is a thinking reed." — Blaise Pascal

Humanity's strength lies in the ability to think, reflect, and understand.
As Artificial Intelligence becomes increasingly capable of processing vast amounts of information, Pascal's words remain ever relevant:
**True intelligence should not be defined solely by instrumental capacity, but also by the capacity for philosophical reflection and introspective reasoning.**

My research at [AI Interpretability @ Illinois](https://interpretability.web.illinois.edu/) extends this idea toward machine intelligence by exploring how Mechanistic Interpretability, Modularity, and Biological Plausibility can inspire the design of next-generation AI systems that go beyond pattern recognition and behave as a "thinking reed":

- **Structural Interpretability of AI Models:** I study the organization of knowledge and computational mechanisms within AI models, borrowing core principles from biological intelligence—such as modularity, functional specialization, and sparse activation—to design architectures whose computation can be understood and regulated with brain-like efficiency.
- **Behavioral Interpretability of AI Agents:** I work on autonomous and self-evolving agents that learn on the fly through continual interaction with changing environments. A self-reflective, continuously updated memory module allows the agent to integrate past experiences, representing a key step toward "System-2 thinking"; while modeling collaboration and competition in multi-agent frameworks can induce Pareto-efficient systems that resemble competitive economic markets.

## Availability

If you'd like to reserve a time to discuss, please choose a slot below.

{% if site.calendar_booking_url %}
<iframe
  src="{{ site.calendar_booking_url }}"
  style="border:0;width:100%;min-height:720px;"
  frameborder="0"
  scrolling="no"
  title="Appointment Schedule"
></iframe>
{% else %}
<p>Please set <code>calendar_booking_url</code> in <code>/_config.yml</code> to your Google Appointment Schedules booking link.</p>
{% endif %}
