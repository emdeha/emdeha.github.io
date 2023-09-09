---
layout: post
title: "Redesigning Software Systems"
date: 2021-12-19
---

Without constant refactoring, technical organizations tend to lose agility. This essay delves into an organization that has gone too far in delivering features at the expense of maintainability. As a result, outages have become the norm, feature delivery is slower than ever and developer satisfaction is low. At the core of this lies a distributed monolith. The senior engineering leadership team has reached the conclusion that something should be changed.  But what?

<!--more-->

---

When approaching architecture decomposition, we should start with [Conway's law](https://en.wikipedia.org/wiki/Conway%27s_law):

> Software design follows from the communication structure in a given organization.

This basically means that you can't effectively redesign a software system without changing the organization structure. So, if we want a system redesign to work, we should follow it with the appropriate organizational changes.

## How to redesign a system?

Now, how should we approach the redesign **technically**? There are couple of approaches:

1. Redesign according to technical domains: DB, Infrastructure, API, Business Logic Backend, Business Logic Frontend, Architecture;
2. Redesign according to objects: Van Service, Driver Service, Shift Service, Plan Service, Absence Service;
3. Redesign according to subdomains: Availability Management, Proposal Flow, Scheduling.

The most efficient design is the third one. Next, we'll see why is that and how to achieve it.

## Redesign according to technical domains

This redesign leads to big, highly coupled teams. Teams become highly coupled because the Business Logic team always needs the DB, Infrastructure and Architecture teams. They also become big because as the organization grows, the teams must grow to accommodate for the more work that needs to be done.

Another important consequence is the fact that it becomes really hard to share a common vision between the teams. Being under different leads, they have different objectives. The DB team wants to keep the DB as stable as possible and with the least possible schema changes. The Architecture team can get out of touch with reality if they don't fully understand the business context. The Business Logic teams are focused on making feature delivery as fast as possible. Whether all of these divisions jell well, depends entirely on how well the senior leaders communicate between each other. Even if they do it well, that's a big unnecessary hop in communication which leads to slowdowns.

Last but not least, deployment becomes a bottleneck. The Business Logic and DB teams have to sync between each other constantly.

The solution is cross-functional teams. All architecture, infra, DB and business logic should be provided by a single, small, well-organized team. There are two ways to do that: split the teams according to business objects or split the teams according to business domains.

## Redesign according to objects

Following [the single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) we might think that "do one thing and do it well" scales to microservice architecture. If we interpret it as "a single service should be responsible for a single object", it doesn't.

The main reason is the communication overhead in a distributed system. When migrating from a monolith to a microservice architecture, we trade off communication for independence. Teams and services need to communicate more but in exchange for that each team can work independently and each service can be deployed and scaled independently. Given that, it's key to keep the communication overhead in a microservice architecture to a minimum. So, if we split a monolith in objects we'll need to increase the communication between teams and services. Even more, the independence property (the key advantage of the microservice architecture) might be lost due to the need to coordinate deployments between several services that always change in unison.

Several services that change in unison. That's the key. What if all these services were a single service? Won't that solve our problem? Yes and it leads us to the proper way of decomposing a monolith in a microservice architecture.

## Redesign according to subdomains

Things that change in unison tend to belong to the same business [subdomain](https://microservices.io/patterns/decomposition/decompose-by-subdomain.html). However, what does a business subdomain represent? There's a well known concept in Domain Driven Design (DDD). This is the concept of a **domain**. A domain is the application's problem space - the business. An example problem space might be "getting a parcel from point A to point B". However, domains are usually too big and general. That necessitates splitting them into subdomains. Subdomains are parts of the business that contribute to the whole of the business when they interact between each other.

Given the above example problem space, there can be several subdomains for it:

- Proposal - Propose a parcel delivery service;
- Availability - Let the driver manage their availability;
- Schedule - Provide a schedule for parcel delivery.

However, a key property of a subdomain is that the change in a subdomain should rarely require a change in another subdomain. If that doesn't hold there's a high chance that you might need to expand your subdomain.

According to the above definition, it follows that when a microservice architecture is split according to subdomains, teams should be working as independently as possible, with the least amount of communication overhead.

We've understood that the proper way to redesign a system is to base it on the subdomains of the business. Let's see how to do that.

## How to split a system according to subdomains?

There are two major things here:

1. Defining the subdomains;
2. Changing the organizational structure, so it resembles them.

### Defining the subdomains

The most basic way to define these is to talk to the business. Understand how the business organization is structured. What key verticals are there? What are the key business flows? In order to do this properly we need a process. As far as I'm aware, the best process for that is [event storming](https://www.eventstorming.com/resources/).

During an event storming workshop a group comprised of both engineers and business people gathers. Their objective is to find out the main event flows in the system, the commands that trigger them and the functional components in which a group of event flows lives. You can see the process in detail in these [blog series](https://philippe.bourgau.net/misadventures-with-big-design-up-front/).

At the end of an event storming workshop, the team should've identified the key functional components in the system. Each functional component should map to a subdomain.

### Changing the organizational structure

After you've identified the subdomains, the next challenge is to change the organizational structure. Without changing this, you won't be able to implement the architecture. I've no clear proposal on this matter, but I think [this book](https://leanpub.com/dynamicreteaming) might be useful.

## Conclusion

The only approach that will lead to splitting an organization into proper teams is according to subdomains. This will lead to highly independent teams. We can do that by facilitating an event storming session where both product and engineering will be present. Once we finish this session, we should have a clear view of the new team structure. Based on this, we can move forward and implement the desired organization from which our architecture will evolve.
