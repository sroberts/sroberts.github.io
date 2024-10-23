---
layout: post
title: Getting Started with Synapse
date: 2021-11-02T17:33:08.742Z
tags:
  - intelligence
lastmod: 2024-05-13T16:56:03.876Z
---
If you care about intelligence analysis and management tools (and I presume you do) you’ve hopefully heard about the Vertex Project’s [Synapse](https://github.com/vertexproject/synapse) intelligence… thing. Synapse starts as a little abstract, but once you understand you'll see it's a powerful intelligence workbench and data fusion system. I'm here to say it's actually far easier than you think, worth the time you'll put in, and ultimately you'll find yourself doing far more accurate, fast, and comprehensive analysis.

## What Is Synapse?

Synapse describes itself as: *"a “batteries included” intelligence analysis platform designed to help analysts and algorithms answer complex questions which require the fusion of data across different disciplines"*.

I don't know about you, but that sounds good to me, like a good donut and fresh cup of coffee on a Saturday morning with no plans until Tuesday (since Monday is a holiday) level of good. I admit downloading a Python library doesn't sound like all that, but ultimately that single Python library and some custom code can do almost everything you could ask for.

{{< giphy Jn9Td3EAh6cJfiyg60 >}}

There are two ways to use Synapse. The first is the open-source version you get running `pip3 install synapse` that we're going to explore. This is free, but not always easy (free as in a puppy), and runs as a combination of terminal-based tools. It's a terminal command line interface and requires proper management, but it has 100% of the capabilities of Synapse. Second, if you want advanced capabilities like a graphical user interface, collaboration, managed data, etc. you’ll need to talk to [Vertex](https://vertex.link) their paid offering which includes the Synapse UI (aka Optic). We’re going to save Optic for later and stick to the command line for now that I use almost every day. This is the *try hard approach*, but the concepts will be the same on the CLI or in Optic.

![Synapse CMDR](/images/uploads/synapse-cmdr.png "So this is us now…")

I'm going to assume for now you're a home analyst and want to build your own data curation and intelligence workbench for personal projects. I'm making those assumptions because that's what I did, and Synapse has been my [intelligence analysis workbench and data storage layer](https://sroberts.io/posts/burnt-tips/).

To get started, we're going to discuss two key aspects for getting started with Synapse: the mindset you need and some core concepts you'll lean on. For now this will be philosophical and abstract, but in the future I'll share more concrete getting started steps.

## Mindset

In some ways Synapse is easier to teach a new analyst than an experienced one. Analysis is a series of models, processes, and shortcuts. Synapse has models, processes, and shortcuts as well but a different set than most tools I had used in the past. Ultimately, Synapse is easier, but first we have to unlearn what we’ve learned. The shortcuts experienced analysts lean on are often wrong, for example thinking of a DNS relationship as a connection between a domain and IP, instead of the combination of the two, and we have to unlearn those habits. I've had junior analysts *get it* faster than senior analysts in some cases because they don't have those crutches. I urge you to come into learning Synapse with what Dune calls *[the naive mind](https://dune.fandom.com/wiki/Mentat)*.

And stay hydrated. It’s always important to stay hydrated.

### Mindset: Inductive, Deductive, & Abductive Reasoning 

Let’s start with the most important thing: Most analysts getting started want to use Synapse like [Maltego](https://www.maltego.com). In my experience for most folks that means throwing a ton of data into one view and the analyst *sorts out* what that means. This idea of looking up a large amount of data and then trying to imply understanding is inductive reasoning. Can you do this with Synapse? Sure; but it isn’t where Synapse shines. We need some definitions (these are imperfect, and I try to link to better ones, this is more philosophy than I’m able to be authoritative on):

* **Inductive Reasoning:** Using a series of observations, inductive reasoning attempts to come up with a logical theory that seems to fit that observed data. Induction reasoning relies on a certain amount of probability. For instance, if you saw a pie sitting on a window sill (since in this anecdote we live in a fairy tale) then you assume someone baked it and put it on that sill to cool.
* **Deductive Reasoning:** By the contrast, deductive reasoning is to some extent the same process, but backwards, where the analyst follows the data progressively forward to piece together how an event transpired as each event flows to the next. You use evidence to show someone added ingredients, put a tin in the oven, pulled out a pie, and put it on the window sill.
* **Abductive Reasoning:** I’m still getting better at wrapping my head around this one. Basically, in abductive reasoning, major pieces are well known and understood and minor pieces are more difficult to understand. As a result, we have to use the piece we do know as a framework to focus on the pieces we must reason on. It simplifies the problem by using what we know to focus on what we don’t. *I think.*

> Read more at [Merriam-Webster: 'Deduction' vs. 'Induction' vs. 'Abduction'](https://www.merriam-webster.com/words-at-play/deduction-vs-induction-vs-abduction)

Synapse starts making sense when you start applying abductive reasoning instead of relying on inductive crutches. This works best by generating a series of hypotheses and then creating queries that return the data to either prove or disprove those hypotheses progressively. Now, can you deductively prove everything? No, but by using abductive reasoning we can often come up with a reasonable understanding of complex scenarios.

### Mindset: Tools vs Languages

One of the next fundamental concepts to understand is Synapse isn’t a tool. Not at its core. It *has tools* (`cmdr`, `server`, `feed`, and others) but that’s not what Synapse is.

No, Synapse is actually a software development environment for the Storm programming language. Storm is a programming langue for modeling intelligence data and building tools to manipulate that intelligence. *Why is that important?* Well, it’s simple: you learn tools differently than languages.

Learning GUI-based tools is often a matter of following examples around small uses cases, often done incrementally. When you first learned to use a computer it probably came down to some basics:

* How to turn the computer on?
* How to use the mouse?
* How to use the keyboard?
* How to start basic applications?

These are all pretty simple: What are the basic actions, how do you do them, and what is the expected effect? What happens if you’ve figured out the keyboard but haven’t figured out the mouse? You’re limited, but you can still do some basic commands, allowing you to add new concepts at your own pace.

By contrast, what about learning a programming language like Python or C:

* How do I start everything up (interpreters, services, editors)?
* What data types are available, how are the declared, and which ones do you use when?
* What are actions you can take on that data?
* How do you create your own actions?
* What’s the best way to lay out your program?

Basically data types, syntax, control flow, architecture, and best practices. That’s ultimately far more complicated because while there’s some amount of progression in learning a language, there’s a much higher barrier of entry before you can start doing tasks. It’s ultimately a lot more capable, but it takes a lot more investment.

In my experience when people start using Synapse they often want to use it like a graphical intelligence exploration tool such as Maltego. Start up a Synapse (whatever that means), throw some data around, pivot a bit, and then figure out all the bells and whistles when they need them. Since Synapse is a language more than a tool, this doesn’t work well. People want to see an IP address and don’t understand why they need to review the documentation for `inet:ipv4` and `inet:ipv6`, learn about starting `cmdr`, understand how lifts work, etc.

In the same way that learning Excel is more complicated than learning `calc.exe` learning Storm is more complicated than learning a lot of other intelligence analysis tools, but it’s also infinitely more powerful. It’s an investment of your time to ultimately be able to do considerably more.



What does it take to learn a language rather than a tool? Patience and practice. Understand that you need a higher amount of base understanding before Synapse can be useful. If you’re an analyst, brace yourself for the fact Synapse will take more mental effort than using a basic graph, you’ll spend more time looking up form definitions and syntax than randomly clicking around until you hit the right button. If you’re a manager looking at Synapse prepare for the fact that it’ll be slow-going, your team will need time to get data wrangled, know how to lift data and what command to use (this will be easier if you have at least one person experienced with Synapse to do some initial heavy lifting), etc. In both cases though, like any good investment, the result will be dramatically more than you started with.

## Key Concepts

Still hydrated? I hope so.

Now that you understand the mindset changes it’s time to start understanding the more practical key concepts that rely on your new mindset. Most should some somewhat familiar from classic intelligence analysis texts, they’re that fundamental.

### Key Concepts: A Little Vocabulary

| Term        | Definition                                                                                                                                                                                                                                                        |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Synapse** | The whole shebang, Synapse is the combination of Storm, underlying services, tools, data models, and your own custom additions. Most people end up using Storm and Synapse interchangeably, but Synapse is the whole thing. At least that’s how I think of it.    |
| **Storm**   | The programming language that underlies Synapse. It’s the syntax for describing manipulations you want to do to your intelligence data.                                                                                                                           |
| **Cortex**  | A specific Synapse tool that stores intelligence data you can manipulate using Storm. This is the core service you’ll use for everything, though it’s often supported by other services.                                                                          |
| **Lift**    | Storm's idea of a read operation or search is a lift. We'll talk a lot about these in my next post on Synapse.                                                                                                                                                    |
| **Node**    | The implementation of an atomic piece of data. These can look a little different in different circumstances, but a node is ultimately the representation of everything from the IP `7.7.7.7` to the person `Daniel Craig` to the document `The Foundation`.       |
| **Tag**     | Analysts apply tags to nodes to represent abstract data or categories, most notably assessments. If we said a given IP is a command and control node, we might attach the tag`#cno.c2` to that IPs node. This is a key concept we’ll talk about more in a second. |
| **Form**    | A form is the abstract pattern for a given node. For example `inet:ipv4=7.7.7.7` is a node, but the form would be `inet:ipv4`. Think of it as the category of the data.                                                                                           |
| **Prop**    | A prop is a property of a node, though most often this references a sub property. The form `inet:ipv4` has a handful of props, including ASN. A prop for `inet:ipv4=7.7.7.7` would be `:asn=749`, as in 7.7.7.7 is in the ASN 749.                                |
| **Type**    | At its most basic, types are the building blocks for forms and props. These are fundamentally basic, such a `string`, `int`, `bool`, etc. and build up to make up to model complex types. Every prop and indeed every form has a base type.                       |

Okay, slightly more than a little, but it’s important and now you have this handy table to refer to.

### Key Concepts: Facts vs Assessments

When I started looking at Synapse there were pieces that took a while to gel, but this one was so obvious I felt foolish, even though I’d never seen it before: Synapse distinctly separates facts (as nodes) from assessments (as tags).

![Synapse Meme](/images/uploads/synapse.jpg)

> *Thanks to [@CYINT_dude](https://twitter.com/cyint_dude) for the genius meme concept.*

What do I mean by that? Let’s say we have a bad IP address. That would be a node (defined as something like `inet:ipv4=10.67.41.5`, which is the form `inet:ipv4` which we use to represent IPv4 addresses). The fact that an IP address exists is a fact, indisputable, but the fact it’s bad, say hosting a browser exploit, is an assessment and in fact can change. Given it’s a changeable thing that we believe the assessment is separate from the fact that the IP address exists. Thus, we use a tag. Something like `[ inet:ipv4=10.67.41.5 :asn=0 +#cno.wateringhole ]`.

That separation is crucial when we need to make changes later on. For instance, at some point when someone cleans up that IP and it’s no longer a watering hole. The IP still exists, it still has the same ASN, but the less intrinsic characteristics have changed.

Becoming a good Synapse user means starting to think about the difference between facts (which you need to store in nodes) and assessments (which you apply to nodes as tags). There’s a lot of different data modeling you’ll have to do, but this one is the most important.

### Key Concepts: Form Categories

Something you’ll run into is the categories of forms. [In fact, it has a whole page in the official documentation.](https://synapse.docs.vertex.link/en/latest/synapse/userguides/data_model_form_categories.html#data-model-form-categories) This is another piece of magic that isn’t obvious at first, but becomes something you see other systems get wrong.

| Form Type            | Definition                                                                                                                                                                                                                                                                                                                                       | Example                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------- |
| Simple Forms         | A simple node is precisely what it sounds like; a single obvious value is the core of the node.                                                                                                                                                                                                                                                  | `inet:ipv4=1.2.3.4`                                                         |
| GUID Form            | An extension of a Simple Form GUID Forms have a hash as the value, in circumstances where the node may change or have duplicates values. A good example is `ps:person`, since there could be a limitless number of people with the same names.                                                                                                  | `ps:person=fed9..03a7`                                                         |
| Composite Forms      | Okay, this one is genius. Composite Forms (or what I think of as Fused Forms) is a form where It's not about a single value, but a combination of values. Think of a DNS request. It's a combination of two pieces of data, the domain name and the IP that domain associates with. You need both, and the interesting thing is the combination. | `inet:dns:a=(sroberts.io, 104.198.14.52)`                                   |
| Edge Representations | Composite forms do what simple edges do in most tools, but Synapse also allows direct connections between entities. These come in two varieties: digraph nodes and lightweight edges. Both have reasons, but for now I'd focus on the lightweight edges.                                                                                         | `inet:web:acct=(twitter.com, sroberts) +(authors)> inet:fqdn="sroberts.io"` |

I skipped over a lot, including [generic forms](https://synapse.docs.vertex.link/en/latest/synapse/userguides/data_model_form_categories.html#generic-form) and [digraph forms](https://synapse.docs.vertex.link/en/latest/synapse/userguides/data_model_form_categories.html#digraph-edge-form). You should read up on those from the Synapse documentation.

## [o7](https://www.urbandictionary.com/define.php?term=o7)

Alright, you made it. I originally planned to write a lot more (as if this wasn't already a lot) because this gives the key concepts to get started but doesn’t explain how to do it. That’s fine. I've found sometimes answering the "what is Synapse" question the hardest part. For now take this, digest, and start thinking about how you can use nodes vs assessments and the fact that a DNS resolution makes more sense as fused knowledge than as a line on a graph.

Hopefully by now you can see why I'm not alone about what a Synapse-powered future looks like:

 {{< tweet user="stvemillertime" id=1454122820791934979 >}}

Once you’re done with that, I recommend starting to dig into the Vertex Project [Documentation](https://synapse.docs.vertex.link/en/latest/synapse/intro.html) and [Videos](https://vimeo.com/vertexproject).

Synapse is a long journey and it’s a marathon, not a sprint. And it's worth it. And remember: stay hydrated.