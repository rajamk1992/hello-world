# Jira Concepts -- Epic, Sprint, Task, and Subtask

**Session Notes for Classroom Teaching**

------------------------------------------------------------------------

# 1. Introduction

In Agile project management (commonly used in software companies), work
is organized in structured levels:

Epic → Story/Task → Subtask\
And work is executed inside a Sprint.

Understanding this hierarchy is very important for students.

------------------------------------------------------------------------

# 2. What is an Epic?

An **Epic** is a large feature or major objective of a project.

It is too big to complete in a single sprint.\
So it is broken down into smaller Stories or Tasks.

### Example:

Project: College Management System

Epic: - Student Management Module

This Epic may include: - Add student - Edit student - Delete student -
View student profile

### Key Points:

-   Big goal
-   Contains multiple stories/tasks
-   Can run across multiple sprints

------------------------------------------------------------------------

# 3. What is a Story / Task?

A **Story** (or Task) is a smaller functional requirement under an Epic.

It represents a piece of work that delivers value.

### Example under Student Management Epic:

Stories/Tasks: - Create student registration form - Validate input
fields - Save student data to database - Display student list

### Key Points:

-   Part of an Epic
-   Can be completed within a sprint
-   Assigned to a team member

------------------------------------------------------------------------

# 4. What is a Subtask?

A **Subtask** is a smaller unit of work inside a Story or Task.

It helps divide work clearly.

### Example:

Story: Create student registration form

Subtasks: - Design HTML layout - Add CSS styling - Write backend API -
Connect to database - Unit testing

### Key Points:

-   Exists under a Task/Story
-   Makes work more manageable
-   Assigned individually if needed

------------------------------------------------------------------------

# 5. What is a Sprint?

A **Sprint** is a fixed time period (usually 1--2 weeks) in which
selected tasks are completed.

It is part of the Scrum methodology.

### Sprint Flow:

1.  Sprint Planning -- Select tasks from backlog
2.  Development -- Work on tasks
3.  Testing -- Validate work
4.  Sprint Review -- Demonstration
5.  Sprint Retrospective -- Discuss improvements

### Key Points:

-   Time-boxed (fixed duration)
-   Contains selected Stories/Tasks
-   Goal-oriented

------------------------------------------------------------------------

# 6. Relationship Structure (Hierarchy)

Epic └── Story / Task └── Subtask

Sprint → Contains Stories/Tasks → Helps complete part of an Epic

------------------------------------------------------------------------

# 7. Real-Time Example for Teaching

Imagine building an E-Commerce Website.

Epic: - Payment Integration

Stories: - Integrate Razorpay API - Add payment success page - Add
payment failure handling

Subtasks under "Integrate Razorpay API": - Create API keys - Write
integration code - Handle callbacks - Test transactions

Sprint: - Sprint 1: Complete basic payment integration - Sprint 2: Add
advanced validation & reports

------------------------------------------------------------------------

# 8. Simple Comparison Table

  Level        Size          Example                     Duration
  ------------ ------------- --------------------------- ------------------
  Epic         Very Large    Student Management Module   Multiple sprints
  Story/Task   Medium        Create Registration Form    One sprint
  Subtask      Small         Design HTML Form            Few hours / days
  Sprint       Time Period   2 Weeks Work Cycle          Fixed duration

------------------------------------------------------------------------

# 9. Simple Explanation for Students

Epic → Big Goal\
Story/Task → Part of the Goal\
Subtask → Small work inside task\
Sprint → Time period to complete tasks

------------------------------------------------------------------------

# 10. One-Line Summary

Epic defines WHAT big feature to build.\
Stories define WHAT part to build.\
Subtasks define HOW to build it.\
Sprint defines WHEN to build it.

------------------------------------------------------------------------

End of Session Notes
