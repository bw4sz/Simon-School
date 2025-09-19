---
layout: default
title: Home
description: Welcome to Simon's School - your personalized learning hub for 3rd grade education
---

<section class="hero">
    <h1><i class="fas fa-graduation-cap"></i> Welcome to Simon's School</h1>
    <p>Your personalized learning hub for 3rd grade education. Organized lesson plans, daily schedules, and engaging activities to make learning fun and effective.</p>
</section>

<section class="features">
    <div class="feature-card">
        <i class="fas fa-book-open"></i>
        <h3>Structured Lessons</h3>
        <p>Well-organized lesson plans covering all subjects with clear objectives, examples, and practice problems.</p>
        <a href="{{ '/lessons/' | relative_url }}" class="btn btn-primary">View Lessons</a>
    </div>
    
    <div class="feature-card">
        <i class="fas fa-calendar-alt"></i>
        <h3>Daily Schedules</h3>
        <p>Organized daily schedules to keep learning on track with time management and activity planning.</p>
        <a href="{{ '/schedules/' | relative_url }}" class="btn btn-primary">View Schedules</a>
    </div>
    
    <div class="feature-card">
        <i class="fas fa-star"></i>
        <h3>Progress Tracking</h3>
        <p>Track learning progress and celebrate achievements with our built-in progress monitoring tools.</p>
        <a href="#progress" class="btn btn-primary">Coming Soon</a>
    </div>
</section>

<section class="recent-content">
    <h2><i class="fas fa-clock"></i> Recent Lessons</h2>
    <div class="content-grid">
        {% assign recent_lessons = site.lessons | sort: 'date' | reverse | limit: 3 %}
        {% for lesson in recent_lessons %}
        <div class="content-card" data-subject="{{ lesson.subject | downcase }}">
            <div class="content-card-header">
                <h3>{{ lesson.title }}</h3>
                {% if lesson.subject %}
                <span class="subject-tag">{{ lesson.subject }}</span>
                {% endif %}
            </div>
            <div class="content-card-body">
                {% if lesson.description %}
                <p>{{ lesson.description }}</p>
                {% elsif lesson.why_important %}
                <p>{{ lesson.why_important | truncate: 150 }}</p>
                {% endif %}
                <a href="{{ lesson.url | relative_url }}">Start Lesson <i class="fas fa-arrow-right"></i></a>
            </div>
        </div>
        {% endfor %}
        
        {% if site.lessons.size == 0 %}
        <div class="content-card">
            <div class="content-card-header">
                <h3>Sample Lesson</h3>
                <span class="subject-tag">Coming Soon</span>
            </div>
            <div class="content-card-body">
                <p>Lessons will appear here once you start adding them. Check out the sample lesson to see the format!</p>
                <a href="{{ '/lessons/sample-math-lesson/' | relative_url }}">View Sample <i class="fas fa-arrow-right"></i></a>
            </div>
        </div>
        {% endif %}
    </div>
</section>

<section class="quick-access">
    <h2><i class="fas fa-rocket"></i> Quick Access</h2>
    <div class="features">
        <div class="feature-card">
            <i class="fas fa-plus"></i>
            <h3>Create New Lesson</h3>
            <p>Ready to add a new lesson? Use our template to create structured, engaging content.</p>
            <a href="{{ '/lesson-template/' | relative_url }}" class="btn btn-secondary">Lesson Template</a>
        </div>
        
        <div class="feature-card">
            <i class="fas fa-clipboard"></i>
            <h3>Create Daily Schedule</h3>
            <p>Plan your day with our schedule template for organized and productive learning sessions.</p>
            <a href="{{ '/schedule-template/' | relative_url }}" class="btn btn-secondary">Schedule Template</a>
        </div>
        
        <div class="feature-card">
            <i class="fas fa-search"></i>
            <h3>Browse All Content</h3>
            <p>Explore all available lessons and schedules with our organized content browser.</p>
            <div style="display: flex; gap: 0.5rem; justify-content: center; margin-top: 1rem;">
                <a href="{{ '/lessons/' | relative_url }}" class="btn btn-secondary">All Lessons</a>
                <a href="{{ '/schedules/' | relative_url }}" class="btn btn-secondary">All Schedules</a>
            </div>
        </div>
    </div>
</section>