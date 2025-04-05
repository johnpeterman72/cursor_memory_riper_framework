# Migration Guide: Cursor RIPER Framework 2.0

This guide provides instructions for migrating to the new MDC-based RIPER Framework Version 2.0.

## Overview of Changes

Version 2.0 introduces several key changes:

1. **MDC Format Adoption**: Converting all framework files to Multi-Document Context (MDC) format for better AI retrieval
2. **New File Structure**: Moving from `.cursorrules` to the `.cursor/rules/` folder structure
3. **Modular Framework Design**: Splitting the framework into core, workflow, and intelligence components
4. **Enhanced State Management**: Adding explicit state tracking for project phases and modes
5. **Unified Workflow**: Integrating START phase and RIPER workflow into a cohesive system
6. **Customization System**: Adding user-configurable settings for framework behavior
7. **Safety Enhancements**: Adding protections against accidental re-initialization

## Migration Steps

### 1. Backup Existing Implementation

```bash
# Create backup directory
mkdir -p ./backup-$(date +%Y%m%d)

# Backup existing .cursorrules file
cp .cursorrules ./backup-$(date +%Y%m%d)/

# Backup any existing memory files
cp -r memory-bank/ ./backup-$(date +%Y%m%d)/ 2>/dev/null || true
```

### 2. Create New Directory Structure

```bash
# Create framework directory structure
mkdir -p .cursor/rules/framework
mkdir -p .cursor/rules/memory-bank
mkdir -p .cursor/rules/intelligence
mkdir -p .cursor/rules/framework/archive
mkdir -p .cursor/rules/memory-bank/backups
```

### 3. Install Framework Files

Copy the following MDC files into the new structure:

```
.cursor/rules/framework/core.mdc
.cursor/rules/framework/state.mdc
.cursor/rules/framework/riper_workflow.mdc
.cursor/rules/framework/start_phase.mdc
.cursor/rules/framework/customization.mdc
.cursor/rules/intelligence/patterns.mdc
.cursor/rules/intelligence/preferences.mdc
.cursor/rules/intelligence/decisions.mdc
```

### 4. Migrate Existing Memory Bank (if applicable)

If you have an existing memory bank, migrate it to the new format:

```bash
# For each existing memory file
for file in memory-bank/*.md; do
  # Extract filename without extension
  filename=$(basename "$file" .md)
  
  # Create MDC header
  echo "---" > ".cursor/rules/memory-bank/${filename}.mdc"
  echo "title: \"${filename}\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "version: \"1.0\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "date_created: \"$(date +%Y-%m-%d)\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "last_updated: \"$(date +%Y-%m-%d)\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "content_type: \"memory_bank\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "retrieval_priority: \"medium\"" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "---" >> ".cursor/rules/memory-bank/${filename}.mdc"
  echo "" >> ".cursor/rules/memory-bank/${filename}.mdc"
  
  # Append existing content
  cat "$file" >> ".cursor/rules/memory-bank/${filename}.mdc"
done
```

### 5. Migrate Project Intelligence (if applicable)

If you have existing .cursorrules content with project intelligence:

```bash
# Extract project patterns and preferences from .cursorrules
grep -A 20 "PROJECT PATTERNS" .cursorrules > .cursor/rules/intelligence/extracted_patterns.txt
grep -A 20 "USER PREFERENCES" .cursorrules > .cursor/rules/intelligence/extracted_preferences.txt

# Manually review and integrate these into the appropriate MDC files
```

### 6. Initialize Framework State

For an existing project:

```bash
# Set appropriate state for an existing project
cat > .cursor/rules/framework/state.mdc << EOF
---
title: "Cursor RIPER Framework - State Management"
version: "2.0"
date_created: "$(date +%Y-%m-%d)"
last_updated: "$(date +%Y-%m-%d)"
framework_component: "state"
priority: "critical"
scope: "always_load"
---

# Cursor RIPER Framework - State Management
# Version 2.0

## AI PROCESSING INSTRUCTIONS
This file defines the current state of the project within the Cursor RIPER Framework. As an AI assistant, you MUST:
- Always load this file after core.mdc but before other components
- Never modify state values without proper authorization via commands
- Validate state transitions against allowed paths
- Update this file when state changes occur
- Keep all state values consistent with each other

## CURRENT PROJECT STATE

PROJECT_PHASE: "DEVELOPMENT"
# Possible values: "UNINITIATED", "INITIALIZING", "DEVELOPMENT", "MAINTENANCE"

RIPER_CURRENT_MODE: "RESEARCH"
# Possible values: "NONE", "RESEARCH", "INNOVATE", "PLAN", "EXECUTE", "REVIEW"

START_PHASE_STATUS: "COMPLETED"
# Possible values: "NOT_STARTED", "IN_PROGRESS", "COMPLETED", "ARCHIVED"

START_PHASE_STEP: 6
# Possible values