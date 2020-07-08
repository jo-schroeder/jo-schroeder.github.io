---
layout: post
title: "Unmasking methods in data journalism"
description: "Methods comprehension is a key, yet often overlooked, facet of data literacy."
keywords: "Data journalism, methods, election, data literacy"
categories: blog
---

*Note: This is repost of an article I worked on in February 2019 for my Digital Journalism class portfolio.* <a href="http://digitaljournalism.blogs.wm.edu/2020/03/02/unmasking-methods-data-journalism/"> The original article can be found here.</a>

With the Democratic primary underway, voters are looking to political journalism for election recaps and predictions. Innovations in data journalism have made in-depth analyses more accessible than ever for the public. <a href="http://digitaljournalism.blogs.wm.edu/2020/02/17/coronavirus-disease-panic-lack-ethical-journalism/">In my last blog post</a>, I compared how different visualizations of the coronavirus outbreak can affect public response. In this post, I will be focusing on how data journalists use statistics and methods to inform their writing and attempts to openly discuss methods with a data-literate audience.

## Background: The 2016 Election

In the 2016 election, many consumers of data journalism were shocked when Donald Trump won the presidency. <a href="https://www.nytimes.com/interactive/2016/upshot/presidential-polls-forecast.html?_r=0#other-forecasts">The New York Times</a> put Trumps’ odds at winning at 15%. <a href="https://projects.fivethirtyeight.com/2016-election-forecast/">Five Thirty Eight</a>, a well-respected political statistics blog, put Trump's chances at 28.6%. After the election, Five Thirty Eight’s creator Nate Silver <a href="https://fivethirtyeight.com/features/why-fivethirtyeight-gave-trump-a-better-chance-than-almost-anyone-else/">published a blog post justifying the prediction</a>, touting his methods as flexible to opinion polling errors. In the final paragraph of his post, Silver says he believes the public should have been “better prepared” for a Trump win. Though Five Thirty Eight makes a great effort to educate their readers on the nuances of their statistical methods, it is unclear if the data literacy of the public is where Silver expects it to be.

<figure>
<a href="https://www.nytimes.com/interactive/2016/upshot/presidential-polls-forecast.html?_r=0#other-forecasts"><img class="size-medium wp-image-5995" src="http://digitaljournalism.blogs.wm.edu/files/2020/03/Screen-Shot-2020-03-02-at-1.59.33-PM-300x61.png" alt="From the New York Times article, &quot;2016 Election Forecast: Who Will Be President?&quot;" height="70" <figcaption> "From the New York Times article, '2016 Election Forecast: Who Will Be President?'" </figcaption> /></a>
</figure>

<a href="https://fivethirtyeight.com/features/why-fivethirtyeight-gave-trump-a-better-chance-than-almost-anyone-else/"><img class="size-medium wp-image-5996" src="/assets/images/methods-fivethirtyeight.png" alt="From Five Thirty Eight's &quot;Why Five Thirty Eight Gave Trump a Better Chance Than Everyone Else.&quot;" width="252" height="300" caption = "From Five Thirty Eight's 'Why Five Thirty Eight Gave Trump a Better Chance Than Everyone Else.'"/></a>

## The 2020 Democratic Primary

After the South Carolina primary on February 29<sup>th</sup>, <a href="https://www.washingtonpost.com/politics/2020/03/01/south-carolinas-turnout-makes-bidens-win-even-more-impressive/?arc404=true">the Washington Post published an article on the changes in turnout</a> from the 2016 primaries. Turnout is not the most common electoral statistic to see reporting on, and it certainly tells a different story than vote margins. The Post uses turnout in this article to suggest that Biden is, “(attracting) different types of energized Democratic voters” and by disaggregating turnout by race, that these voters are largely white.

<a href="https://www.washingtonpost.com/politics/2020/03/01/south-carolinas-turnout-makes-bidens-win-even-more-impressive/?arc404=true"><img class="size-medium wp-image-6000" src="/assets/images/methods-wpsc.png" alt="From the Washington Post's &quot;How Turnout in South Carolina makes Biden's win more impressive.&quot;" width="300" height="281" caption = "From the Washington Post's 'How Turnout in South Carolina makes Biden's win more impressive.'"/></a>

Lenny Bronner, a contributor to this article and a data scientist at the Post, is a main contributor to a new blog, <a href="https://washpost.engineering/">PostCode</a>, dedicated to telling the backend stories of the Washington Post’s articles. In the past, <a href="https://washpost.engineering/2019/11/01/how-the-washington-post-estimates-turnout-on-election-nights/">Bronner has blogged on how the methods used by the Post to predict turnout on election nights</a>. Bronner explains that the usual metric, precincts reporting, “<a href="https://observablehq.com/@palewire/election-results-challenge-precincts-reporting">can mislead readers</a>.” In a recent post, <a href="https://washpost.engineering/2020/02/29/how-the-washington-post-estimates-outstanding-votes-during-primaries/">Bronner dives into a method the Post is using to estimate primary elections</a>. This method, looking at voter flow from one primary cycle to the next, estimates how voter preferences change from one primary to the next. The Post, then, is not only making an effort to diversify statistical methods used to tell political stories but explain those methods to readers. Bronner has not yet responded for comment to this story.[^1]

<a href="https://washpost.engineering/2020/02/29/how-the-washington-post-estimates-outstanding-votes-during-primaries/"><img class="size-medium wp-image-6001" src="/assets/images/methods-wpflows.png" alt="From PostCode's blog &quot;How the Washington Post Estimates Outstanding Votes During Primaries.&quot;" width="239" height="300" caption = "From PostCode's blog 'How the Washington Post Estimates Outstanding Votes During Primaries.'' The graph shows how Bronner's model estimates how voters shift preferences from one primary election to the next.[/caption]" /></a>

On the audience side, it is still challenging to tell how methods in political data journalism are interpreted. For consumers of data journalism, it can be difficult to parse through the intricacies of different statistical methods used for reporting. Especially for organizations using data journalism to inform their work, correctly interpreting what a set of visualizations or metrics says can be crucial, especially come Super Tuesday. Both the W&amp;M Young Democrats and the Williamsburg James City County Democrats have not yet responded for comment to this story.

[^1] Bronner did eventually get back to me, but we have not yet had the time to formally chat.
