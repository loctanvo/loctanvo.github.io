---
layout: post
title:  "System.Random and random sequences"
origin-url: http://blog.forse.no/system-random-and-random-sequences/
tags: .net math-random
author: "Loc Tan Vo"
disqus-id: b0e32838-2a81-45be-a370-6133b2282df6
---

Actually, this is .NET 101. Probably everyone who has worked with the <code>Random</code> class already knows this. However, last week we encountered a <a href="https://en.wikipedia.org/wiki/Heisenbug" title="Heisenbug">Heisenbug</a> in one of our feature, and this blog post is just a reminder of how the Random class works.

The bug: Our system is generating sample data files. In this specific case, we were generating thousands of sample files. Each file contains some metadata and a time series. It turned out that all these files had the identical same time series values, but correct metadata. When we debugged, everything looked good; all sample files had different time series.

It turned out that we created a new instance of the <code>Random</code> class for each sample generation. What people may not know, is that two <em>different</em> random instances will produce the <em>exact</em> same random sequence if the instances are using the same seed. When not specifying the seed value, the system clock will be used to generate the seed. So, instantiating two random generators in close succession will result in two identical random sequences. You can read more about this in the <a href="https://msdn.microsoft.com/en-us/library/system.random(v=vs.110).aspx" title="Random-documentation">documentation</a>.

Here is a demo of the described behavior.

The code:

<script src="https://gist.github.com/loctanvo/cdb63f7f73a3fd873564.js"></script>

The output:

![MathRandom.Same](http://blog.forse.no/wp-content/uploads/2015/11/MathRandom.Same_.png)

And now, sleeping for <code>1ms</code> between the random generators (line <code>12</code>):

<script src="https://gist.github.com/loctanvo/4061fda8f745127c317b.js"></script>

Which is enough to generate different sequences:

![MathRandom.Sleep](http://blog.forse.no/wp-content/uploads/2015/11/MathRandom.Sleep_.png)

So, lastly, if you want to have true random sequences, within your scope of work, you need to always use the same random instance. A static instance would have solved our problem, but an even quicker fix for us was to just use a new Guid's hashcode as a seed every time.

<script src="https://gist.github.com/loctanvo/d150db1fa98b400eb25e.js"></script>

![MathRandom.Seeded](http://blog.forse.no/wp-content/uploads/2015/11/MathRandom.Seeded.png)
