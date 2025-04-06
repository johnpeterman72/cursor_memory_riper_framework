# Cursor RIPER Framework

A comprehensive framework for AI-assisted software development in Cursor IDE. The RIPER Framework combines structured workflows with persistent memory to enhance productivity and maintain context across development sessions.

## Overview

The RIPER Framework provides a systematic approach to software development through five distinct operational modes:

1. **Research**: Information gathering and understanding existing code
2. **Innovate**: Brainstorming potential approaches and solutions
3. **Plan**: Creating detailed technical specifications
4. **Execute**: Implementing approved plans with precision
5. **Review**: Validating implementation against plans

This structure prevents unintended modifications while maintaining perfect continuity across coding sessions.

## Features

- **MDC Format**: Optimized for AI retrieval and understanding
- **Structured Workflow**: Clear separation of development phases
- **Memory Bank**: Persistent documentation across sessions
- **Project Intelligence**: Learning from patterns and preferences
- **State Management**: Explicit tracking of project phase and mode
- **Safe Initialization**: Guided setup with protection against re-initialization
- **Customization**: User-configurable framework behavior

## Directory Structure

```
.cursor/
└── rules/
    ├── framework/
    │   ├── core.mdc                # Core framework constants
    │   ├── state.mdc               # Project state tracking
    │   ├── riper_workflow.mdc      # RIPER mode operations
    │   ├── start_phase.mdc         # Project initialization
    │   ├── customization.mdc       # User preferences
    │   └── archive/                # Archived components
    │
    ├── memory-bank/                # Project memory files
    │   ├── projectbrief.mdc        # Project goals and requirements
    │   ├── productContext.mdc      # Product context and users
    │   ├── systemPatterns.mdc      # Architecture and patterns
    │   ├── techContext.mdc         # Technology stack details
    │   ├── activeContext.mdc       # Current focus and changes
    │   ├── progress.mdc            # Project status tracking
    │   └── backups/                # Automatic backups
    │
    └── intelligence/               # Project intelligence
        ├── patterns.mdc            # Observed code patterns
        ├── preferences.mdc         # User preferences
        └── decisions.mdc           # Key decisions and rationales
```

## Getting Started

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/cursor-riper-framework.git
   ```

2. Copy the files to your project:
   ```bash
   cp -r cursor-riper-framework/.cursor your-project/
   ```

3. Begin using the framework by starting the initialization phase:
   ```
   /start
   ```

### Quick Commands

The framework supports both traditional commands and slash commands:

| Action | Traditional Command | Slash Command |
|--------|---------------------|---------------|
| Start Initialization | BEGIN START PHASE | /start |
| Enter Research Mode | ENTER RESEARCH MODE | /research |
| Enter Innovate Mode | ENTER INNOVATE MODE | /innovate |
| Enter Plan Mode | ENTER PLAN MODE | /plan |
| Enter Execute Mode | ENTER EXECUTE MODE | /execute |
| Enter Review Mode | ENTER REVIEW MODE | /review |

## Workflow

### Project Initialization

The initialization process guides you through:
1. Requirements gathering
2. Technology selection
3. Architecture definition
4. Project scaffolding
5. Environment setup
6. Memory bank initialization

### Development Workflow

The RIPER workflow operates in a cyclical pattern:
1. **Research**: Understand the current state and requirements
2. **Innovate**: Brainstorm potential solutions
3. **Plan**: Create detailed implementation plans
4. **Execute**: Implement the approved plans precisely
5. **Review**: Validate the implementation against the plans

## Documentation

For detailed documentation, see:
- [Framework Guide](./docs/framework-guide.md)
- [Memory Bank Guide](./docs/memory-bank-guide.md)
- [Customization Guide](./docs/customization-guide.md)
- [Migration Guide](./docs/migration-guide.md)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

*The RIPER Framework prevents coding disasters while maintaining perfect continuity across sessions.*
