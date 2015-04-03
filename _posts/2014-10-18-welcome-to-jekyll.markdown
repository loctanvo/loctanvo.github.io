---
layout: post
title:  "Welcome to Jekyll!"
date:   2014-10-18 20:59:26
tags: test liksom bla dingding
author: "Loc Tan Vo"
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve --watch`, which launches a web server and auto-regenerates your site when a file is updated.

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> \- By **Major Nes**, [Recursively rolling tables](http://google.com)

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

## A subtitle that can be really long, so long that it could cause trouble for the page

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

{% highlight csharp linenos%}
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
    }
}
{% endhighlight %}

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

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

## How about a title that is not that long?

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

### Lastly, a `h3` tag

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.

Ut metus velit, efficitur hendrerit dolor eget, dictum posuere metus. Curabitur ut erat nec arcu scelerisque luctus vitae at erat. Nulla vitae eros at massa porta tincidunt ac at enim. Aenean cursus tortor id sem ullamcorper, non tempor mauris hendrerit. Integer in velit eu leo mattis pretium nec at ex. Vivamus eu velit sit amet nulla pharetra scelerisque. Fusce feugiat sit amet lorem vel facilisis. In iaculis fringilla nisl dictum ultrices. Vestibulum tempor ligula a sem volutpat viverra. Curabitur a congue ipsum. Cras fringilla vel tortor eu consequat. Ut consequat molestie mi. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
