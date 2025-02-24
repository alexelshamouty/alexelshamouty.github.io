---
title: "Platform Engineering Antipatterns"
date: 2025-02-24T17:10:36+01:00
draft: false 
---

# Platform Engineering Antipatterns

You are probably already on your path to implementing platform engineering in your company. Maybe it was triggered by a major cloud transformation or a significant overhaul of your software development practices. Perhaps you embarked on this journey because you’ve been struggling with DevOps or SRE practices. You are thinking platform engineering is loved, cherished and promoted by the industry, so, there must be something to it?

One thing is for sure: you started this path because you want a better and more efficient model for your organization—whether to speed up development or reduce costs. Who wouldn’t want that?

---

## What Do You Mean by a Platform?

In this article, we discuss platforms through the lens of cloud modernization. Our focus is mostly on internal developer platforms. Therefore, when we refer to a platform in this article, we mean an **internal developer platform**.

---

## Why This Article?

Despite good intentions and valuable promises, platforms often fail due to systematic issues and unforeseen challenges. They promise to solve many problems: reduce complexity, increase innovation, and streamline operations. But they can fall short in addressing broader contextual needs that go beyond technology.

This article aims to provide mental models that help you navigate these complexities and guardrail your strategy from the start.

---

## But What Is an Antipattern?

In this article, we use the term *antipattern* in the same manner as Donella H. Meadows describes it in her book *Thinking in Systems*:

> "An antipattern can be understood as a systemic trap or archetype. A recurring dysfunctional pattern in complex systems that leads to undesirable outcomes."  

I have never met anyone in my career—or in life for that matter—who set out to execute a strategy knowing it would fail and lead to dysfunctional outcomes. Yet, those outcomes occur!

In this article we will highlight areas to be cautious about and questions you might face when implementing and designing your platform strategy.

These antipatterns arise within specific contexts rather than being universal. They emerge unintentionally, as a consequence of the complex nature of technological transformation. If you observe the symptoms we outline below, you have likely encountered an antipattern.

*The antipatterns overlap, and that is expected. Systematic problems are often connected, yet they manifest differently depending on the context.*

---

## 1. A Platform for Everything

### Context

A well-intended approach by platform teams is to create a single platform that covers **every aspect** of the software development lifecycle—with no escape hatches, only an opinionated and heavily guarded path. This platform attempts to unify development, deployment, observability, security, optimization, and governance. This antipattern is common during transformation times.

### Symptoms

- Platform teams introduce rigid prioritization techniques to manage the flux of demand.
- A lack of cohesion between platform components leads to excessive documentation, approvals, and meetings to maintain harmony.
- Platform teams continuously try to introduce a common denominator even when it is not needed.
- New tools and capabilities are frequently added with low adoption rates (feature creep).

### Results

**Innovation Slows Down:**

Innovation is inherently unstructured and often lacks clear requirements. Innovating teams need speed and sometimes access to less mature or niche technologies. If your platform covers a huge surface area, teams will tend to apply strict prioritization and standardization to maintain order and stability—clashing with the need for rapid, exploratory innovation.

**Increased Platform Complexity:**

Platform teams, driven by a broad mission, often fall into the **Build Trap** by rapidly adding features in response to innovation team demands. This reactive approach prioritizes output over long-term platform stability, leading to increased complexity and unchecked technical debt. Instead of focusing on measurable outcomes and sustainable improvements, teams can become trapped in an endless cycle of feature delivery, which diminishes the platform’s effectiveness.

*Be cautious with this antipattern, especially if innovation is a priority. Your platform may end up serving only the biggest stakeholders, leaving innovators in the cold—or over time, it may serve every purpose, exponentially increasing your maintenance demands. And, are you really saving costs?*

### Analogy

**Slowing Innovation:**

Imagine that every time you want to go skiing, you have only one safe, governed path to follow. Without the option to safely explore new routes, you might either search for a new resort that offers adventure or venture out on your own without safety nets—an outcome that could be either exciting or disastrous.

**Increased Complexity:**

Think of it as constantly battling against a cloud service provider. Is that really the challenge you want to face?

---

## 2. Product Everything

### Context

Another well-intended strategy is to decompose all developers’ requirements into components (or “capabilities” in product lingo) and treat every platform component as a managed product. Over time, the granularity of these products increases—even the smallest non-functional requirements become separate products. This approach demands more time from product owners or even additional product owners to manage these “products” effectively. This antipattern is typical in organizations that are still learning platform engineering and adopting product-thinking methodologies.

### Symptoms

- Solutions are created for problems that were never concerns before—even if you just came from a private cloud environment.
- Platform teams complain about a lack of vision and unclear roles.
- Teams become fragmented, working on small, non-functional requirement “products.”
- Teams seek control over well-standardized, cloud-managed services with “add value” propositions.
- Platform teams obsess over abstracting away complexity from developers, while developers complain about being isolated from cloud technologies.

### Results

**Increased Waste:**

Teams develop solutions for problems that either do not exist or have already been solved. These solutions often take the form of customized components layered on top of cloud-managed services—purporting to add value but potentially introducing unforeseen issues.

These issues not only affect platform teams (who must maintain these components) but also impact stakeholders and platform users. The divergence between cloud-standardized models and your custom model can paradoxically increase the very fragmentation your platform initiative sought to reduce.

*Be cautious if your goal is to provide the most impactful and minimally necessary platform for developers. This antipattern will increase friction and slow down your strategic goals. Does your platform really need to abstract all technologies behind it?*

### Analogy

Imagine opening a bakery with the goal of delivering the best customer experience. To ensure complete quality control, you decide to manage every aspect of service—even generating your own electricity and designing custom microwaves so customers can reheat pastries perfectly at home. However, your electricity company delivers a unique voltage, and your custom microwaves work only when connected to your own optimized electrical supply.

While you may have optimized your internal value chain, you could be complicating your stakeholders’ experience with unnecessary, overly specific optimizations. Local metrics might suggest customer happiness, but the customer experience could tell a different story.

---

## Shape

*(*Note: "Shape" appears as a standalone header in the original text without additional content. It may indicate an intended focus on the structure or evolution of your platform. Consider reflecting on how your platform might naturally evolve toward a simpler, more efficient model.*)*

---

## Conclusion

Platform engineering is not doomed, but it is challenging. It drastically changes the way your organization works—for the better! However, success requires a systematic approach to change.

The symptoms reveal the antipatterns. Identify these symptoms and correlate them with your strategy. If you see a strong correlation, you’ve found the antipattern, and you’ll have a clearer idea of the outcomes it may bring.

Overgeneralization leads to complexity. To paraphrase Bjarne Stroustrup:

> "Within C++, there is a much smaller and cleaner language struggling to get out."

Likewise, within your complex platform, there is a smaller and cleaner platform waiting to emerge.

Sequencing your platform architecture is just as important as defining the target architecture. Starting with a rigid target assumes you know all the requirements upfront. Instead, leave room for maneuverability.

We have observed these antipatterns—and more—while assisting organizations in executing and developing platform strategies. Connecting platform layers from stakeholders to engineering teams is difficult and raises countless unforeseen questions—from “How do we keep on innovating?” to “But who’s going to be on-call for all of this?”

A successful platform strategy requires understanding your environment and having deep expertise in sequencing a dynamic strategy with strong, clear value propositions that connect the dots between **People, Work, Structure, and Technology**.
