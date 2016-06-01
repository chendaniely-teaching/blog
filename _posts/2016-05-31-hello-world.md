---
layout: post
title: "Hello World"
date: 2016-05-31
description: Hello World
tags:
 - Getting Started
---

Here is a sample post for Jekyll-Clean-Dark theme. 

* Get it from [github](https://github.com/streetturtle/jekyll-clean-dark).
* See the [live demo](http://pavelmakhov.com/jekyll-clean-dark).
* See it [in action on my blog](http://pavelmakhov.com).

This theme was created on top of [Jekyll Clean theme](https://scotte.github.io) by Scotte.

This theme uses some parts of Twitter Bootstrap, which allows it looks nice on a mobile devices using a collapsable nav bar and hiding the sidebar.

Here how it looks like on some portable devices:

![My helpful screenshot]({{ site.baseurl | prepend:site.url}}/images/iphone_portrait.PNG){: .center-image }*iPhone 5 portrait*

![My helpful screenshot]({{ site.baseurl | prepend:site.url}}/images/iphone_landscape.PNG){: .center-image }*iPhone 5 landscape*

![My helpful screenshot]({{ site.baseurl | prepend:site.url}}/images/ipad_portrait.PNG){: .center-image }*iPad mini portrait*

![My helpful screenshot]({{ site.baseurl | prepend:site.url}}/images/ipad_landscape.PNG){: .center-image }*iPad mini landscape*


Some examples of text formating for some common text elements.

# Headers

# Header1

## Header2

### Header3

#### Header4

# Emphasis

Italics: `*asterisks*` -> *asterisks* or `_underscores_` -> _underscores_.

Bold: `**asterisks**` -> **asterisks** or `__underscores__` -> __underscores__.

You also can combine them: `**asterisks and _underscores_**` -> **asterisks and _underscores_**.

# Blockquotes and notes


{% highlight bash %}
>Blockquotes
{% endhighlight bash %}

>Blockquotes

Using very cool [feature](http://kramdown.gettalong.org/quickref.html#block-attributes) of kramdown which allows to assign any attribute to a block-level element I've added note and warning:

{% highlight bash %}
>Note 
{: .note}
{% endhighlight bash %}

>Note 
{: .note}

{% highlight bash %}
>Warning 
{: .note .warning}
{% endhighlight bash %}

>Warning 
{: .note .warning}

# Keyboard buttons

In case you need to show some keyboard shortcut like `Ctrl`{: .key}+`A`{:.key} use following construction:

{% highlight bash %}
`Ctrl`{: .key}+`A`{:.key}
{% endhighlight bash %}

Example of keyboard shortcut in terminal:

`Ctrl`{: .key} + `A`{: .key} = Move cursor to beginning of line
`Ctrl`{: .key} + `E`{: .key} = Move cursor to end of line
`Ctrl`{: .key} + `C`{: .key} = kills the current process.
`Ctrl`{: .key} + `Z`{: .key} = sends the current process to the background.
`Ctrl`{: .key} + `D`{: .key} = logs you out.
`Ctrl`{: .key} + `R`{: .key} = finds the last command matching the entered letters.



## Installation

If you dont't have your own blog you can clone this repository and put your articles in a `_posts` folder.
If you already have your own blog then I think you can clone this repository and copy-paste content keeping your `_posts` folder.

After you will have to set up your `_config.yml`

## License

The content of this theme is distributed and licensed under a [Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode)

> This license lets others distribute, remix, tweak, and build upon your work,
> even commercially, as long as they credit you for the original creation. This
> is the most accommodating of licenses offered. Recommended for maximum
> dissemination and use of licensed materials.

In other words: you can do anything you want with this theme on any site, just please
provide a link to the original theme on github.

This theme includes the following files which are the properties of their
respective owners:

* js/bootstrap.min.js - [bootstrap](http://getbootstrap.com)
* css/bootstrap.min.css - [bootstrap](http://getbootstrap.com)
* js/jquery.min.js - [jquery](https://jquery.com)




## Introduction

This theme supports two types of images:
 
- inline images: ![Battery Widget]({{ site.url | append:site.baseurl }}/images/batWid1.png)

{% highlight html %}
{% raw %}
![Battery Widget]({{ site.url | append:site.baseurl }}/images/batWid1.png)
{% endraw %}
{% endhighlight html %}

- centered images with caption (optionally):
 
![screenshot]({{ site.baseurl | prepend:site.url}}/images/iphone_landscape.PNG){: .center-image }*iPhone 5 landscape*

{% highlight html %}
{% raw %}
![screenshot]({{ site.baseurl | prepend:site.url}}/images/iphone_landscape.PNG){: .center-image }*iPhone 5 landscape*
{% endraw %}
{% endhighlight html %}

You can apply your own styles to image by creating css class with style:

{% highlight css %}
.custom-image
{
// your style
}
{% endhighlight css %}

And then applying your style just after the image in curly brackets with colon:

{% highlight html %}
{% raw %}
[!image](path to image){:.custom-image}
{% endraw %} 
{% endhighlight html %}



## Introduction

For code syntax coloration I'm using Darcula theme from Intellij IDEA, which I've found in this post [Darcula theme for Pygments](http://smasue.github.io/pygments-darcula/).

XML with line numbers (linenos flag), `{{ "{%" }} highlight xml linenos %}`:
{% highlight xml linenos %}
{% raw %}
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom">
  <channel>
    <title>{{ site.name }}</title>
    <description>{{ site.description }}</description>
    <link>{{site.baseurl | prepend:site.url}}</link>
    <atom:link href="{{site.baseurl | prepend:site.url}}/feed.xml" rel="self" type="application/rss+xml" />
    {% for post in site.posts limit:10 %}
      <item>
        <title>{{ post.title }}</title>
        <description>{{ post.content | xml_escape }}</description>
        <pubDate>{{ post.date | date: "%a, %d %b %Y %H:%M:%S %z" }}</pubDate>
        <link>{{post.url | prepend:site.baseurl | prepend:site.url}}</link>
        <guid isPermaLink="true">{{post.url | prepend:site.baseurl | prepend:site.url}}</guid>
      </item>
    {% endfor %}
  </channel>
</rss>
{% endraw %}
{% endhighlight xml %}

JSON:
{% highlight json %}
{"employees":[
    {"firstName":"John", "lastName":"Doe"},
    {"firstName":"Anna", "lastName":"Smith"},
    {"firstName":"Peter", "lastName":"Jones"}
]}
{% endhighlight json %}

SQL:
{% highlight SQL %}
select count(*) as cm_content_nodes
from alf_node nd, alf_qname qn, alf_namespace ns
where qn.ns_id = ns.id
  and nd.type_qname_id = qn.id
  and ns.uri = 'http://www.alfresco.org/model/content/1.0'
  and qn.local_name = 'content';
{% endhighlight SQL %}

Java:
{% highlight java %}
private String getToken(HttpClient client) throws UnsupportedEncodingException{
  Cookie[] cookies = client.getState().getCookies();
  for (Cookie cookie : cookies){
    if (cookie.getName().equals("Alfresco-CSRFToken")){
      return URLDecoder.decode(cookie.getValue(), "UTF-8");
    }
  }
  return null;
}
{% endhighlight java %}



## Analytics
 
#### [Google Analytics](http://www.google.com/analytics/)

To enable Google Analytics create an account [here](https://analytics.google.com). Then add your tracking id in `config.xml`, it should look something like `UA-********-1`
 
#### [Yandex Metrica](http://metrica.yandex.com)
 
To enable Yandex Metrica you need to register, create a 'counter' and then copy-paste it's code in `/_includes/yandex-metrika.html` file.

## Tags

Using tags in Jekyll is a bit tricky topic, I used this approach: [charliepark.org/tags-in-jekyll/](http://charliepark.org/tags-in-jekyll/). You can read technical details there. To simply use tags provide list of tags in post header:

{% highlight bash %}
tags:
 - jekyll
 - analytics
 - tags
 - comments
{% endhighlight bash %}

And then before pushing your changes to github copy generated folder `/_site/tag` in your blog's root folder, since github pages will not generate it automatically.

## Comments

To enable [Disqus](http://disqus.com) register on the site and then just put your name in `_config.xml`. Comments could be switched on and off on per post basis, just put `comments: true` to enable them.



You can have social icons which could lead to your social profile.
Out-of-the box it has: 

<ul class="social-media">
  <li>
    <a title="Github"
      href="https://github.com/{{ site.social.github }}"
      target="_blank"><i class="fa fa-github fa-2x"></i></a>
  </li>
  <li>
    <a title="StackOverflow"
      href="http://stackoverflow.com/users/1252056/{{ site.social.stackoverflow }}"
      target="_blank"><i class="fa fa-stack-overflow fa-2x"></i></a>
  </li>
  <li>
    <a title="LinkedIn"
      href="https://www.linkedin.com/in/{{ site.social.linkedin }}"
      target="_blank"><i class="fa fa-linkedin fa-2x"></i></a>
  </li>
  <li>
    <a title="Instagram"
      href="https://instagram.com/{{ site.social.instagram }}"
      target="_blank"><i class="fa fa-instagram fa-2x"></i></a>
  </li>
  <li>
    <a title="Last.fm"
      href="http://lastfm.com/user/{{ site.social.lastfm }}"
      target="_blank"><i class="fa fa-lastfm fa-2x"></i></a>
  </li>
  <li>
    <a title="RSS"
      href="{{site.url}}/{{ site.social.rss }}"
      target="_blank"><i class="fa fa-rss fa-2x"></i></a>
  </li>
</ul>

They could be setup in `_config.yml`.

To add more icons do following steps:

 - choose an icon you want to use: [Font Awesome Icons](https://fortawesome.github.io/Font-Awesome/icons/)
 - add variable in `_config.yml`
 - add icon in `social.html` with check if variable exists:
 
{% highlight html %}
{% raw %}
 {% if site.social.rss %}
  <li>
    <a title="{{ site.social.<your_social_variable> }}" 
       href="{{site.url}}/{{ site.social.<your_social_variable> }}" 
       target="_blank"><font_awesome_icon></i></a>
  </li>
{% endif %}
{% endraw %}
{% endhighlight html %}
