---
title: "Django Tags"
date: 2022-06-19T17:03:29+03:00
cover:
    image: django_tags.png
    alt: 'django tags solution'
    caption: 'django tags solution'
tags: ["django", "python"]
categories: [""]
---

# Intro

Alright, I will just write all the thoughts in my head for now. I am
too excited that I managed tags to work on this site!

The idea was to have page with Blogposts and list all the posts in it.
Then, when I click on the posts, I wanted to be able to read it. Then,
if I click on any tags associated with that posts, I wanted to get a
list of other posts with the same tags.

This task proved to be a 2 day headache for me, django novice dude. I
have seen people using djangotaggit package, but dint want myself to
get involved in it, since I knew that somehow, it should be possible
to create this functionality by django itself.

# Body

I am not even sure what part of code I should share here.. I want to
share all the steps that took me to reach the result, but that would
just be a too long post and this blog is not even finished yet, so
yeah… let me just share a key piece.

```python
def tag(request, pk_test):
    tag = Tag.objects.get(id=pk_test)
    # postauskai = Blog_post.objects.filter(tags__name='emacs')
    postauskai = tag.blog_post_set.all()
    context = {'tag': tag, 'postauskai': postauskai}

    return render(request, 'base/tag.html', context)
```

This, above, is my final result. First of all, this piece:

```python
postauskai = Blog_post.objects.filter(tags__name='emacs')
```

After a day of fiddling, using this line I have finally managed to
output SOMETHING into the tag.html template. Now I could filter by
tag. Was super happy about it. Learned that I can put as many things
in the context are as I want, as this video -Rendering Data to
Templates | Template Tags | Django (3.0) Crash Course Tutorials (pt 8)
has proved it to be possible.

Then I skimmed though another video of his in this playlist and
noticed that he is doing something very similar that I am trying to
achive. He wants to output all the orders of a single customer. Well,
that is exaclty what I want to do. Output all the posts of a single
tag. Digging through a few of his videos I have noticed him using
_setDatabase Model Queries | Django (3.0) Crash Course Tutorials (pt
7).That was it. It basically queries the childer on the thingie? Not
sure exactly how it works and what it does, but I knew this is the
thing for me right when I saw it.

I used it and vuolia. The posts that have a certain tag appeared
inside that tags page. AMAZING!!

# Final config

I then had to step back and think how to make a link to that specific
blog post. This worked.

```python
{% extends 'app/main.html' %}

{% block content %}
    <h1>{{tag.name}}</h1>
    <hr/>
    {% for x in postauskai %}
        <p>{{x.created|date:'Y-m-d'}} - <a href="{% url 'blog_post' x.id %}">{{x.title}}</a></p>
    {% endfor %}
{% endblock content %}
```

AMAZING!! I am done and I can not believe I did it. [Link to Github project.](https://github.com/arvydasg/django_blog)
