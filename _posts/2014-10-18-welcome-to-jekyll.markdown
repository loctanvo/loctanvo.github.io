---
layout: post
title:  "Welcome to Jekyll!"
date:   2014-10-18 20:59:26
tags: test
author: "Loc Tan Vo"
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve --watch`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

{% highlight csharp %}
using Fluent.Time.Test.TestUtilities.Data;
using Fluent.Time.Test.TestUtilities.TimeHandling;
using NUnit.Framework;

namespace Fluent.Time.Test
{
    [TestFixture]
    public class ClockTest
    {
        [Test]
        public void OClock_NotSpecified_ReturnsTimeToday()
        {
            TimeMachine.SandBox(time =>
            {
                time.FreezeTo(Some.Time);

                var twoOClock = 2.OClock();

                Assert.That(twoOClock.TimeOfDay.Hours, Is.EqualTo(2));
                Assert.That(twoOClock.TimeOfDay.Minutes, Is.EqualTo(0));
                Assert.That(twoOClock.TimeOfDay.Seconds, Is.EqualTo(0));
                Assert.That(twoOClock.TimeOfDay.Milliseconds, Is.EqualTo(0));
                Assert.That(twoOClock.Date, Is.EqualTo(Day.Today.Date));
            });
        }

        [Test]
        public void OClock_DateSpecified_ReturnsTimeOfThatDate()
        {
            TimeMachine.SandBox(time =>
            {
                time.FreezeTo(Some.Time);

                var twoOClock = 2.OClock(Day.Yesterday);

                Assert.That(twoOClock.TimeOfDay.Hours, Is.EqualTo(2));
                Assert.That(twoOClock.TimeOfDay.Minutes, Is.EqualTo(0));
                Assert.That(twoOClock.TimeOfDay.Seconds, Is.EqualTo(0));
                Assert.That(twoOClock.TimeOfDay.Milliseconds, Is.EqualTo(0));
                Assert.That(twoOClock.Date, Is.EqualTo(Day.Yesterday.Date));
            });
        }
    }
}
{% endhighlight %}


Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
