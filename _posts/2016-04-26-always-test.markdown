---
layout: post
title: Test every little change
date: 2016-04-26
---

Yesterday I was dumb enough to roll-in a change on production without testing
it.  Today that backfired.

The change was quite simple -- a service has been moved from one location to
another and I had to change that in a config file.  In a kind of out-of-mind
state, I told everyone that all's good and continued with my daily schedule.
But, you know, changing a not-so-well-designed service's location sometimes
means that you have to migrate its database as well.  And if you don't do that
correctly the simplest thing that could go wrong is to screw up the DB's access
rights.  At voila, you get: `Access denied for user 'someone'@'localhost' 
(using password: YES)` as a response.  And what you expected was just a csv
with some values...

Some rules should be coined out of this situation:

1. No matter how small a change is, test it thoroughly before releasing;
2. Migrating a server shouldn't lead to migrating its database;
3. Be prepared for any kind of response and handle it accordingly.
