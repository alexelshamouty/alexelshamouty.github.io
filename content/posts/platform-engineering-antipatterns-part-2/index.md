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

# Platform Engineering Antipatterns: Part two

In the [previous blog](/posts/platform-engineering-antipatterns/) post we wrote about some of the anti-patterns of Platform Engineering.

We discussed what an Anti-pattern is, and we touched up-on the Platform for everything, and, product everything pattern.

Today we will discuss a few more anti-patterns within the scope of an internal developer platforms.

That being said, although we are discussing platforms from the lens of cloud modernisation and developer platforms I truely believe that some of that anti-patterns we will discuss today will have strong presence in other types of platforms as well. But that will be a subject we will be discussing in depth in another series.

Let's dive in!

<!--more-->

---

# Use “X” Technology for Everything 

### Context 

Many organisation will resort to the usage of cloud-agnostic technologies to reduce the vendor lock-in risk. This is a subject in itself which I do not feel that needs to be covered since [Gregor Hohpe](https://architectelevator.com/about/) already wrote [a master piece on this subject](https://architectelevator.com/architecture/cloud-oss-lockin/).

Those cloud agnostic components pull teams to build more custom solutions on-top of them with the promise of avoiding lock-in, cost efficency and many more. These components offer fine-grained control, which appeals to platform tech-savvy teams who prefer custom-built solutions over ready-made alternatives. However, this results in low adoption of managed cloud services. Why is that a problem you might ask? It's a problem because if you went to the public cloud to benefit from public cloud services but all of a sudden you find out that your public footprint actually resembels a private cloud footprint with most of the spending allocated to vanilla compute, storage, and networking rather than managed services, then you might not have achieved the goal you set out to achieve. 

{{< rows >}}
{{< row-item >}}
The effects of this anti-pattern are usually amplified when combined with the product everything anti-pattern. Teams managing those platform component, incentivised by a product development approach, prush relentelsy for adoption effectively creating their own service provider within your department. Usually not what the business intended or neeeded when they embarked on their cloud modernisation journey.
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

Your team mostly hires A-players, and you struggle finding, hiring, and retaining them 

Managed cloud services are underutilized. 

Teams develop in-house solutions that have strong cloud-managed alternatives. 
{{< / list >}}

 
### Results 

**Strategic misalignment:**

Culture is an important part of any organisation - The DNA of the organisation and it's value form an integral part of it's sociotechnical system. Introducing technology within your organisation should be viewed not only from the lens of technical advantage, but also from the lens of cultural fitness.

Inserting a technology that incentivise more "build" over "consumption" will increase the wall of intertia of componentization - affecting your ability to create new sources of values. I am thankful that I do not have to write about this myself because there are great thinkers and giants which I can stand up-on their shoulders. If you want to deep dive in what I mean by creatinng new sources of values by componentization please refere to the Wardley's Climiatic patterns - specifically [Higher order systems create new sources of worth](https://medium.com/wardleymaps/exploring-the-map-ad0266fad59b)

What does mean practically? Let's flip the question:

{{< list >}}
Are you running your own documentdb?
Are you running your own elastic-search service?
Are you running your own identity and access managment for M2M?
Is your "public cloud team" considering running function as a service platforms on-top of Kubernetes to provide serverless technologies to developers?
{{< / list >}}


The well-intended behavior to help the organisation will undermine the "you build it, you run it" paradigm. Why is it a problem to undermine "you build it, you run it" philosophy? Well - it's likely you did not go to the cloud to start a prioritisation and product refinment session everytime a development team needs a feature or a technology, right? If they can not build it and run it, someone will have to, right? 


# Starting with the Target Architecture 

### Context 

You are building a developer platform within an organization that has a federated operating model with separate or semi-separate business units and goals. Your aim is to unify the developer experience through a centralized platform. However, adoption is low, and teams struggle to promote platform components. 

### Symptoms 

{{< list >}}
Platform friction increases over time, instead of decreasing. 

The platform’s benefits are vague and unclear. 

Finding common denominators is difficult, leading to excessive customization for different teams. 

The focus is solely on platform convergence and adoption, with no vision for what comes after. 

Platform teams discuss high-level theory but struggle to connect it to practical organizational challenges. 

Value proposition is focused on lowering run cost.  

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