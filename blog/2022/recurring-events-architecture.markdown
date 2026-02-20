---
layout: default
title:  "Recurring events architecture"
date:   2022-06-12
parent: 2022
grand_parent: Blog
has_children: false
categories: architecture
tags:
    - architecture
---

# The challenge

On a well-known Romanian development forum I found a [nice challenge](https://devforum.ro/t/cum-stochez-evenimente-recurente-in-db-si-cum-le-interoghez-dupa/17698) from the administrator himself. The question was formulated along the lines of "how do I store calendar events in the database" with events categorised as occuring:

1. once, at a certain hour,
1. once, in a defined time interval, 
1. once, duration full day, 
1. once, spans across an interval of days, 
1. recurent, with or without an end date. 

It listed as requirements quite a few query-ing challenges for 

- all events in a date range
- filter valid events
- sort by occurence date

Apparently the troublesome part was the troublesome part, specifically when needing to perform sorting and/or filtering.

This immediately trigered nice memories of a system I built a few years ago, when I had to solve an interesting banking problem: issuing a credit card required a lot of complex project management tasks, some recurring and some not, whihle needing to take into account each supplier bank holiday. Mind you, credit card issuers work globally, and digitizing such a system taught me everything I didn't yet know about 3rd party suppliers and their timezones, depending tasks, and recurring events.

![use_cases](../diagrams_dest/recurring-events-architecture/use_cases.png)
