# Chaos Engineering Whitepaper v0.1

Although a wealth of definition subtle variations exist on the subject of chaos engineering, we'll start with the one from the [Principles of Chaos Engineering](http://principlesofchaos.org/):

*Chaos Engineering is the discipline of experimenting on a distributed system in order to build confidence in the system’s capability to withstand turbulent conditions in production.*

Said otherwise:

**Bad things** will happen to your system, no matter how well designed it is. You cannotbecome ignorant to it.

The definition covers most of the main important aspects of chaos engineering:

* it is a discipline rather than a process. In other words, it leans on the actors capacity to stick to principles and making the right judgment call rather than having to follow prescriptive rules about how they must conduct their effort. The discipline usually emerges from the actors, and their unique needs
* while this definition is specific about distributed system, where it provides the great benefits, chaos engineering is concerned about any system with enough complexity. It gives the actors a way of navigating this  complexity to learn and improve production is the main target of the effort. While actors could, and likely should, carry chaos engineering effort in their non-production environment, it is best performing it in production where it matters.

All of these facets are meant for actors to build confidence in their production system and feel they can become familiar, and responsive, with its dynamic nature.

## Characteristics

The Principles of Chaos Engineering describe well the various characteristics of the discipline.

## Vocabulary

Throughout this proposal, we will be using some terms that are fairly specific to the chaos engineering discipline:

* **hypothesis**: question actors ask themselves about an aspect of their system's behavior after condition variations, described in terms of a result expressed as a quantity (ie. measurement)
* **experiment**: investigation of the hypothesis through variable measurement and observability of the system's state 
* **instrument(ation)**: associate a particular result with an change in the system’s condition (the method of measurement)
* **calibration**: identify and refine the amount of uncertainty included in a result.
* **observability**: capability of a system to be considered from different angles while it is being used

## Use Cases

So, what are the use cases for chaos engineering? As stated in the overview, there is no single golden rule applied across the board.

However, here are a few areas where it makes sense to carry chaos engineering efforts:

* **Dependency on third-party providers ****out of actor's**** control**: what is the effect of using provider X, when that provider goes down?
* **Network dependant services:** Network cannot be trusted, even internal networking, can we cope with a link failure?
* **Service release impact may not be tested for peripheral aspects of the system:** New release is made of one of the internal services, while its performances do not impact user's responsiveness, we note an increase in our costs due to poor resource management
* **Testing the engagement process and ensuring employees understand how to respond to pages and where playbook resources are**: in other words, actors should hope to find answers, using chaos engineering experiments, regarding unhappy paths, especially cascading failure modes.
* **Surfacing unknown/transitive dependencies within a system:** as systems become more complex the dependency graph and how stresses in one part of the system can cause other parts to change can become impossible to know holistically ahead of time.

## Chaos Engineering in Cloud Native Systems

While chaos engineering is by no means focusing on a specific system architecture, it can have deep impacts on cloud native systems usage. Characteristics of cloud native systems that are interesting to chaos engineering:

* **dynamic**: resources and services come and go and cannot be trusted to remain for any specific amount of time
* **promote isolation of concerns**: outcomes of a well-focused chaos experiment should be easier to make sense of
* **automation**: being API driven makes them great candidate for experimental automation needs
* **value observability**: cloud native systems expose mechanisms for an operator to observe the live system's behavior, which is an inherent expectation of a well-crafted chaos experiment

In other words, cloud native systems characteristics lend themselves naturally

to chaos engineering and vice versa.

But, what's in it for cloud native users and operators? Would they conduct chaos experiments for the sake of it?

Cloud native systems abstract large chunks of complexity away from them. But it does not seem reasonable to assume this complexity disappears altogether. It is merely made simpler to deal with. Operators, and developers alike, must keep a level of familiarity and understanding of the stack they rely on in order to offer relevant responses in face of adversarial conditions.

In a nutshell, chaos engineering reminds the actors that the underlying system, for all its benefits, cannot be trusted nor become a black box.

Actors must remain active, and even proactive, in the lifecycle of their system.

## Landscape

* Kubernetes-native chaos engineering

    * [https://github.com/bloomberg/powerfulseal](https://github.com/bloomberg/powerfulseal)

    * [https://github.com/jnewland/kubernetes-pod-chaos-monkey](https://github.com/jnewland/kubernetes-pod-chaos-monkey)

    * [https://github.com/asobti/kube-monkey](https://github.com/asobti/kube-monkey)

    * [https://github.com/linki/chaoskube](https://github.com/linki/chaoskube)

* [The Simian Army](https://github.com/Netflix/SimianArmy) - A suite of tools for keeping your cloud operating in top form.

* [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - Version 2 of Chaos Monkey by Netflix

* [kube-monkey](https://github.com/asobti/kube-monkey) - An implementation of Netflix's Chaos Monkey for Kubernetes clusters.

* [Gremlin ](https://www.gremlininc.com/)- Chaos-as-a-Service - Gremlin is a platform that offers everything you need to do Chaos Engineering. Supports all cloud infrastructure providers, Kubernetes, Docker and host-level chaos engineering. Offers an API and control plane. 

* [Pumba](https://github.com/gaia-adm/pumba) - Chaos testing and network emulation for Docker containers (and clusters).

* [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) - A chaos engineering toolkit to help you build confidence in your software system.

* [ChaoSlingr](https://github.com/Optum/ChaoSlingr) - Introducing Security Chaos Engineering. ChaoSlingr focuses primarily on the experimentation on AWS Infrastructure to proactively instrument system security failure through experimentation.

* [drax](https://github.com/dcos-labs/drax) - DC/OS Resilience Automated Xenodiagnosis tool. It helps to test DC/OS deployments by applying a Chaos Monkey-inspired, proactive and invasive testing approach.

* [Wiremock](http://wiremock.org/) - API mocking (Service Virtualization) which enables modeling real world faults and delays

* [MockLab](http://get.mocklab.io/) - API mocking (Service Virtualization) as a service which enables modeling real world faults and delays.

* [Pod-Reaper](https://github.com/target/pod-reaper) - A rules based pod killing container. Pod-Reaper was designed to kill pods that meet specific conditions that can be used for Chaos testing in Kubernetes.

* [Muxy](https://github.com/mefellows/muxy/) - A chaos testing tool for simulating a real-world distributed system failures.

* [Toxiproxy](https://github.com/Shopify/toxiproxy) - A TCP proxy to simulate network and system conditions for chaos and resiliency testing.

* [Blockade](https://github.com/worstcase/blockade) - Docker-based utility for testing network failures and partitions in distributed applications.

* [chaos-lambda](https://github.com/bbc/chaos-lambda) - Randomly terminate ASG instances during business hours.

* [Namazu](https://github.com/osrg/namazu) - Programmable fuzzy scheduler for testing distributed systems.

* [Litmus](https://github.com/openebs/litmus) -  An open source framework for chaos engine based qualification of Kubernetes environments

* [https://github.com/guardicore/monkey](https://github.com/guardicore/monkey): The Infection Monkey is an open source security tool for testing a data center's resiliency to perimeter breaches and internal server infection. The Monkey uses various methods to self propagate across a data center and reports success to a centralized Monkey Island server.
