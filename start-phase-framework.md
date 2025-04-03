# Cursor IDE: START Phase Framework
# Version 1.0

This framework defines the START phase for project initialization and scaffolding in the Cursor IDE. It's designed as a preprocessing phase before entering the RIPER workflow.

## START PHASE OVERVIEW

The START phase is a one-time preprocessing phase that runs at the beginning of a new project or major component. It focuses on project initialization, scaffolding, and setting up the Memory Bank with baseline information.

```mermaid
flowchart TD
    Start[BEGIN START PHASE] --> Req[Requirements Gathering]
    Req --> Tech[Technology Selection]
    Tech --> Arch[Architecture Definition]
    Arch --> Scaffold[Project Scaffolding]
    Scaffold --> Setup[Environment Setup]
    Setup --> Memory[Memory Bank Initialization]
    Memory --> End[TRANSITION TO RIPER]
```

## START PHASE PROCESS

[PHASE: START]
- **Purpose**: Project initialization and scaffolding
- **Permitted**: Requirements gathering, technology selection, architecture definition, project structure setup
- **Entry Point**: User command "BEGIN START PHASE" or "/start"
- **Exit Point**: Transition to RESEARCH mode with "ENTER RESEARCH MODE" after setup is complete

### 1. Requirements Gathering
- Collect and document core project requirements
- Define project scope, goals, and constraints
- Identify key stakeholders and their needs
- Document success criteria
- **Key Questions**:
  - What problem is this project trying to solve?
  - Who are the primary users or stakeholders?
  - What are the must-have features?
  - What are the nice-to-have features?
  - What are the technical constraints?
  - What is the timeline for completion?

### 2. Technology Selection
- Assess technology options based on requirements
- Evaluate frameworks, libraries, and tools
- Make recommendations with clear rationales
- Document technology decisions
- **Key Questions**:
  - What programming language(s) best fit this project?
  - What frameworks or libraries would be most appropriate?
  - What database technology should be used?
  - What deployment environment is targeted?
  - Are there any specific performance requirements?
  - What testing frameworks should be used?

### 3. Architecture Definition
- Define high-level system architecture
- Identify key components and their relationships
- Create initial architectural diagrams
- Document architectural decisions
- **Key Questions**:
  - What architectural pattern is most appropriate?
  - How will the application be structured?
  - What are the key components and their responsibilities?
  - How will data flow through the system?
  - How will the system scale?
  - What security considerations need to be addressed?

### 4. Project Scaffolding
- Set up initial folder structure
- Create configuration files
- Initialize version control
- Set up package management
- Create initial README and documentation
- **Key Actions**:
  - Create the basic folder structure
  - Initialize git repository
  - Set up package manager (npm, pip, etc.)
  - Create initial configuration files
  - Set up basic build process

### 5. Environment Setup
- Configure development environment
- Set up testing framework
- Establish CI/CD pipeline configuration
- Define deployment strategy
- **Key Actions**:
  - Set up local development environment
  - Configure testing framework
  - Create initial test cases
  - Define CI/CD pipeline
  - Document deployment process

### 6. Memory Bank Initialization
- Create and populate all core memory files:
  - projectbrief.md
  - productContext.md
  - systemPatterns.md
  - techContext.md
  - activeContext.md
  - progress.md
- Establish initial .cursorrules file
- **Key Actions**:
  - Create memory-bank directory
  - Create and populate all core memory files
  - Document initial state in activeContext.md
  - Set up progress.md with initial tasks

## PROJECT TEMPLATES

### Standard Project Scaffold Template
```
project-root/
├── src/                           # Source code
│   ├── components/                # UI components (for frontend projects)
│   ├── services/                  # Service layer
│   ├── utils/                     # Utility functions
│   ├── config/                    # Configuration files
│   └── index.js                   # Main entry point
├── tests/                         # Test files
│   ├── unit/                      # Unit tests
│   ├── integration/               # Integration tests
│   └── e2e/                       # End-to-end tests
├── docs/                          # Documentation
│   ├── architecture/              # Architecture diagrams
│   ├── api/                       # API documentation
│   └── guides/                    # User and developer guides
├── scripts/                       # Utility scripts
│   ├── setup.sh                   # Environment setup script
│   └── build.sh                   # Build script
├── memory-bank/                   # Memory Bank files
│   ├── README.md                  # Instructions for using memory files
│   ├── projectbrief.md            # Foundation document defining core requirements and goals
│   ├── productContext.md          # Why this project exists and problems it solves
│   ├── systemPatterns.md          # System architecture and key technical decisions
│   ├── techContext.md             # Technologies used and development setup
│   ├── activeContext.md           # Current work focus and next steps
│   ├── progress.md                # What works, what's left to build, and known issues
│   ├── personal-memory.md         # User's personal preferences and details
│   └── implementation-plans/      # Saved PLAN mode checklists
│       └── README.md              # Instructions for implementation plans
├── .cursorrules                   # Cursor rules file
├── .gitignore                     # Git ignore file
├── README.md                      # Project README
├── LICENSE                        # License file
└── package.json                   # Package configuration (or equivalent)
```

### Technology Decision Template
```markdown
# Technology Decision: [DECISION_NAME]
*Date: [DECISION_DATE]*
*Deciders: [DECISION_MAKERS]*

## Context
[Describe the context and background for this decision]

## Decision Drivers
- [DRIVER_1]
- [DRIVER_2]
- [DRIVER_3]

## Options Considered
### Option 1: [OPTION_1_NAME]
- **Pros**: [LIST_OF_PROS]
- **Cons**: [LIST_OF_CONS]

### Option 2: [OPTION_2_NAME]
- **Pros**: [LIST_OF_PROS]
- **Cons**: [LIST_OF_CONS]

### Option 3: [OPTION_3_NAME]
- **Pros**: [LIST_OF_PROS]
- **Cons**: [LIST_OF_CONS]

## Decision
[Document the selected option and the rationale behind it]

## Consequences
- **Positive**: [POSITIVE_CONSEQUENCES]
- **Negative**: [NEGATIVE_CONSEQUENCES]
- **Neutral**: [NEUTRAL_CONSEQUENCES]

## Implementation Plan
[Brief description of how this decision will be implemented]

---

*This document is part of the project's architectural decision records.*
```

### Architecture Definition Template
```markdown
# System Architecture: [PROJECT_NAME]
*Version: 1.0*
*Date: [CURRENT_DATE]*

## Overview
[High-level description of the system architecture]

## Design Principles
- [PRINCIPLE_1]
- [PRINCIPLE_2]
- [PRINCIPLE_3]

## System Components
### [COMPONENT_1]
- **Purpose**: [PURPOSE]
- **Responsibilities**: [RESPONSIBILITIES]
- **Interfaces**: [INTERFACES]

### [COMPONENT_2]
- **Purpose**: [PURPOSE]
- **Responsibilities**: [RESPONSIBILITIES]
- **Interfaces**: [INTERFACES]

### [COMPONENT_3]
- **Purpose**: [PURPOSE]
- **Responsibilities**: [RESPONSIBILITIES]
- **Interfaces**: [INTERFACES]

## Data Flow
[Description of how data flows through the system]

## APIs
### [API_1]
- **Purpose**: [PURPOSE]
- **Endpoints**: [ENDPOINTS]
- **Authentication**: [AUTHENTICATION]

### [API_2]
- **Purpose**: [PURPOSE]
- **Endpoints**: [ENDPOINTS]
- **Authentication**: [AUTHENTICATION]

## Deployment Architecture
[Description of the deployment architecture]

## Security Considerations
- [SECURITY_CONSIDERATION_1]
- [SECURITY_CONSIDERATION_2]
- [SECURITY_CONSIDERATION_3]

## Scalability Strategy
[Description of how the system will scale]

## Monitoring and Logging
[Description of monitoring and logging approach]

---

*This document captures the high-level architecture of the system.*
```

## TRANSITION TO RIPER WORKFLOW

Once the START phase is complete, you should transition to the RIPER workflow by:

1. Ensuring all memory files are populated with initial information
2. Documenting the current state in activeContext.md
3. Setting up initial tasks in progress.md
4. Transitioning to RESEARCH mode with "ENTER RESEARCH MODE" command

The START phase is designed to be run once at the beginning of a project, while the RIPER workflow is cyclical and continues throughout the project lifecycle.

```mermaid
flowchart LR
    Start[START Phase] -->|One-time| R[Research]
    R -->|Cyclical| I[Innovate]
    I --> P[Plan]
    P --> E[Execute]
    E --> Rev[Review]
    Rev -.-> R
```

## DELIVERABLES CHECKLIST

At the end of the START phase, ensure the following are complete:

- [ ] Project requirements documented
- [ ] Technology stack selected and documented
- [ ] System architecture defined
- [ ] Project scaffold created
- [ ] Development environment configured
- [ ] Memory Bank initialized with all core files
- [ ] Initial tasks documented in progress.md
- [ ] .cursorrules file created with initial patterns

Once all items are checked, transition to the RIPER workflow by informing the user by displaying "START PHASE HAS BEEN SUCCESSFUL." Then tell the User they must type the "ENTER RESEARCH MODE" command to move into the research mode of the Riper workflow
