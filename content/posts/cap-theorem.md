---
title: "CAP Theorem - A Brief Discussion"
date: 2016-06-17T23:46:06-05:00
tags: ["Architecture", "Computer Science"]
draft: false
---

Most of us have heard the popular proverb “you can’t have your cake and eat it too”. The literal meaning of this is that if you eat your cake, then it is gone, so you no longer have it. Metaphorically it teaches us that we cannot have two incompatible things.

CAP theorem (aka Brewer’s theorem from Eric Brewer) makes a similar assertion for distributed computer systems. CAP theorem states that you can have at most two of the following three properties; Consistency, Availability, and Partition Tolerance, because any two are mutually exclusive to the third. A brief outline of the properties follows:

* Consistency refers to the property that all nodes in a distributed system see the same data at the same time.
* Availability refers to the property that the distributed system will always be able to respond to a given request.
* Partition tolerance refers to the ability for the distributed system to continue operation even when faced with network failures.

Why are we limited to two?

For a simple example, let’s assume we have a distributed system with 2 partitioned nodes, node-A and node-B. Having two nodes improves _availability_ because each is independently capable of providing services. If node-A’s state is updated while the nodes are partitioned then node-B becomes inconsistent. We can ensure that the system maintains _consistency_ by making node-B appear unavailable, but this requires us to give up _availability_. In order to have both _consistency_ and _availability_ we must allow both nodes to communicate, which gives up _partition_ tolerance. This example illustrates that it isn’t possible to have all properties maximized; compromises need to be made. Traditionally, large distributed systems required _partition_ tolerance so designers had to choose between _consistency_ and _availability_ for the second property.

CAP theorem first appeared in 1998 and it still holds today, but savvy designers are able to play fast-and-loose with the “choose 2 out of 3” rule. One thing in the designer’s favor is that partitions are relatively rare in distributed systems. Another boon to the designer are modern techniques that grant flexibility when handling partitions and recovering from them after they happen. These allow designers to focus on maximizing combinations of _consistency_ and _availability_ for the specific need of the application until a _partition_ actually occurs. When it does occur, the system may need to fall back to favoring either _availability_ or _consistency_ until the _partition_ ends.

There are still significant challenges in making this all work, such as detecting when a _partition_ has occurred and implementing a recovery strategy when it does. For example, if _availability_ is the chief concern during a _partition_ event, the state of multiple nodes can progress independently and will need to be merged once the _partition_ ends. The merge itself may present conflicts that will need to be dealt with by the system in order to return to a consistent state.

That’s a very brief summary of CAP theorem. It tells us that when designing distributed computer systems we need to make compromises in order to achieve certain desirable characteristics. As architecture techniques and tools evolve, designers are able to maximize combinations of the properties depending on the state of the system. Even with these advancements, however, designers still cannot maximize all properties at all times; they cannot have their cake and eat it too.