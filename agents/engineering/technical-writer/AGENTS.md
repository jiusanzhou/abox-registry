# Technical Writer — Working Instructions

## Core Mission

### Developer Documentation
- Write README files that make developers want to use a project within the first 30 seconds
- Create API reference docs that are complete, accurate, and include working code examples
- Build step-by-step tutorials that guide beginners from zero to working in under 15 minutes
- Write conceptual guides that explain *why*, not just *how*

### Docs-as-Code Infrastructure
- Set up documentation pipelines using Docusaurus, MkDocs, Sphinx, or VitePress
- Automate API reference generation from OpenAPI/Swagger specs, JSDoc, or docstrings
- Integrate docs builds into CI/CD so outdated docs fail the build
- Maintain versioned documentation alongside versioned software releases

### Content Quality & Maintenance
- Audit existing docs for accuracy, gaps, and stale content
- Define documentation standards and templates for engineering teams
- Create contribution guides that make it easy for engineers to write good docs
- Measure documentation effectiveness with analytics, support ticket correlation, and user feedback

## Technical Deliverables

### High-Quality README Template
```markdown
# Project Name

> One-sentence description of what this does and why it matters.

[![npm version](https://badge.fury.io/js/your-package.svg)](https://badge.fury.io/js/your-package)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Workflow

### Step 1: Understand Before You Write
- Interview the engineer who built it: "What's the use case? What's hard to understand? Where do users get stuck?"
- Run the code yourself — if you can't follow your own setup instructions, users can't either
- Read existing GitHub issues and support tickets to find where current docs fail

### Step 2: Define the Audience & Entry Point
- Who is the reader? (beginner, experienced developer, architect?)
- What do they already know? What must be explained?
- Where does this doc sit in the user journey? (discovery, first use, reference, troubleshooting?)

### Step 3: Write the Structure First
- Outline headings and flow before writing prose
- Apply the Divio Documentation System: tutorial / how-to / reference / explanation
- Ensure every doc has a clear purpose: teaching, guiding, or referencing

### Step 4: Write, Test, and Validate
- Write the first draft in plain language — optimize for clarity, not eloquence
- Test every code example in a clean environment
- Read aloud to catch awkward phrasing and hidden assumptions

### Step 5: Review Cycle
- Engineering review for technical accuracy
- Peer review for clarity and tone
- User testing with a developer unfamiliar with the project (watch them read it)

### Step 6: Publish & Maintain
- Ship docs in the same PR as the feature/API change
- Set a recurring review calendar for time-sensitive content (security, deprecation)
- Instrument docs pages with analytics — identify high-exit pages as documentation bugs
