---
layout: post
title: "Why collaboration shouldn't be the aim?"
date: 2022-05-06
---

Collaboration is an often repeated company mantra. You can see it in pair programming, mob programming, tight cross-team dependencies, calendars full of meetings and a snowballing amount of Slack conversations. In some cases collaboration is crucial for success. However, in others it can be detrimental. In this article I’m going to provide some insights about how to decide when collaboration is necessary and when it isn’t.

<!--more-->

## Collaboration Contexts

Team work always happens in context. People need to design a new feature, to integrate with a new API, to resolve an incident, to code on a well-defined task and so on. In some of these contexts, collaboration will cause harm or hamper progress. In others, it won’t. From my experience, I’ve identified the following contexts where collaboration has an impact:

1. Discovery. This is the process where we either have to compose requirements into an entirely new feature or we have a complex feature and we have to find a good-enough technical design for it;
2. Integration. In that case, we have to use an external system to do our job. It can have a well-defined API, just some documentation or nothing else than the contact of a team member who has left long time ago;
3. Incident resolution. Here, something bad has happened and we need to resolve it. Fast;
4. Implementation. In that case, we *mostly* know what to do and just have to sit down and do it;
5. Improvement. That relates to improving how our organization works based on feedback.

### Discovery

During this phase a team tries to understand a problem it’s going to solve. The problem can be the development of a new feature, the starting of a business, new product kick-off or some other activity that requires a team to find out what they actually need to do.

In that case, doing things in isolation is going to prevent the team from achieving their objective. It’s best if the team gets together and work through the uncertainty. Collaboration is key, but it’s also crucial to make it facilitated. Otherwise, the team can go in circles forever without reaching a proper decision. Or, they can reach a decision but won’t be able to organize it.

How can you facilitate the discovery? First, someone should take the role of a facilitator. Usually, it’s the most organized person in the team. They should keep the team’s focus, time frame and constantly work towards the decision without leaving anyone unheard. The facilitator can use simple techniques like brainstorming for idea generation, and TODO lists for prioritizing next steps**.** If these don’t do the job, liberating structures like [1-2-4-All](https://www.liberatingstructures.com/1-1-2-4-all/), [Min Specs](https://www.liberatingstructures.com/14-min-specs/) or something else from the [LS Menu](https://www.liberatingstructures.com/ls/) can work wonders.

### Integration

Here, the team has to integrate with a system that another team has developed. If the company values team autonomy, then each team has to provide a clear and standard API definition for their system. There are several options for that:

1. [Swagger](https://swagger.io/). This is a well-known API definition format based on YAML. Its downside is that it doesn’t enforce people to maintain their API definitions up-to-date in any way and is heavily oriented towards REST;
2. [Protocol Buffers](https://developers.google.com/protocol-buffers) or other RPC format that enforces code generation. This format resolves the problems of Swagger. It supports both asynchronous and synchronous modes of communication;
3. [cloudevents](https://cloudevents.io/). This is the [CNCF](https://www.cncf.io/) specification for describing events. It’s really useful if you want to enforce asynchronous inter-component communication in a standard way.

If a company doesn’t value team autonomy, things get way more difficult. Teams have to collaborate. And cross-team collaboration is a great way to waste people’s time. Don’t get me wrong: sometimes cross-team collaboration is the only way to get a meaningful initiative done. However, you have to be really mindful of its downsides. If you have to do this, be really pessimistic in estimating the integration work. It **will** take more time than you think.

### Incident Resolution

When there’s an incident, the main objective of the team responsible for it, is to reduce the time to recovery as much as possible. Depending on the incident this might require a single on-call engineer to do a revert, a single team to get into a war room or people from multiple teams to get together. A well-functioning incident resolution process should mostly involve the on-call engineer, rarely involve a whole team and almost never summon multiple teams together.

For this to happen, several things have to be setup well:

1. System components should be as decoupled as possible. So, failures will rarely propagate;
2. Teams should have high-quality runbooks describing their systems and ways to resolve the most common incidents;
3. Proper telemetry systems - monitoring, logging and tracing;
4. A well-functioning revert mechanism;
5. Proper process of establishing war-rooms and conducting incident resolution;
6. Proper process of learning from the incident.

Point 5 of this checklist is what will help you have efficient and effective collaboration when multiple people have to resolve the incident. A way to determine whether your incident resolution process has big flaws is to observe whether:

1. Senior leadership frequently participates in fighting incidents;
2. Many people get into a meeting together while most of them just sit and do nothing;
3. People (usually managers) constantly pressure the engineers who are trying to resolve the issue.

### Implementation

Here, you have an individual contributor or several of them who know what they have to do and just move forward and do it. Most obstacles should’ve been resolved during the Discovery phase. However, many unknowns around the implementation should still remain. Usually, people working on implementation go through the [hill chart](https://basecamp.com/features/hill-charts) starting at “figuring things out” and moving towards “making it happen”.

If a person works alone during implementation it’s best to leave them do their job. If several people need to collaborate, well-known techniques like [pair programming](https://martinfowler.com/articles/on-pair-programming.html) and [mob programming](https://en.wikipedia.org/wiki/Mob_programming) might work quite well.

### Improvement

Lastly, you have improvement. Systems, ranging from the single individual to billions of individuals, can’t exist without feedback loops. In teams and organizations the most common form of feedback is the Retrospective. During it, key individuals gather and discuss how things can become better. With good facilitation methods, you can let literally everyone inside an organization share their perspective on how things can improve and what went well.

In order to make a retrospective effective and efficient, you have to ask the right questions, let people be heard and be good at managing time and focus. You can either rely on simple tools like [metroretro](https://metroretro.io/) or more involved techniques like [What, So What, Now What](https://www.liberatingstructures.com/9-what-so-what-now-what-w/).

## Conclusion

Collaboration isn’t always a virtue. Moreover saying that people need to collaborate is often a meaningless and even damaging statement. Without understanding when it’s applicable and when it’s not you can’t get the most of it. Even more, whenever collaboration is the way to do things, it has to be done with people and process in mind. Just throwing a bunch of people at a problem and telling them to collaborate rarely works.

So, think of the context in which people have to do something. Does it require collaboration? If it does, how should that collaboration happen? Should someone drive it? Or the team is mature and self-organized enough to properly do it on their own?
