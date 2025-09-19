---
layout: default
title: Lesson Template
description: Template and guide for creating structured lesson plans
---

<div class="page-header">
    <h1><i class="fas fa-file-alt"></i> Lesson Template</h1>
    <p>Use this template to create structured, effective lesson plans. Copy the markdown below and customize it for your specific lesson needs.</p>
</div>

<div style="background: white; padding: 2rem; border-radius: 10px; margin-bottom: 2rem;">
    <h2><i class="fas fa-info-circle"></i> How to Use This Template</h2>
    <ol style="margin-left: 1rem;">
        <li>Copy the markdown template below</li>
        <li>Create a new file in the <code>_lessons</code> directory</li>
        <li>Name your file descriptively (e.g., <code>multiplication-basics.md</code>)</li>
        <li>Fill in all the sections with your content</li>
        <li>Save and your lesson will automatically appear on the site</li>
    </ol>
</div>

<div style="background: #f8f9fa; padding: 2rem; border-radius: 10px; border-left: 4px solid #667eea;">
    <h3><i class="fas fa-copy"></i> Copy This Template</h3>
    <pre style="background: white; padding: 1rem; border-radius: 5px; overflow-x: auto; font-size: 0.9rem;"><code>---
layout: lesson
title: "Your Lesson Title Here"
subject: "Math"  # Math, Science, Reading, Writing, Social Studies, etc.
grade_level: 3
duration: "45 minutes"
description: "Brief description of what this lesson covers"
topics:
  - "First main topic"
  - "Second main topic" 
  - "Third main topic"
why_important: |
  Explain why this lesson is important for the student's learning.
  What foundational concepts does it build? How does it connect
  to other subjects or real-life applications?
example: |
  Provide a clear, concrete example that demonstrates the
  concept being taught. Make it relatable and engaging.
problem: |
  Present a practice problem or exercise for the student
  to work through. Include step-by-step guidance if needed.
review: |
  Summarize the key points covered in the lesson.
  Include questions to check understanding.
materials:
  - "Item 1 needed for the lesson"
  - "Item 2 needed for the lesson"
  - "Item 3 needed for the lesson"
---

## Lesson Introduction

Start your lesson content here. Provide background information,
context, and engage the student's interest.

## Main Content

This is where you'll put the core teaching content. Break it
into logical sections with clear headers.

### Section 1: First Concept

Explain the first main concept with clear explanations and examples.

### Section 2: Building on the Concept

Show how concepts build on each other and connect.

## Guided Practice

Include activities or exercises the student can do with guidance.

## Independent Practice

Provide opportunities for the student to practice independently.

## Extension Activities

Optional: Include additional activities for students who want
to explore the topic further.
</code></pre>
</div>

<div style="background: white; padding: 2rem; border-radius: 10px; margin-top: 2rem;">
    <h3><i class="fas fa-lightbulb"></i> Template Field Explanations</h3>
    
    <div style="margin-top: 1rem;">
        <h4>Front Matter (YAML) Fields:</h4>
        <ul style="margin-left: 1rem;">
            <li><strong>title:</strong> The name of your lesson (shown as the main heading)</li>
            <li><strong>subject:</strong> The subject area (Math, Science, Reading, Writing, Social Studies)</li>
            <li><strong>grade_level:</strong> Target grade level (usually 3 for 3rd grade)</li>
            <li><strong>duration:</strong> How long the lesson should take</li>
            <li><strong>description:</strong> Brief summary for the lesson index page</li>
            <li><strong>topics:</strong> List of main topics covered (shown as bullet points)</li>
            <li><strong>why_important:</strong> Explanation of the lesson's significance</li>
            <li><strong>example:</strong> A concrete example demonstrating the concept</li>
            <li><strong>problem:</strong> Practice problem or exercise</li>
            <li><strong>review:</strong> Summary and comprehension questions</li>
            <li><strong>materials:</strong> List of items needed for the lesson</li>
        </ul>
    </div>
    
    <div style="margin-top: 1.5rem;">
        <h4>Content Sections:</h4>
        <ul style="margin-left: 1rem;">
            <li><strong>Lesson Introduction:</strong> Hook the student's interest and provide context</li>
            <li><strong>Main Content:</strong> Core teaching material, broken into logical sections</li>
            <li><strong>Guided Practice:</strong> Activities with support and guidance</li>
            <li><strong>Independent Practice:</strong> Solo practice opportunities</li>
            <li><strong>Extension Activities:</strong> Optional enrichment for advanced learners</li>
        </ul>
    </div>
</div>

<div style="background: #d4edda; padding: 2rem; border-radius: 10px; border-left: 4px solid #28a745; margin-top: 2rem;">
    <h3><i class="fas fa-star"></i> Best Practices</h3>
    <ul style="margin-left: 1rem;">
        <li><strong>Keep it age-appropriate:</strong> Use language and concepts suitable for 3rd graders</li>
        <li><strong>Include visuals:</strong> Add images, diagrams, or charts when helpful</li>
        <li><strong>Make it interactive:</strong> Include hands-on activities and engagement</li>
        <li><strong>Connect to real life:</strong> Show how concepts apply outside the classroom</li>
        <li><strong>Check understanding:</strong> Include regular comprehension checks</li>
        <li><strong>Accommodate different learning styles:</strong> Include visual, auditory, and kinesthetic elements</li>
    </ul>
</div>

<div style="text-align: center; margin-top: 2rem;">
    <a href="{{ '/lessons/' | relative_url }}" class="btn btn-primary">
        <i class="fas fa-arrow-left"></i> Back to Lessons
    </a>
    <a href="{{ '/_lessons/sample-math-lesson.md' | relative_url }}" class="btn btn-secondary">
        <i class="fas fa-eye"></i> View Sample Lesson
    </a>
</div>