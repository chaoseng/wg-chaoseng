# Chaos Engineering Whitepaper v0.1

## What is Chaos Engineering

*Chaos Engineering is the discipline of experimenting on a distributed system in order to build confidence in the system’s capability to withstand turbulent conditions in production.* - [Principles of Chaos Engineering](http://principlesofchaos.org/)

### Short History

### Principles

The Principles of Chaos Engineering describe well the various characteristics of the discipline.

The definition covers most of the main important aspects of chaos engineering:

* it is a discipline rather than a process. In other words, it leans on the actors capacity to stick to principles and making the right judgment call rather than having to follow prescriptive rules about how they must conduct their effort. The discipline usually emerges from the actors, and their unique needs
* while this definition is specific about distributed system, where it provides the great benefits, chaos engineering is concerned about any system with enough complexity. It gives the actors a way of navigating this  complexity to learn and improve production is the main target of the effort. While actors could, and likely should, carry chaos engineering effort in their non-production environment, it is best performing it in production where it matters.

All of these facets are meant for actors to build confidence in their production system and feel they can become familiar, and responsive, with its dynamic nature.

#### Terminology

Throughout this proposal, we will be using some terms that are fairly specific to the chaos engineering discipline:

* **hypothesis**: question actors ask themselves about an aspect of their system's behavior after condition variations, described in terms of a result expressed as a quantity (ie. measurement)
* **experiment**: investigation of the hypothesis through variable measurement and observability of the system's state
* **instrument(ation)**: associate a particular result with an change in the system’s condition (the method of measurement)
* **calibration**: identify and refine the amount of uncertainty included in a result.
* **observability**: capability of a system to be considered from different angles while it is being used

## Why practicing Chaos Engineering

### Harness and Improve System Reliability

Chaos Engineering as a practice lends itself to exploring facets of a system's
reliability such as its resilience, scalability, security, safety or
privacy.

All these dimensions of a system have a direct impact on end-users' perception.
Experimenting degraded conditions may leave lasting negative opinion of the
service a system renders. In the worst case scenario, poor conditions may
lead to legal issues.

In effect, Chaos Engineering is a unique practice to enable an organization-wide
budget for harnessing and improving the system reliability for a delightful
user experience.

### Benefits for Cloud Native Systems

Chaos Engineering lends itself well to Cloud Native Systems which, by
nature, provide the platform for strong system reliability.

Properties of Cloud Native Systems that benefit Chaos Engineering:

* **dynamic**: resources and services come and go and cannot be trusted to remain for any specific amount of time
* **promote isolation of concerns**: outcomes of a well-focused chaos experiment should be easier to make sense of
* **automation**: being API driven makes them great candidate for experimental automation needs
* **value observability**: cloud native systems expose mechanisms for an operator to observe the live system's behavior, which is an inherent expectation of a well-crafted chaos experiment


Through these properties, Chaos Engineering experiments can be
designed, implemented and automated to provide continuous auditing of the
impact of degraded conditions in the system. This feedback loop provides
great insights about platform and application behavior under stress,
allowing both to adapt and improve accordingly.

With that said, while Cloud Native Systems abstract large chunks of complexity
away from users, this complexity does not disappear altogether.
It is merely made simpler to deal with. Operators, and developers alike,
must keep a level of familiarity and understanding of the stack they rely on
in order to offer relevant responses in face of adversarial conditions.

In a nutshell, Chaos Engineering reminds the actors that the underlying system,
for all its benefits, cannot be trusted nor become a black box.

Actors must remain active, and even proactive, in the lifecycle of their system.

### Software and Operational Practices In Production

Chaos Engineering is a new practice in the toolbox of product teams, but whereas,
most best practices focus upstream, Chaos Engineering does take a look at
downstream, once the system is live, ideally in production.

Practices such as testing happen either in development environment or
production lookalike but seldom performed once the system is in the hands of
users. In other words, testing is most often performed in static or controlled
conditions whereas Chaos Engineering factors in a certain level of serendipity.

Chaos Engineering does not take results of an experiment in binary - 
passed|not passed - fashion. Instead, results are meant to be analysed and
correlated with the system's state and events at the time the experiment
took place.

With that said, the practice of Chaos Engineering should benefit from
well-defined policies such as automation or reporting.

### Use Cases

So, what are the use cases for chaos engineering? As stated in the overview, there is no single golden rule applied across the board.

However, here are a few areas where it makes sense to carry chaos engineering efforts:

* **Dependency on third-party providers ****out of actor's**** control**: what is the effect of using provider X, when that provider goes down?
* **Network dependant services:** Network cannot be trusted, even internal networking, can we cope with a link failure?
* **Service release impact may not be tested for peripheral aspects of the system:** New release is made of one of the internal services, while its performances do not impact user's responsiveness, we note an increase in our costs due to poor resource management
* **Testing the engagement process and ensuring employees understand how to respond to pages and where playbook resources are**: in other words, actors should hope to find answers, using chaos engineering experiments, regarding unhappy paths, especially cascading failure modes.
* **Surfacing unknown/transitive dependencies within a system:** as systems become more complex the dependency graph and how stresses in one part of the system can cause other parts to change can become impossible to know holistically ahead of time.

## Practicing Chaos Engineering

### Getting Started With Chaos Engineering

#### Is my system ready to endure Chaos Engineering?

Chaos Engineering is a fairly disruptive practice as it takes the position
that, by forcing the system away from its natural position, we can learn subtle
aspects of the system's behaviors other practices wouldn't unearth.

To achieve useful learnings however, the system need to be in a fairly reliable
conditions already. Should the system be too fragile, either the learnings
would be trivial or with high level of false positives.

The difficulty from trivial results is that the cost of setting up a Chaos
Engineering experiment may be high versus the quality of the learning.

As we suggested, Chaos Engineering supports exploring the reliability of a
system. While being authoritative is a challenge this whitepaper will not take,
it is good to check the basics of your system:

* Security: Look at the [OWASP](https://www.owasp.org/index.php/Main_Page))
  project which provides good security approaches for various use-cases
* ...




#### Do I need to get started in production

While we may want this, starting in prod may not fit "getting started scenarios".

#### Communicate with the Organization

This is where we need to continue the discussion and figure out how far we want/can go with the patterns.

Should we talk gamedays for instance? Observability?

The following phases may or may not be useful. I think it would be valuable if we could describe what it means to deal with chaos in those various cases, but is it the right place?

### Chaos Engineering Perturbations

#### Degrade Network Conditions

#### Vary Computing Resources

#### Stress to the Limits

#### Simulate Data Loss

#### Change ACLs Permissions

#### Provoke a Security Breach

#### Assume application fails to restart

### Chaos Engineering Automation

#### Continous Chaos Engineering

### Chaos Engineering Reporting

#### Report Findings

### Landscape

* Kubernetes-native chaos engineering
  * [https://github.com/bloomberg/powerfulseal](https://github.com/bloomberg/powerfulseal)
  * [https://github.com/jnewland/kubernetes-pod-chaos-monkey](https://github.com/jnewland/kubernetes-pod-chaos-monkey)
  * [https://github.com/asobti/kube-monkey](https://github.com/asobti/kube-monkey)
  * [https://github.com/linki/chaoskube](https://github.com/linki/chaoskube)

* [Blockade](https://github.com/worstcase/blockade) - Docker-based utility for testing network failures and partitions in distributed applications.
* [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - Version 2 of Chaos Monkey by Netflix
* [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) - A chaos engineering toolkit to help you build confidence in your software system.
* [chaos-lambda](https://github.com/bbc/chaos-lambda) - Randomly terminate ASG instances during business hours.
* [ChaoSlingr](https://github.com/Optum/ChaoSlingr) - Introducing Security Chaos Engineering. ChaoSlingr focuses primarily on the experimentation on AWS Infrastructure to proactively instrument system security failure through experimentation.
* [drax](https://github.com/dcos-labs/drax) - DC/OS Resilience Automated Xenodiagnosis tool. It helps to test DC/OS deployments by applying a Chaos Monkey-inspired, proactive and invasive testing approach.
* [Gremlin](https://www.gremlininc.com/)- Chaos-as-a-Service - Gremlin is a platform that offers everything you need to do Chaos Engineering. Supports all cloud infrastructure providers, Kubernetes, Docker and host-level chaos engineering. Offers an API and control plane.
* [https://github.com/guardicore/monkey](https://github.com/guardicore/monkey): The Infection Monkey is an open source security tool for testing a data center's resiliency to perimeter breaches and internal server infection. The Monkey uses various methods to self propagate across a data center and reports success to a centralized Monkey Island server.
* [kube-monkey](https://github.com/asobti/kube-monkey) - An implementation of Netflix's Chaos Monkey for Kubernetes clusters.
* [Litmus](https://github.com/openebs/litmus) -  An open source framework for chaos engine based qualification of Kubernetes environments
* [MockLab](http://get.mocklab.io/) - API mocking (Service Virtualization) as a service which enables modeling real world faults and delays.
* [Muxy](https://github.com/mefellows/muxy/) - A chaos testing tool for simulating a real-world distributed system failures.
* [Namazu](https://github.com/osrg/namazu) - Programmable fuzzy scheduler for testing distributed systems.
* [Pod-Reaper](https://github.com/target/pod-reaper) - A rules based pod killing container. Pod-Reaper was designed to kill pods that meet specific conditions that can be used for Chaos testing in Kubernetes.
* [Pumba](https://github.com/gaia-adm/pumba) - Chaos testing and network emulation for Docker containers (and clusters).
* [The Simian Army](https://github.com/Netflix/SimianArmy) - A suite of tools for keeping your cloud operating in top form.
* [Toxiproxy](https://github.com/Shopify/toxiproxy) - A TCP proxy to simulate network and system conditions for chaos and resiliency testing.
* [Wiremock](http://wiremock.org/) - API mocking (Service Virtualization) which enables modeling real world faults and delays
