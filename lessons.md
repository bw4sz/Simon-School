---
layout: default
title: Lessons
description: Browse all available lesson plans organized by subject and topic
---

<div class="page-header">
    <h1><i class="fas fa-book-open"></i> Lesson Plans</h1>
    <p>Explore our collection of structured lesson plans designed for 3rd grade learning. Each lesson includes topics, explanations, examples, and practice problems.</p>
</div>

<div class="search-filter-section">
    <div class="search-box">
        <input type="text" id="search-input" placeholder="Search lessons..." style="width: 100%; padding: 0.75rem; border: 1px solid #ddd; border-radius: 5px; font-size: 1rem;">
    </div>
    
    <div class="filter-buttons" style="margin-top: 1rem; text-align: center;">
        <button class="filter-btn active" data-filter="all" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">All Subjects</button>
        <button class="filter-btn" data-filter="math" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">Math</button>
        <button class="filter-btn" data-filter="science" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">Science</button>
        <button class="filter-btn" data-filter="reading" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">Reading</button>
        <button class="filter-btn" data-filter="writing" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">Writing</button>
        <button class="filter-btn" data-filter="social-studies" style="margin: 0.25rem; padding: 0.5rem 1rem; border: 1px solid #ddd; background: white; border-radius: 5px; cursor: pointer;">Social Studies</button>
    </div>
</div>

<div class="content-grid">
    {% assign sorted_lessons = site.lessons | sort: 'title' %}
    {% for lesson in sorted_lessons %}
    <div class="content-card" data-subject="{{ lesson.subject | downcase | replace: ' ', '-' }}">
        <div class="content-card-header">
            <h3>{{ lesson.title }}</h3>
            <div class="lesson-meta">
                {% if lesson.subject %}
                <span class="subject-tag">{{ lesson.subject }}</span>
                {% endif %}
                {% if lesson.grade_level %}
                <span class="grade-tag">Grade {{ lesson.grade_level }}</span>
                {% endif %}
                {% if lesson.duration %}
                <span class="duration-tag"><i class="fas fa-clock"></i> {{ lesson.duration }}</span>
                {% endif %}
            </div>
        </div>
        <div class="content-card-body">
            {% if lesson.description %}
            <p>{{ lesson.description }}</p>
            {% elsif lesson.why_important %}
            <p>{{ lesson.why_important | strip_html | truncate: 150 }}</p>
            {% else %}
            <p>A structured lesson plan covering important {{ lesson.subject | default: "educational" }} concepts.</p>
            {% endif %}
            
            {% if lesson.topics %}
            <div class="lesson-topics" style="margin-top: 1rem;">
                <strong>Topics:</strong>
                <ul style="margin-top: 0.5rem; margin-left: 1rem;">
                    {% for topic in lesson.topics limit: 3 %}
                    <li>{{ topic }}</li>
                    {% endfor %}
                    {% if lesson.topics.size > 3 %}
                    <li><em>... and {{ lesson.topics.size | minus: 3 }} more</em></li>
                    {% endif %}
                </ul>
            </div>
            {% endif %}
            
            <div style="margin-top: 1rem;">
                <a href="{{ lesson.url | relative_url }}" class="btn btn-primary">
                    Start Lesson <i class="fas fa-arrow-right"></i>
                </a>
            </div>
        </div>
    </div>
    {% endfor %}
    
    {% if site.lessons.size == 0 %}
    <div class="content-card">
        <div class="content-card-header">
            <h3>No Lessons Yet</h3>
            <span class="subject-tag">Getting Started</span>
        </div>
        <div class="content-card-body">
            <p>You haven't added any lessons yet. Start by creating your first lesson using our template!</p>
            <a href="{{ '/lesson-template/' | relative_url }}" class="btn btn-primary">
                Create First Lesson <i class="fas fa-plus"></i>
            </a>
        </div>
    </div>
    {% endif %}
</div>

<div class="page-footer" style="margin-top: 3rem; text-align: center; padding: 2rem; background: white; border-radius: 10px;">
    <h3><i class="fas fa-lightbulb"></i> Need Help Creating Lessons?</h3>
    <p>Check out our lesson template to understand the structure and format we recommend for effective learning.</p>
    <a href="{{ '/lesson-template/' | relative_url }}" class="btn btn-secondary">
        <i class="fas fa-file-alt"></i> View Lesson Template
    </a>
</div>