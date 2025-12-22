---
title: Bookety Top 100 Books 2025/26
layout: default
---

<div class="reading-list-page">
    <div class="back-link-wrapper">
        {%-include back_link.html-%}
    </div>

    <h1>{{ page.title }}</h1>

    <div class="progress-bar-container">
        {%- assign bookety_books = site.books | where_exp: "book", "book.bookety_rank" -%}
        {%- assign read_count = bookety_books | where: "read_status", "Read" | size -%}
        {%- assign reading_count = bookety_books | where: "read_status", "Reading" | size -%}
        {%- assign total_progress = read_count | plus: reading_count -%}
        {%- assign progress_percent = total_progress | times: 100 | divided_by: 100 -%}

        <div class="progress-stats">
            <p>Progress: {{ read_count }} read + {{ reading_count }} reading = {{ total_progress }}/100 books</p>
        </div>

        <div class="progress-bar">
            <div class="progress-fill" style="width: {{ progress_percent }}%"></div>
        </div>
    </div>

    {%- include bookety_list.html -%}
</div>

<style>
.progress-bar-container {
    margin: 2rem 0;
    padding: 1.5rem;
    background: #f5f5f5;
    border-radius: 8px;
}

.progress-stats {
    margin-bottom: 1rem;
    font-size: 1.1rem;
    text-align: center;
}

.progress-bar {
    width: 100%;
    height: 30px;
    background: #e0e0e0;
    border-radius: 15px;
    overflow: hidden;
}

.progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #4CAF50, #45a049);
    transition: width 0.3s ease;
}
</style>
