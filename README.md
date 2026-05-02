## System Flow

Signal → AI Detection → Human Validation → Execution → Outcome → Feedback

This is not a linear pipeline.

It is a **closed-loop execution system** where outcomes continuously influence future decisions.

---

### Simple Execution Loop

```mermaid
graph LR
Signal --> AI
AI --> Human
Human --> Action
Action --> Outcome
Outcome --> Feedback
Feedback --> AI
```

---

### Visual Flow Representation

```mermaid
graph TD

A[Health Signal] --> B[AI Detection]

B --> C{Human in the Loop}

C -->|Approve| D[Decision Confirmed]
C -->|Modify| D
C -->|Reject| B

C -->|No Response| X[Escalation Trigger]

X --> Y[Escalated Actor - ANM Doctor Supervisor]

Y --> D

D --> E[Task Creation]

E --> F[ATMAN Execution Layer]

F --> G[ASHA]
F --> H[ANM]
F --> I[Doctor]

G --> J[Action]
H --> J
I --> J

J --> K[Outcome]

K --> L[Feedback Loop]

L --> B
```
