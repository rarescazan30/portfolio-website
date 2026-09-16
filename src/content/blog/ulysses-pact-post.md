---
title: "ulysses pact and cioran's nihilism"
description: "how do you engineer with a clear intention? will imposing constraints converge to meaning, or to nihilism?"
pubDate: 2026-09-03
tag: "article"
---

Have you ever felt like you’re hitting a concrete wall every step you make when building a new project? Your mind keeps levitating towards using another API, even though you know managing so many services would be impossible. Importing this whole library for just one negligible feature is a cheap shortcut that might come back to haunt you. Somewhere deep down, you know you’re losing performance, you can’t modularise properly and you’ll end up with a product that’s not robust. Maybe experience tells you *“doing this right now will prove to be a dead end in a bit”*. *You don’t want that.* You started out with quality and scalability in mind. Yet, this path of least resistance seems so tempting.

I like to envision engineering projects as constantly building layers over layers. The project might be done tomorrow or next year, but your foundation needs to be strong enough to support the weight of all the future features and changes. Software systems accumulate promises. Some are explicit, while others are accidental. Having the ability to design your project in such a way as to effortlessly accommodate as many of the accidental promises is key. Still, an unfortunate thing engineers have to consider is that we can’t predict the future. *Consistently, at least…* So we rely on experience and technique to overcome this hurdle.

Here’s a practical example that’s bound to clear things up. We’re all familiar with the TCP protocol. Imagine you’re building a small backend that uses TCP. You need to send requests like `GET_USER 123\n` and `GET_USER 456\n`. The absolute simplest way to do this would be something like:

```python
data = sock.recv(1024)
request = data.decode()
handle(request)
```

*You’ve made a pact in that exact moment:* a `send()` from your client would always translate into one request on your backend. That is, however, a promise that TCP never made. TCP relies on a byte stream, not a message stream. When your system would get some traffic, you’d end up with scrambled requests like:

```text
GET_US
ER123\n

GET_USER 
456\n
```

Your simple `decode()` and `handle()` would not suffice in this scenario. What you’d need is framing. In this case, that means a simple `[length][payload]` protocol that you impose from the get-go. It’s more work to implement this sort of standard, but not having it from the start would mean all your logic relies on an assumption that’s not always true. Your system fails, your client never gets their data and what seemed to be the simpler solution ends up costing you much more.

So maybe your intuition tells you something is bound to go wrong in the future, unless you impose some constraints from the beginning. Or maybe it doesn’t yet, and you end up having to redo your whole backend a few days before deployment… Having the ability to limit a potentially disastrous choice at timestamp `t + 1` by *deliberately restricting yourself* at timestamp `t` is exactly what Ulysses’ Pact stands for.

In Homer’s *The Odyssey*, Odysseus and his crew have to pass by the Sirens. The consequences of hearing them singing would be fatal. Instead, his crew is instructed to plug their ears with beeswax, so they cannot hear the calling. Still, Odysseus is tempted to hear the song, so he straps himself to the mast, forced to listen to the forbidden calling, while also restricted from giving in and chasing the Sirens.

There’s a very subtle line between feeling powerful and powerless, and Odysseus understands this fully. He physically constrains himself, as he’s tightly strapped to the mast, while his mind fully confronts the Sirens, in a position no man before ever survived. He’s experiencing extreme lucidity, *but at what cost?* Once there, how much does he really want to know?

This gets back to something Cioran wrote about, whether a state of complete lucidity is helpful for us as humans, or, even taken further, whether *it is actually harmful*. He argues that extreme consciousness amplifies the burden of existence. We’re not designed to wholeheartedly consider every single detail. We can’t comprehend the world as it is, so we rely on abstractions, we choose to ignore information, we simplify and cram as much as possible into a few concepts, in order to keep it all together. Abstaining from this leads to nihilism. *Is that, really, what we do in engineering?* I’d argue it’s not. Abstraction in engineering is not a coping mechanism, the way Cioran describes it in our human tendency. Building upon abstractions is a deliberate boundary. Once you add the framing to the TCP payload, the product works. There’s no need to re-question a perfectly working mechanism. We’re actually in the position to draw the line. But the question still stands: Could Ulysses’ Pact overshadow our main goal?

I’d say it won’t. Nihilism is what happens when you can’t stop questioning every assumption and constraint. It’s where you get to when you have no finish line, when lucidity has no stopping point. Odysseus didn’t remain strapped to the mast, listening to the Sirens’ calling. His ship sailed past them. His crew untied him. *The pact worked because it was never meant to be permanent.*

Our minds are weak at times, but we rely on choices we’ve made beforehand to overcome those moments. The projects we work on are tightly related to their scope. The result *is* their meaning, and that will inevitably come, *that is our finish line*. The constraints we impose are constantly anchored to external objects. They have the exit condition that Cioran’s lucidity can’t contain. A product has an edge, while pure consciousness doesn’t.

Homer definitely wasn't thinking about backend engineering when he wrote *The Odyssey*, and you probably weren't thinking about Greek poetry the last time you designed a system. I said at the start that we can't predict the future. What we can do is decide, beforehand, which mistakes we refuse to make later. That's what a pact is.
