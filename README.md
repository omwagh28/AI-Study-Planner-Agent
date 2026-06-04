# AI Study Planner Agent
Demo Link - https://drive.google.com/file/d/1kiUTYfdRqKTxKoWL7XGYJU7Sp_tCad_q/view?usp=sharing
## Project Overview

AI Study Planner Agent is an Agentic AI workflow built using n8n and Google Gemini. The system helps students manage academic workloads by automatically analyzing assignments, prioritizing tasks, estimating workload and stress levels, generating study schedules, and providing productivity recommendations.

The workflow demonstrates how multiple specialized AI agents can collaborate to solve a real-world planning problem through task decomposition and workflow orchestration.

---

## Problem Statement

Students often struggle to decide:

* Which assignment should be completed first
* How to divide limited study hours
* How to manage workload and stress
* How to create an effective study plan

This project automates the entire decision-making process by using multiple AI agents working together.

---

## Solution

The user provides:

* Assignment list
* Deadlines
* Difficulty levels
* Available study hours

The workflow then:

1. Extracts and structures tasks
2. Prioritizes assignments
3. Analyzes workload and stress level
4. Creates a study schedule
5. Generates productivity recommendations
6. Produces a final student study report

---

## Workflow Architecture

```text
Manual Trigger
      ↓
Student Input
      ↓
Task Extractor Agent
      ↓
Priority Agent
      ↓
Workload Analyzer Agent
      ↓
Stress Level Check (IF)
      ↓
Study Planner Agent
      ↓
Recommendation Agent
      ↓
Final Summary Agent
```

---

## Agent Responsibilities

### 1. Task Extractor Agent

Purpose:

* Extract assignment information
* Convert raw input into structured data

Input:

```json
{
  "assignments": "ML Report - Tomorrow - Hard ..."
}
```

Output:

```json
{
  "tasks": [
    {
      "name": "ML Report",
      "deadline": "Tomorrow",
      "difficulty": "Hard"
    }
  ]
}
```

---

### 2. Priority Agent

Purpose:

* Rank assignments based on urgency and difficulty

Output Example:

```json
{
  "priority_order": [
    "ML Report",
    "DBMS Quiz",
    "CN Lab"
  ]
}
```

---

### 3. Workload Analyzer Agent

Purpose:

* Estimate workload intensity
* Estimate stress level
* Identify the most challenging assignment

Output Example:

```json
{
  "workload_level": "High",
  "stress_level": "High"
}
```

---

### 4. Stress Level Check (IF Node)

Purpose:

* Demonstrates deterministic workflow control
* Routes workflow based on workload analysis

This node represents traditional rule-based logic working alongside AI reasoning.

---

### 5. Study Planner Agent

Purpose:

* Allocate available study hours
* Generate a personalized study schedule

Output Example:

* ML Report → 2.5 Hours
* DBMS Quiz → 1 Hour
* CN Lab → 0.5 Hour

---

### 6. Recommendation Agent

Purpose:

* Generate productivity recommendations
* Suggest effective study techniques
* Warn against common mistakes

Example Recommendations:

* Use focused study sessions
* Break tasks into milestones
* Avoid multitasking

---

### 7. Final Summary Agent

Purpose:

* Consolidate results
* Present a clean student study report

Final Output Includes:

* Priority Task
* Workload Status
* Study Plan
* Recommendations
* Motivation

---

## Technologies Used

* n8n
* Google Gemini API
* Agentic AI Workflow Design
* Prompt Engineering

---

## Key Agentic AI Concepts Demonstrated

### Task Decomposition

Large planning problems are broken into smaller specialized tasks.

### Multi-Agent Collaboration

Multiple AI agents work together to solve a single objective.

### Workflow Orchestration

n8n coordinates information flow between agents.

### Hybrid Intelligence

Combines:

* AI reasoning
* Deterministic IF-node logic

### Personalized Planning

Each workflow execution generates a customized plan based on user inputs.

---

## Sample Input

```json
{
  "assignments": "ML Report - Tomorrow - Hard DBMS Quiz - 4 Days - Medium CN Lab - 5 Days - Easy",
  "available_hours": 4
}
```

---

## Sample Output

```text
STUDENT STUDY REPORT

Priority Task:
ML Report

Workload Status:
High

Study Plan:
1. ML Report - 2.5 Hours
2. DBMS Quiz - 1 Hour
3. CN Lab - 0.5 Hour

Recommendations:
- Use focused study sessions
- Break tasks into milestones
- Avoid multitasking

Motivation:
Stay consistent and focus on one task at a time.
```

---

## Screenshots

Screenshots of workflow execution are available in the screenshots folder.

---

## Future Improvements

* Calendar integration
* Google Tasks integration
* Email reminders
* Dynamic workload tracking
* Multi-day study planning

---

## Author

Om Waghchavare
