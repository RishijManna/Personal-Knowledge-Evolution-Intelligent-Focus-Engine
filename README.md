# AI-Powered Personal Learning Engine

A Windows desktop application designed to help users study with focus, understand their learning progress, identify knowledge gaps, and receive personalized practice recommendations.

**Project Status:** Planning / Early Development

## Table of Contents

- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Project Goals](#project-goals)
- [Planned Features](#planned-features)
- [How It Will Work](#how-it-will-work)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Implementation Roadmap](#implementation-roadmap)
- [Privacy and Local AI](#privacy-and-local-ai)
- [Current Status](#current-status)
- [Future Improvements](#future-improvements)

## Overview

The AI-Powered Personal Learning Engine is a planned Windows desktop application that combines focused study sessions with personalized learning progress tracking.

The application will help users select subjects, study with fewer distractions, practice through quizzes, analyze mistakes, and understand their strengths and weaknesses.

Instead of measuring learning only by the number of hours spent studying, the application aims to evaluate learning progress using quiz answers, mistakes, and performance over time.

Existing AI models will be integrated to support question generation, explanations, answer analysis, and personalized learning recommendations.

## Problem Statement

Students often struggle to maintain focus, identify weak topics, revise effectively, and measure their actual understanding of a subject.

Traditional study trackers mainly record time spent studying, but study duration alone cannot determine whether a student has mastered a topic.

This project aims to solve these problems by combining focus management, AI-assisted learning, knowledge tracking, and personalized revision recommendations in one desktop application.

## Project Goals

- Build a dedicated Windows desktop learning application.
- Allow users to select their preferred subjects and topics.
- Provide focused study sessions with a timer.
- Reduce distractions through supported website or application restrictions.
- Track quiz answers, mistakes, and learning performance.
- Identify weak topics and recurring mistakes.
- Estimate topic-level understanding using learning evidence.
- Generate personalized practice and revision recommendations.
- Display learning progress through a dashboard.
- Integrate existing AI models instead of training a model from scratch initially.

## Planned Features

### 1. User Onboarding and Topic Selection

Users will be able to select the subjects and topics they want to learn.

For example:
- Python
- Data Structures and Algorithms
- Mathematics
- Chemistry

The selected topics will help personalize the user's learning experience.

### 2. Focus Mode

Focus Mode will help users concentrate on a selected subject for a specific duration.

Planned capabilities include:

- Study timer.
- Subject and topic selection.
- Study-session tracking.
- Recording completed and interrupted sessions.
- Supported website or application restrictions.
- Study-session summary.

The level of distraction blocking will depend on Windows permissions and the final implementation. System-wide application restrictions may require additional Windows-specific functionality.

### 3. Personal Knowledge Evolution Engine

The Knowledge Evolution Engine will be the core learning component of the application.

It will analyze evidence from the user's learning activities to maintain and update a topic-level understanding of their progress.

Planned capabilities include:

- Tracking topic-wise performance.
- Identifying strengths and weaknesses.
- Analyzing quiz answers and mistakes.
- Identifying recurring errors.
- Updating the learner's estimated knowledge state over time.
- Recommending topics that need revision.
- Suggesting suitable practice questions based on performance.

The system will use actual learning evidence rather than treating study time alone as proof of mastery.

### 4. AI-Assisted Learning

The application will integrate an existing generative AI model to support learning-related tasks.

Planned capabilities include:

- Generating practice questions.
- Explaining difficult concepts in simple language.
- Evaluating submitted answers.
- Providing feedback on mistakes.
- Suggesting revision activities.
- Supporting personalized learning recommendations.

The AI model will be one component of the application, not the entire Knowledge Evolution Engine.

### 5. Learning Dashboard

The dashboard will provide a clear overview of the user's learning progress.

Planned information includes:

- Total study time.
- Completed study sessions.
- Topic-wise performance.
- Strengths and weaknesses.
- Repeated mistakes.
- Learning progress over time.
- Recommended topics for the next study session.

## How It Will Work

The intended workflow is:

1. The user selects subjects and topics.
2. The user starts a focused study session.
3. The user studies and completes quizzes or other learning activities.
4. The application records answers and performance.
5. The Knowledge Evolution Engine analyzes the collected learning evidence.
6. The AI component generates questions, explanations, or feedback when required.
7. The learner's knowledge profile is updated.
8. The dashboard displays progress and recommends what to practice or revise next.

This workflow will be implemented gradually during development.

## Technology Stack

| Component | Planned Technology | Purpose |
|---|---|---|
| Desktop Application | Electron | Build a Windows desktop application |
| Frontend | React | Create the user interface and dashboard |
| Backend | Python and FastAPI | Handle application logic and API requests |
| Database | SQLite | Store user settings, sessions, answers, and learning records |
| Local AI Integration | Ollama | Run compatible AI models locally |
| AI Model | Compatible local model or external model API | Generate questions, explanations, and feedback |
| Development Environment | Visual Studio Code | Write and manage project code |
| Packaging | Electron-compatible packaging tools | Package the application for Windows |

The technology stack is planned and may be adjusted as implementation progresses.

## System Architecture

The application will use a modular architecture in which different components work together.

```text
Windows Desktop Application
          |
          v
   Electron + React
     User Interface
          |
          v
 Python + FastAPI
      Backend
          |
    +-----+------+
    |            |
    v            v
  SQLite     AI Integration
  Database   (Ollama or API)
    |            |
    +------+-----+
           |
           v
 Personal Knowledge
  Evolution Engine
           |
           v
 Learning Progress
 and Recommendations

 Windows Focus Module
 - Study timer
 - Session tracking
 - Supported distraction restrictions
```

The frontend will handle user interaction, the backend will manage application logic, and the database will store learning records.

The Knowledge Evolution Engine will analyze learning evidence and update the user's knowledge profile. The AI model will assist with selected learning tasks.

## Implementation Roadmap

### Phase 1: Project Setup

- Set up the project in Visual Studio Code.
- Create the initial Electron and React application.
- Establish the project folder structure.
- Run the basic desktop application.

### Phase 2: User Interface

- Build the onboarding screen.
- Add subject and topic selection.
- Create the main dashboard.
- Design the study-session screen.

### Phase 3: Backend and Database

- Set up Python and FastAPI.
- Create the SQLite database.
- Store user preferences and learning records.
- Connect the frontend with the backend.

### Phase 4: Focus Mode

- Implement the study timer.
- Track study sessions.
- Record completed and interrupted sessions.
- Implement supported distraction-blocking functionality.

### Phase 5: AI Integration

- Integrate Ollama with a compatible local model or evaluate an external AI API.
- Generate practice questions.
- Provide concept explanations.
- Analyze submitted answers.
- Generate feedback on mistakes.

### Phase 6: Knowledge Evolution Engine

- Create the initial topic-level knowledge profile.
- Track performance across multiple attempts.
- Identify weak topics and recurring errors.
- Update estimated knowledge levels using learning evidence.
- Generate personalized revision recommendations.

### Phase 7: Integration and Testing

- Connect all major components.
- Test the complete learning workflow.
- Check database operations and error handling.
- Evaluate AI response quality.
- Test recommendation accuracy and progress calculations.
- Verify Windows compatibility.

### Phase 8: Windows Application Packaging

- Package the application for Windows.
- Test application installation and startup.
- Document setup instructions.
- Prepare the initial distributable version.

## Privacy and Local AI

Ollama is being considered for running compatible AI models locally on the user's computer.

Local AI can reduce dependence on external AI services and avoid per-request API charges for local inference.

However, local models require sufficient system resources, including RAM, storage, and processing power. Downloading models requires an internet connection, although local inference can generally work offline after setup.

If an external AI API is used, its pricing and data-handling policies will need to be considered.

The final data flow and privacy behavior will be documented as implementation decisions are finalized.

## Current Status

The project is currently in the planning and initial setup stage.

- [ ] Create the initial desktop application.
- [ ] Build the first user interface screens.
- [ ] Set up the backend.
- [ ] Create the database.
- [ ] Implement Focus Mode.
- [ ] Integrate an AI model.
- [ ] Build the Knowledge Evolution Engine.
- [ ] Develop the learning dashboard.
- [ ] Add personalized recommendations.
- [ ] Test and package the Windows application.

