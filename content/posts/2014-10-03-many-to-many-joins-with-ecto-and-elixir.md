---
title: Many to Many joins with Ecto and Elixir
date: 2014-10-03T09:48:03+00:00
author: Taybin Rutkin
---
[Ecto](https://github.com/elixir-lang/ecto) is an DSL for writing queries and interacting with databases in [Elixir](http://elixir-lang.org/).  It has a style similar to ActiveRecord, but since there aren’t objects, you can’t really call it an ORM.

Like [ActiveRecord](http://guides.rubyonrails.org/association_basics.html), it has `has_many` and `belongs_to`, but it doesn’t have `has_many :through` yet. Here is how I implemented a [DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph) using a many-to-many join in Ecto anyways

The basic idea is I have a Nodes table.  And each Node can have multiple parents and multiple children.  The most straightforward implementation of this is to have a many-to-many join table and then use that with INNER JOIN to query for parents or children.

First, I needed to create the tables using Ecto’s migration feature.

{{<gist taybin ffc8c18f9c8459f5f47a>}}

Then I define the models using the Ecto model DSL.

{{<gist taybin c5e343c16525b4d6265c>}}

This wasn&#8217;t quite enough though. I ran into trouble getting Node to preload its children and parents via NodeToNode. I ended up adding help functions to the Node module.

{{<gist taybin 16a30c08b73ae76a72be>}}

This now lets me write an association.

{{<gist taybin 3cf9c9f47a800d122632>}}

This works as far as I can tell with my unittests. I&#8217;m not completely comfortable with Ecto&#8217;s association proxy, so there might be a better way to do this that is more idiomatic. I hope that `has_many :through` [support is added soon](https://github.com/elixir-lang/ecto/issues/183) so I can concentrate on my business logic instead of mundane joins. I think more documentation of reading and writing associations is necessary.

If you know a better way to express this, please let me know.
