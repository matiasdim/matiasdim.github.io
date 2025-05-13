---
layout: default
---
Welcome to my corner of the web! Here, I share a variety of tech topics that inspire me, along with insights from my personal journey. Some content is available in both English and Spanish. To learn more about my professional background, feel free to visit the "About Me" page where you'll find my CV.

<hr />

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span style="color: gray;">{{ post.date | date: "%B %-d, %Y" }}</span>
    </li>
  {% endfor %}
</ul>
