---
title: Welcome to my first blog experience
---

Software Develoment is really Interesting but you need to pay more attention and more practice!!!

---
layout: default
title: Home
---

# 📚 My Assignments

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})
🗓️ {{ post.date | date: "%B %d, %Y" }}

{{ post.excerpt }}

[Read more →]({{ post.url }})

---
{% endfor %}

---

## 🛰️About

This website was created by Glory at Beihang University to showcase Basics of Softwar Development (assignments and project work related to **GNSS signal processing**, **AI-based navigation**, and **geospatial applications** for academic publishing principles and technics.

---

## Contact
gloryameh.e@gmail.com  
🌍 Based in: Hangzhou, China | Originally from Nigeria

---

© 2025 Ameh Glory Ene-dugbo-ojo.
