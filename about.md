---
layout: page
permalink: /about/index.html
title: Aman Agrawal
tags: [Aman, Agrawal, amnagrawal]
imagefeature: fourseasons.jpg
chart: true
---
<figure>
  <img src="{{ site.url }}/images/aman-agrawal.jpg" alt="Aman Agrawal">
</figure>

{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}


My name is **Aman Agrawal**, and this is my personal blog. It currently has {{ site.posts | size }} posts in {{ site.categories | size }} categories which combinedly have {{ total_words }} words, which will take an average reader ({{ site.wpm }} WPM) approximately <span class="time">{{ total_readtime }}</span> minutes to read. {% if featuredcount != 0 %}There are <a href="{{ site.url }}/featured">{{ featuredcount }} featured posts</a>, you should definitely check those out.{% endif %} The most recent post is {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} which was published on {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}. The last commit was on {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }} IST.

I am a final year student, pursuing my B.Tech in *Mathematics and Computing* at [Delhi Technological University](http://www.dtu.ac.in/), formerly known as DCE. I like to develop Android Applications, and have done internships at various startups as Android Developer. Also, I have been working on Machine Learning for quite some time now, and very soon I'll share my projects here. My hobbies include swimming, playing chess, singing, playing guitar, and watching movies and TV shows.

*[DCE]: Delhi College of Engineering
*[IST]: Indian Standard Time

<!---
<figure class="third">
	<a href="{{ site.url }}/images/about/1.jpg"><img src="{{ site.url }}/images/about/1-001.jpg"></a>
	<a href="{{ site.url }}/images/about/2.jpg"><img src="{{ site.url }}/images/about/2-001.jpg"></a>
	<a href="{{ site.url }}/images/about/3.jpg"><img src="{{ site.url }}/images/about/3-001.jpg"></a>
</figure>
<figure class="half">
	<a href="{{ site.url }}/images/about/4.jpg"><img src="{{ site.url }}/images/about/4-001.jpg"></a>
	<a href="{{ site.url }}/images/about/5.jpg"><img src="{{ site.url }}/images/about/5-001.jpg"></a>
</figure>
<figure class="third">
	<a href="{{ site.url }}/images/about/6.jpg"><img src="{{ site.url }}/images/about/6-001.jpg"></a>
	<a href="{{ site.url }}/images/about/7.jpg"><img src="{{ site.url }}/images/about/7-001.jpg"></a>
	<a href="{{ site.url }}/images/about/8.jpg"><img src="{{ site.url }}/images/about/8-001.jpg"></a>
	<figcaption>Doha at its full glory.</figcaption>
</figure>
-->
So, this blog will be about my projects and experiences. In addition to this, I'll be sharing my views on some random topics (lulz :P). I hope to find time to update this blog regularly, and let the readers into some very interesting stuff!
