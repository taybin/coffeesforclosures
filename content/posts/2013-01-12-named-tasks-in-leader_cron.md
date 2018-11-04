---
title: named tasks in leader_cron
date: 2013-01-12T23:35:29+00:00
author: Taybin Rutkin
---
I&#8217;ve been using [erlcron](https://github.com/erlware/erlcron "erlcron") to run scheduled tasks, but since each node in an erlang cluster would have its own copy, it didn&#8217;t help with having the tasks run in only one location per-cluster. Then I found [leader_cron](https://github.com/jeraymond/leader_cron "leader_cron"), which uses [gen_leader](https://github.com/abecciu/gen_leader_revival "gen_leader") to elect a single node in the cluster to run the tasks.

This is great stuff, but it doesn&#8217;t solve the problem of which node should _schedule_ the task. For this purpose, I added the feature of [named tasks](https://github.com/taybin/leader_cron/tree/named_tasks "named tasks"), so that if you add a task with the same name, you receive a {error, already_exists} response. This way all the nodes can try to schedule the tasks, but only one will succeed.

I&#8217;ve [submitted](https://github.com/jeraymond/leader_cron/pull/1 "pull request") it to the maintainer and I hope he likes it, but it seems useful enough to hold onto even if he has reservations.
