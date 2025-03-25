---
authors: ["Alex Elshamouty"]
date: "2025-03-21"
title: "Platform Engineering Antipatterns: Part 2"
description: "Platform engineering is taking over the world! Or... not?"
summary: "Shared responsibility, enablement and bounderies in platform engi"
headerimage: "deepwaterdisaster.jpg"
tags:
    - "strategy"
    - "transformation"
    - "platform engineering"
categories:
    - "strategy"
    - "architecture"
---

# Platform Engineering Antipatterns: Part Two

In the [previous blog](/posts/platform-engineering-antipatterns/) post, we wrote about some of the anti-patterns of Platform Engineering.

We discussed what an Anti-pattern is and touched upon the Platform for everything and product everything patterns.

Today we will discuss a few more anti-patterns within the scope of an internal developer platform.

That being said, although we are discussing platforms from the lens of cloud modernisation and developer platforms, I truly believe that some of the anti-patterns we will discuss today will have a strong presence in other types of platforms as well. But that will be a subject we will discuss in depth in another series.

Let's dive in!

<!--more-->

---

# Use “X” Technology for Everything 

### Context 

Many organisations will resort to the use of cloud-agnostic technologies to reduce the vendor lock-in risk. This is a subject in itself which I do not feel that needs to be covered since [Gregor Hohpe](https://architectelevator.com/about/) already wrote [a master piece on this subject](https://architectelevator.com/architecture/cloud-oss-lockin/).

Those cloud-agnostic components pull teams to build more custom solutions on-top of them with the promise of avoiding lock-in, cost efficiency, and many more. These components offer fine-grained control, which appeals to platform tech-savvy teams who prefer custom-built solutions over ready-made alternatives. However, this results in low adoption of managed cloud services. Why is that a problem, you might ask? It's a problem because if you went to the public cloud to benefit from public cloud services but all of a sudden you find out that your public footprint actually resembels a private cloud footprint with most of the spending allocated to vanilla compute, storage, and networking rather than managed services, then you might not have achieved the goal you set out to achieve. 

{{< rows >}}
{{< row-item >}}
The effects of this anti-pattern are usually amplified when combined with the product everything anti-pattern. Teams managing those platform components, incentivised by a product development approach, push relentlessly for adoption, effectively creating their own service provider within your department. Usually not what the business intended or needed when they embarked on their cloud modernisation journey.
{{< /row-item >}}
{{< row-item >}}
 {{< figure src="/images/kubernetes.jpg" alt="Kubernetes!" class="w-full" >}}
{{< /row-item >}}
{{< /rows >}}


### Symptoms 
{{< list >}}
Your platform architecture diagrams reveal strong dependencies on specific platform components. 

Teams managing these components are under heavy pressure and frequently request more resources. 

Attempts are made to distribute the operational load of these components to other teams using complex engineering solutions 

Your team mostly hires A-players, and you struggle to find, hiring, and retain them 

Managed cloud services are underutilized. 

Teams develop in-house solutions that have strong cloud-managed alternatives. 
{{< / list >}}

 
### Results 

**Strategic misalignment:**

Culture is an important part of any organisation - The DNA of the organisation and its values form an integral part of its sociotechnical system. Introducing technology within your organisation should be viewed not only from the lens of technical advantage, but also from the lens of cultural fitness.

Inserting a technology that incentivizes more "build" over "consumption" will increase the wall of inertia of componentization, affecting your ability to create new sources of value. I am thankful that I do not have to write about this myself because there are great thinkers and giants whom I can stand on their shoulders. If you want to deep dive into what I mean by creating new sources of value by componentization, please refer to the Wardley's climatic patterns - specifically [Higher order systems create new sources of worth](https://medium.com/wardleymaps/exploring-the-map-ad0266fad59b)

What does it mean practically for the less abstractly inclined reader? Let's flip the question:

{{< rows >}}
{{< row-item >}}
{{< list >}}
Are you running your own documentdb?
Are you running your own elastic-search service?
Are you running your own identity and access management for M2M?
Is your "public cloud team" considering running function as a service platforms on top of Kubernetes to provide serverless technologies to developers?
Are you a cloud service provider by any chance?
{{< / list >}}
{{< /row-item >}}
{{< row-item >}}
 {{< figure src="/images/idk.png" alt="Not sure if!" class="w-full" >}}
{{< /row-item >}}
{{< /rows >}}

The well-intended behavior to help the organisation will undermine the "you build it, you run it" paradigm. Why is it a problem to undermine the "you build it, you run it" philosophy? Well, likely, you did not go to the cloud to start a prioritisation and product refinement session every time a development team needs a feature or a technology, right? If they can not build it and run it, someone will have to, right? 


# Convergence in a federated context

### Context 

You are building a developer platform within an organization that operates under a heavily federated model, where multiple business units function with a high degree of autonomy, each with their own goals, priorities, and technical stacks. Your objective is to unify and streamline the developer experience by offering a centralized platform that promotes standardization, accelerates delivery, and reduces duplication of effort.

As a result, the platform team is not only tasked with technical enablement but also must act as an internal advocate, navigating political boundaries, building trust across business units, and demonstrating clear value tailored to diverse use cases. 

### Symptoms 

{{< list >}}
Platform friction increases over time, instead of decreasing. 

The platform’s benefits are vague and unclear. 

It's challenging to identify shared needs across teams, which often results in the platform being heavily customized for each individual team.

The current focus is entirely on driving platform convergence and adoption, without a clear long-term vision for how the platform will evolve or create ongoing value beyond initial rollout.

Platform teams focus on theory but fail to ground it in the practical realities of the organization.

The focus on operational cost reduction comes without a corresponding analysis of resource needs or capital investments, creating a blind spot in platform planning and evaluation.

Without a clear understanding of resource demands and capital investments, teams risk adopting solutions that are difficult to maintain in the long run, undermining platform sustainability

 {{</ list >}}


### Results 

You will struggle to explain the platform’s benefits to different stakeholders. Your strategy will face pushback because it lacks a roadmap, clear vision, or adoption plan. 

The platform is perceived as an imposed initiative rather than an enabler, leading to resistance and shadow IT. 

Continued investment in the platform becomes hard to justify because its long-term value proposition is unclear. 

This is where your platform strategy may stall or might come to a screeching halt due to friction and lack of stakeholder support. After all, why are you building your platform if not to help your stakeholders?

Imagine you are building a high-speed train network designed to connect multiple cities and improve mobility within each city. Sound like a game-changer? Of course: faster travel, seamless connectivity, and a modern transportation system.  

But paradoxically you cannot generate demand, and people are resenting your plans. 

The reality is that each city you plan to connect has its own existing transportation system and local habits. People do not see a compelling reason to switch their current options are reliable, affordable, and deeply embedded in daily life. Adoption feels like an unnecessary burden residents must install new apps, learn a new ticketing system, and adapt to an unfamiliar mode of travel, making the switch inconvenient. 

You could resort to going to court and force adoption, but this is a long and unpredictable path…
