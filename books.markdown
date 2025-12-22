---
title: Books
layout: default
---

<div class="reading-list-page">
    <div class="back-link-wrapper">
        {%-include back_link.html-%}
    </div>

    <h1>{{ page.title }}</h1>

    <div class="bookety-challenge-link" style="margin: 1.5rem 0; padding: 1rem; background: #f0f8ff; border-left: 4px solid #4CAF50; border-radius: 4px;">
        <p style="margin: 0;">
            <strong>📚 Reading Challenge:</strong>
            <a href="{{ site.baseurl }}/bookety-top-100" style="color: #4CAF50; font-weight: bold;">Bookety Top 100 Books 2025/26</a>
        </p>
    </div>

    {%- include book_list.html -%}
</div>
