---
layout: post
title: "Agile Architecture Review Boards"
date: 2022-01-12
---

The following post describes an organization that is evolving and has reached the point where the need for consistent cross-team practices has arisen. The organization has tried to tackle this issue with an Architecture division. However, having a functional department creates preconditions for Ivory Tower development. I suggest how employing an Agile Architecture Review Board can resolve the issue.

An Agile Architecture Review Board is a cross-functional and cross-team group.  With its diverse technical and domain background it aims at putting a set of architectural principles and practices that should scale the organization. The following sections describe the Purpose, Structure and Processes that should guide this Board.

<!--more-->

## Purpose

The Agile Architecture Review Board should have the responsibility for:

1. **Making sure teams have a standard protocol for communicating between each other (both person-to-person and service-to-service)**. This will resolve the issue where we always need to reach some other team in order to integrate with them. Instead, we can rely on clear APIs that can be used with minimum human interference;
2. **Specifying the architecture principles the organization follows.** Principles such as availability, scalability, security, elasticity, extensibility and so on are the core guides for a successful architecture. These should be clearly specified, measurable and followed by teams;
3. **Defining the architecture the organization wants to achieve and making sure the organizational chart allows this ([inverse Conway maneuver](https://www.thoughtworks.com/radar/techniques/inverse-conway-maneuver)).**

## Structure

The Agile Architecture Review Board should be a **part-time** job for a group of 7-10 key people at the organization. A person can participate in the board if they have some of the following qualities:

1. **Leadership**. To help the Board work towards a common vision;
2. **Management**. To help the Board organize itself in the best way possible;
3. **Technical Expertise**. To help the Board have proper technical guidance;
4. **Popularity at the Organization**. To help organization members see that the board consists of people they admire.

Appropriate positions include: Senior Executives, Directors, TLs, Product Managers, Senior Engineers.

It’s really important that all Board participants are active in the rest of the organization as well (part of teams that deliver products) in order to **bear the consequences of good and bad architecture decisions** and to have a **good idea of the reality around the problems they’re trying to solve with architecture**.

Another key point is that members of the Board should be replaced constantly with fresh people from the organization. This will ensure new perspectives and prevent empire building.

## Process

A key principle of the Agile Architecture Review Board is that **it should help the organization scale, rather than bogging it down in a bureaucratic process.** So, the following list of processes aims at making sure that this principle is being followed. However, we should be ready to amend the list if we notice the slightest sign of bureaucracy.

1. The Board should meet at least once per week. The **purpose** of this meeting is: 1) to go through outstanding architecture items and 2) to determine what’s the focus of the Board for next week. The **outcome** of the meeting should be 1) resolved and followed-up-on architecture items and 2) tasks with assignees for the next week;
2. Whenever a major architecture decision has to be made, the Board should weigh in its opinion on that decision. In some cases, the Board should be able to block the progress with that decision if they have a **strong objection** and **suggest a viable alternative**.

## Conclusion

By being cross-team, cross-functional and aimed at helping the organization scale, the Agile Architecture Review Board should provide a key element to the organization’s scalability. If the Board is utilized properly, it should provide the vision, purpose and proper structure for the technical organization and architecture. It should also guide its implementation by close collaboration with teams at the organization and by being an active part of the day-to-day endeavors.

## References

* [The Art of Scalability](https://akfpartners.com/books/the-art-of-scalability)
* [Video](https://www.youtube.com/watch?v=dNrF1tZf4Lk) on Agile Architecture Review Boards
