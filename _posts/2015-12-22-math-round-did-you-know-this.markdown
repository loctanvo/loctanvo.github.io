---
layout: post
title:  "Math.Round() - Did you know this?"
origin-url: http://blog.forse.no/math-round-did-you-know-this/
tags: .net math-round
author: "Loc Tan Vo"
disqus-id: 8418bede-89c1-43fe-b07d-5520d5ac0e46
---

Our project is delivering calculation heavy software used by engineers. We are performing complex numeric operations, and it's utterly crucial that our software is calculating correctly. Recently, one in our team just encountered that <code>Math.Round()</code> is behaving differently than what we have expected.

When rounding decimals to integers, we expected `Math.Round()` to behave like this:


`2.4 -> 2`
<br>
`2.5 -> 3`

At least that's what we learned at school. Well, it turned out that we were wrong. Here is a tiny program that demonstrates this.

<script src="https://gist.github.com/loctanvo/a7dac5098d788e150e2c.js"></script>

This was the outcome:

<div class="wide">
  <img src="http://blog.forse.no/wp-content/uploads/2015/11/math.round_.default.png" alt="math.round.default" />
</div>

So, here we see that <code>2.5</code> gets rounded to <code>2</code> rather than <code>3</code>. However, for <code>1.5</code> and <code>3.5</code>, it's exactly how we expected it to be.

To quote from the <a href="https://msdn.microsoft.com/en-us/library/3s2d3xkk(v=vs.110).aspx" title="MSDN documentation" target="_blank">documentation</a>:


>Return Value
>Type: System.Decimal
>The integer nearest parameter d. **If the fractional component of d is halfway between two integers, one of which is even and the other odd, the even number is returned.**[...]

Note the emphasized part of. This behavior is actually intended and by design!

So, in order to get <code>Math.Round()</code> to behave how we expected it to be, we needed to specify the <code>MidpointRounding.AwayFromZero</code> like this:

<script src="https://gist.github.com/loctanvo/5b7b61c9fdd5e78443a3.js"></script>

This will give the following outcome:

<div class="wide">
  <img src="http://blog.forse.no/wp-content/uploads/2015/11/math.round_.roundingAwayFromZero.png" alt="math.round.roundingAwayFromZero" />
</div>

Which is exactly what we wanted.
