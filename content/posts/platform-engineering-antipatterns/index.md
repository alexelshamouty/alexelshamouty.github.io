---
authors: ["Alex Elshamouty"]
date: "2025-02-25"
title: "Platform Engineering Antipatterns"
description: "Platform engineering is taking over the world! Or... not?"
summary: "A deep dive into common antipatterns in Platform Engineering, including the 'Platform for Everything' and 'Product Everything' approaches, and how to avoid these systemic traps."
headerimage: "deepwaterdisaster.jpg"
tags:
    - "strategy"
    - "transformation"
    - "platform engineering"
categories:
    - "strategy"
    - "architecture"
---

# Platform Engineering Antipatterns

You are probably already on your path to implementing platform engineering in your company. Maybe it was triggered by a major cloud transformation or a significant overhaul of your software development practices. Perhaps you embarked on this journey because you’ve been struggling with DevOps or SRE practices. You are thinking platform engineering is loved, cherished and promoted by the industry, so, there must be something to it?

<!--more-->

One thing is for sure: you started this path because you want a better and more efficient model for your organization whether to speed up development or reduce costs. Who wouldn’t want that? 

> The header of this blog post is a reference to some of the systematic failures that lead to disasters on large oil platforms, ranging from spills to explosions and all sorts of unwanted, unplanned, and unintended consequences.

---

## What Do You Mean by a Platform?

In this blog, I will discuss platforms through the lens of cloud modernization. From this lens, our focus is mostly on internal developer platforms. Therefore, I mostly refer to “internal developer platforms” when I talk about a platform in this blog. 

---

## Why This blog?

Despite good intentions and valuable promises, platforms often fail due to systematic issues and unforeseen challenges. They promise to solve many problems: reduce complexity, increase innovation, and streamline operations. But they fail in addressing broader contextual needs that go beyond technology. 

This will lead to all sorts of challenges we will see when we are discussing the antipatterns that push platforms into disorder and make it difficult for organizations to realize the benefits they desire from platforms. 

In this blog I aim at providing some mental models that would help you navigate those complexities and guardrail your strategy from the start.

Opinions in this blog are my own. They come from real life experience battling complexity and helping organizations in their cloud transformation journey. 

---

## But What Is an Antipattern?

In this blog, I use the term *antipattern* in the same manner as Donella H. Meadows describes it in her book *Thinking in Systems*:

> "An antipattern can be understood as a systemic trap or archetype. A recurring dysfunctional pattern in complex systems that leads to undesirable outcomes."  

I have never met anyone in my career—or in life for that matter—who set out to execute a strategy knowing it would fail and lead to dysfunctional outcomes. Yet, those outcomes occur!

In this blog I will highlight areas to be cautious about and questions you might face when implementing and designing your platform strategy.

These antipatterns arise within specific contexts rather than being universal. They emerge unintentionally, as a consequence of the complex nature of technological transformation. If you observe the symptoms outlined below, you have likely encountered an antipattern.

*The antipatterns overlap, and that is expected. Systematic problems are often connected, yet they manifest differently depending on the context.*

---

## 1. A Platform for Everything

### Context

A well-intended approach by platform teams is to create a single platform that covers every aspect of the software development lifecycle, with no escape hatches, only an opinionated and heavily guarded path. This platform attempts to unify development, deployment, observability, security, optimization, and governance. This antipattern is common during transformation times. 

### Symptoms
{{< list >}}

Platform teams introduce rigid prioritization techniques to manage the flux of demand.
A lack of cohesion between platform components leads to excessive documentation, approvals, and meetings to maintain harmony.
Platform teams continuously try to introduce a common denominator even when it is not needed.
New tools and capabilities are frequently added with low adoption rates and (feature creep).
{{< / list >}}

### Results

**Innovation Slows Down:**

Innovation is inherently unstructured, often lacking clear requirements. Innovating teams need speed and potentially also access to less mature and commonly adopted technologies. If your platform is covering a huge surface your teams will tend to apply prioritization and standardization techniques to maintain order and stability of the platform and manage their workloads. Left unchecked, this approach clashes with innovation that typically needs access to less mature or niche technologies that have not yet been widely adopted across the organization. 

**Increased Platform Complexity:**

{{< rows >}}
{{< row-item >}}
Platform teams, incentivized by a general platform strategy and broad mission, often fall into the {{< link href="https://melissaperri.com/blog/2014/08/05/the-build-trap" text="Build Trap" >}} by rapidly adding features in response to innovation team demands. This reactive approach prioritizes the platform-as-a-product feature delivery over long-term platform stability, leading to increased complexity and unchecked technical debt. Instead of focusing on measurable outcomes and sustainable improvements, teams become trapped in an endless cycle of feature delivery, which diminishes the platform's effectiveness.
{{< /row-item >}}

{{< row-item >}}
{{< figure src="/images/itsatrap.webp" alt="It's a trap" class="w-full" >}}
{{< /row-item >}}
{{< /rows >}}

Your platform will either only serve the biggest stakeholders leaving innovators in the cold, or, over time it will be serving every purpose, and your maintenance demands will exponentially increase.

The curious thing here, too, is that the biggest stakeholder of your platform isnt necessarily your most valuable asset from a business perspective.

Keep in mind that if innovation is a priority then you need to ask yourself if your platform really delivering on it's promises, or if you are chasing a theoretical dragon that will grant you all your wishes once you find it. 

Can you have such a large platform without maintaining it? can you ever reach that dragon and ask it to grant you all your wishes? how much are you willing to invest into that?

If your answer is: Ah! But it's cheap! And my cloud bill says so. 
Then I wonder what other bills you have and how their cost trend look like?

---

## 2. Product Everything

### Context

Another well-intended strategy by platform teams is to decompose all developers’ requirements into components (capabilities in the product or enterprise architecture lingo) and start treating every platform component as a managed product. The granularity of these products increases over time, with even the smallest non-functional requirements becoming separate products. Platform teams require more time from their product owners or demand additional product owners to manage these "products" effectively. This antipattern is typical in organizations still learning platform engineering and adopting the product thinking ways of working. 

### Symptoms

{{< list >}}
Solutions are created for problems that were never concerns before—even if you just came from a private cloud environment.
Platform teams complain about a lack of vision and unclear roles.
Teams become fragmented, working on small, non-functional requirement "products."
Teams seek control over well-standardized, cloud-managed services with "add value" propositions.
Platform teams obsess over abstracting away complexity from developers, while developers complain about being isolated from cloud technologies.
{{< /list >}}

### Results

**Increased Waste:**
{{< rows >}}
{{< row-item >}}
Platform teams start developing solutions for problems that either do not exist or have already been solved. After all, a platform is a product and that product needs to grow? Right?

These solutions often take the form of customized components layered on top of cloud-managed services with the promise and value proposition of adding value and reducing complexity. A noble and well intended quest. Yet, it can lead to lots of unforeseen issues.

{{< /row-item >}}

{{< row-item >}}
{{< figure src="/images/mvp.jpg" alt="MVP? No way!" class="w-full" >}}
{{< /row-item >}}
{{< /rows >}}

These unforeseen problems will not only affect your platform teams as they would need to maintain all of those components. They will also affect the stakeholders and users of your platform given the divergence in ways of working between standardized cloud models and your customized platform models. 

Reducing the surface of divergence is the very reason you started your platform initiative. But your platform might paradoxically increase the divergence. 

Be cautious if your goal is to provide the most impactful and minimally necessary platform for developers. This antipattern will increase your platform friction and slow down achieving your strategic goals.

Would metrics help you in this scenario? Customer Satisfaction metrics and product metrics? 

Maybe! [Goodhart's law](https://en.wikipedia.org/wiki/Goodhart%27s_law) may disagree though. I would put my money on deliberate and intentional leadership that accounts for the whole systematic view, in my experience, this is the most difficult thing to do, yet, it's is the most impactful. 

---

## Conclusion

Platform engineering is not doomed, but it is challenging. It drastically changes the way your organization works! for the better! However, success requires a systematic approach to change.

The symptoms reveal the antipatterns. Identify these symptoms and correlate them with your strategy. If you see a strong correlation, you’ve found the antipattern, and you’ll have a clearer idea of the outcomes it may bring.

Overgeneralization leads to complexity. To paraphrase Bjarne Stroustrup:

> "Within C++, there is a much smaller and cleaner language struggling to get out."

Likewise, within your complex platform, there is a smaller and cleaner platform waiting to emerge.

Sequencing your platform architecture is just as important as defining the target architecture. Starting with a rigid target assumes you know all the requirements upfront. Instead, leave room for maneuverability.

I have observed these antipatterns—and more—while assisting organizations in executing and developing platform strategies. Connecting platform layers from stakeholders to engineering teams is difficult and raises countless unforeseen questions—from “How do we keep on innovating?” to “But who’s going to be on-call for all of this?”

A successful platform strategy requires understanding your environment and having deep expertise in sequencing a dynamic strategy with strong, clear value propositions that connect the dots between **People, Work, Structure, and Technology**.
