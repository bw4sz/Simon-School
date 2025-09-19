---
layout: default
title: Daily Schedules
description: Organized daily schedules to keep learning on track with structured time management
---

<div class="page-header">
    <h1><i class="fas fa-calendar-alt"></i> Daily Schedules</h1>
    <p>Well-organized daily schedules to structure learning time effectively. Each schedule includes objectives, time blocks, activities, and notes for successful learning sessions.</p>
</div>

<div class="search-filter-section">
    <div class="search-box">
        <input type="text" id="search-input" placeholder="Search schedules..." style="width: 100%; padding: 0.75rem; border: 1px solid #ddd; border-radius: 5px; font-size: 1rem;">
    </div>
</div>

<div class="content-grid">
    {% assign sorted_schedules = site.schedules | sort: 'date' | reverse %}
    {% for schedule in sorted_schedules %}
    <div class="content-card">
        <div class="content-card-header">
            <h3>{{ schedule.title }}</h3>
            <div class="schedule-meta">
                {% if schedule.date %}
                <span class="date-tag"><i class="fas fa-calendar"></i> {{ schedule.date }}</span>
                {% endif %}
                {% if schedule.day_of_week %}
                <span class="day-tag">{{ schedule.day_of_week }}</span>
                {% endif %}
            </div>
        </div>
        <div class="content-card-body">
            {% if schedule.description %}
            <p>{{ schedule.description }}</p>
            {% else %}
            <p>A structured daily schedule with organized learning activities and time management.</p>
            {% endif %}
            
            {% if schedule.objectives %}
            <div class="schedule-objectives" style="margin-top: 1rem;">
                <strong>Today's Objectives:</strong>
                <ul style="margin-top: 0.5rem; margin-left: 1rem;">
                    {% for objective in schedule.objectives limit: 3 %}
                    <li>{{ objective }}</li>
                    {% endfor %}
                    {% if schedule.objectives.size > 3 %}
                    <li><em>... and {{ schedule.objectives.size | minus: 3 }} more</em></li>
                    {% endif %}
                </ul>
            </div>
            {% endif %}
            
            {% if schedule.activities %}
            <div class="schedule-activities" style="margin-top: 1rem;">
                <strong>Activities ({{ schedule.activities.size }}):</strong>
                <div style="margin-top: 0.5rem;">
                    {% for activity in schedule.activities limit: 2 %}
                    <span style="display: inline-block; background: #f0f0f0; padding: 0.2rem 0.5rem; margin: 0.2rem; border-radius: 3px; font-size: 0.9rem;">
                        {{ activity.name }}
                    </span>
                    {% endfor %}
                    {% if schedule.activities.size > 2 %}
                    <span style="display: inline-block; background: #f0f0f0; padding: 0.2rem 0.5rem; margin: 0.2rem; border-radius: 3px; font-size: 0.9rem;">
                        +{{ schedule.activities.size | minus: 2 }} more
                    </span>
                    {% endif %}
                </div>
            </div>
            {% endif %}
            
            <div style="margin-top: 1rem;">
                <a href="{{ schedule.url | relative_url }}" class="btn btn-primary">
                    View Schedule <i class="fas fa-arrow-right"></i>
                </a>
            </div>
        </div>
    </div>
    {% endfor %}
    
    {% if site.schedules.size == 0 %}
    <div class="content-card">
        <div class="content-card-header">
            <h3>No Schedules Yet</h3>
            <span class="date-tag">Getting Started</span>
        </div>
        <div class="content-card-body">
            <p>You haven't created any daily schedules yet. Start by using our schedule template to plan your first day!</p>
            <a href="{{ '/schedule-template/' | relative_url }}" class="btn btn-primary">
                Create First Schedule <i class="fas fa-plus"></i>
            </a>
        </div>
    </div>
    {% endif %}
</div>

<div class="page-footer" style="margin-top: 3rem; text-align: center; padding: 2rem; background: white; border-radius: 10px;">
    <h3><i class="fas fa-clock"></i> Tips for Effective Scheduling</h3>
    <div style="text-align: left; max-width: 600px; margin: 1rem auto;">
        <ul style="margin-left: 1rem;">
            <li><strong>Start with objectives:</strong> Define what you want to accomplish each day</li>
            <li><strong>Balance activities:</strong> Mix different subjects and types of learning</li>
            <li><strong>Include breaks:</strong> Regular breaks help maintain focus and energy</li>
            <li><strong>Be flexible:</strong> Allow time for unexpected learning opportunities</li>
            <li><strong>Review and adjust:</strong> Update schedules based on what works best</li>
        </ul>
    </div>
    <a href="{{ '/schedule-template/' | relative_url }}" class="btn btn-secondary">
        <i class="fas fa-file-alt"></i> View Schedule Template
    </a>
</div>