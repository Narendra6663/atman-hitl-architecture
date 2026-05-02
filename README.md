# ATMAN + Human-in-the-Loop (HITL) Architecture

This repository represents the architecture of ATMAN Health OS integrating AI-driven signal detection with human-in-the-loop validation and system-level execution.

## Core Concept

AI detects signals → Human validates → ATMAN ensures execution

## Architecture Diagram

```mermaid
graph TD

A[Health Signal Input] --> B[AI Risk Detection]

B --> C{Human-in-the-Loop Check}

C -->|Approve| D[Decision Confirmed]
C -->|Modify| D
C -->|Reject| B

D --> E[Task Creation]

E --> F[Execution Layer - ATMAN]

F --> G[ASHA Worker]
F --> H[ANM]
F --> I[Doctor]

G --> J[Action Execution]
H --> J
I --> J

J --> K[Outcome Captured]

K --> L[Feedback Loop]

L --> B
