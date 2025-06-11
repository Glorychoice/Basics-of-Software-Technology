---
title: Welcome to my first blog experience
---

Software Develoment is really Interesting but you need to pay more attention and more practice!!!

---
---
layout: default
title: Welcome to my first blog experience
---

# 👋 Welcome to My Blog

Software Development is really interesting, but you need to pay more attention and do more practice!!!

---

## 📚 Assignments

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
🗓️ {{ post.date | date: "%B %d, %Y" }}

{{ post.excerpt }}

[Read more →]({{ post.url }})

---
{% endfor %}

---

## 🛰️ About

This website was created by **Glory** at Beihang University to showcase basics of **Software Development**—assignments and project work related to **GNSS signal processing**, **AI-based navigation**, and **geospatial
