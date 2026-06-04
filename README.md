# AI Study Planner & Assignment Prioritizer

## Overview

AI Study Planner & Assignment Prioritizer is an Agentic AI workflow built using n8n and Google Gemini. The system helps students organize their academic workload by analyzing assignments, prioritizing them based on urgency and difficulty, and generating a personalized study schedule.

The workflow demonstrates agentic design principles such as task decomposition, specialized AI roles, workflow orchestration, and structured outputs.

---

# Problem Statement

Students often have multiple assignments with different deadlines and difficulty levels. Determining which task should be completed first and how to allocate limited study hours can be challenging.

This project addresses that problem by automatically:

* Extracting assignment details
* Prioritizing assignments
* Creating a study schedule
* Providing actionable recommendations

---

# Objective

The objective of this workflow is to transform raw assignment information into a structured study plan through multiple specialized AI agents.

Input:

* Assignment descriptions
* Deadlines
* Difficulty levels
* Available study hours

Output:

* Structured assignment data
* Priority ranking
* Personalized study schedule

---

# Workflow Architecture

Student Input

↓

Task Extractor Agent

↓

Priority Agent

↓

Study Planner Agent

---

# Agent Descriptions

## 1. Task Extractor Agent

### Purpose

Converts unstructured assignment descriptions into structured data.

### Input

ML Report - Tomorrow - Hard

DBMS Quiz - 4 Days - Medium

CN Lab - 5 Days - Easy

### Output

* Assignment Name
* Deadline
* Difficulty

### Role

This agent acts as the information extraction layer of the workflow.

---

## 2. Priority Agent

### Purpose

Analyzes extracted assignments and determines the order in which tasks should be completed.

### Decision Factors

* Deadline urgency
* Assignment difficulty

### Output

Priority ranking of assignments.

### Role

This agent performs reasoning and prioritization.

---

## 3. Study Planner Agent

### Purpose

Creates a study schedule based on assignment priorities and available study hours.

### Input

* Priority ranking
* Available study hours

### Output

A detailed study plan with time allocation for each assignment.

### Role

This agent converts priorities into actionable recommendations.

---

# Sample Execution

## Input

Assignments:

* ML Report – Tomorrow – Hard
* DBMS Quiz – 4 Days – Medium
* CN Lab – 5 Days – Easy

Available Study Hours:

* 4 Hours

---

## Priority Ranking Generated

1. ML Report
2. DBMS Quiz
3. CN Lab

---

## Study Plan Generated

00:00 – 02:00 → ML Report

02:00 – 03:15 → DBMS Quiz

03:15 – 04:00 → CN Lab

---

# Technologies Used

## n8n

Used for workflow orchestration and agent coordination.

## Google Gemini

Used as the Large Language Model powering all AI agents.

## Gemini Flash Model

Provides reasoning, extraction, prioritization, and planning capabilities.

---

# Agentic AI Concepts Demonstrated

This project demonstrates the following Agentic AI concepts:

* Task Decomposition
* Multi-Agent Workflow Design
* Specialized Agent Roles
* Sequential Reasoning
* Structured Outputs
* Workflow Orchestration
* AI-Powered Planning
* Decision Making

---

# Why This Is Agentic AI

This system is not a simple chatbot.

Instead of solving the entire problem with a single prompt, the workflow breaks the problem into multiple specialized stages:

1. Information Extraction
2. Prioritization
3. Planning

Each agent performs a distinct responsibility and passes its output to the next agent, creating a collaborative multi-agent workflow.

---

# Future Improvements

Potential enhancements include:

* Google Calendar Integration
* Deadline Notifications
* Email Reminders
* Team Project Planning
* Dynamic Schedule Optimization
* Mobile Application Integration

---

# Repository Contents

README.md

workflow.json

screenshots/

* workflow.png
* extractor-output.png
* priority-output.png
* planner-output.png

---

# Author

Developed as part of the Agentic Workflow Design and n8n Demo Assignment.

Built using n8n and Google Gemini.
