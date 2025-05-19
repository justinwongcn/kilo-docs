# Memory Bank

## Overview

Memory Bank is a system of structured documentation that enables Kilo Code to **better understand project** and **maintain context across coding sessions**. It transforms your AI assistant from a stateless tool into a persistent development partner with perfect recall of your project details. Kilo Code automatically reads your Memory Bank files to rebuild its understanding of your project whenever you start a new session.

## Key Benefits

- **Language Agnostic**: Functions with any programming language or framework
- **Efficient Project Understanding**: Helps Kilo Code understand the purpose and tech stack of a project
- **Context Preservation**: Maintain project knowledge across sessions without needing to scan files in every new session
- **Faster Startup**: Kilo Code immediately comprehends your project context when you begin a new session
- **Self-Documenting Projects**: Create valuable documentation as a byproduct

## How Memory Bank Works

Memory Bank is built on Kilo Code's [Custom Rules](/advanced-usage/custom-rules) feature, providing a specialized framework for project documentation. Memory Bank files are standard markdown files stored in `.kilocode/rules/memory-bank` project repository. They're not hidden or proprietary - they're regular documentation files that both you and Kilo Code can access.

Files are organized in a hierarchical structure that builds a complete picture of your project:

## Core Memory Bank Files

### brief.md
*This file is created and maintained manually*
- The foundation of your project
- High-level overview of what you're building
- Core requirements and goals
- Example: *"Building a React web app for inventory management with barcode scanning"*

### product.md
- Explains why the project exists
- Describes the problems being solved
- Outlines how the product should work
- Example: *"The inventory system needs to support multiple warehouses and real-time updates"*

### context.md
- The most frequently updated file
- Contains current work focus and recent changes
- Tracks active decisions and considerations
- Example: *"Currently implementing the barcode scanner component; last session completed the API integration"*

### architecture.md
- Documents the system architecture
- Records key technical decisions
- Lists design patterns in use
- Explains component relationships
- Example: *"Using Redux for state management with a normalized store structure"*

### tech.md
- Lists technologies and frameworks used
- Describes development setup
- Notes technical constraints
- Records dependencies and tool configurations
- Example: *"React 18, TypeScript, Firebase, Jest for testing"*

## Additional Context Files

Create additional files as needed to organize:
- Complex feature documentation
- Integration specifications
- API documentation
- Testing strategies
- Deployment procedures

## Getting Started with Memory Bank

### First-Time Setup

1. Create a `.kilocode/rules/memory-bank/` folder in your project
2. Write a basic project brief in `.kilocode/rules/memory-bank/brief.md`
3. Create a file `.kilocode/rules/memory-bank/instructions.md` and paste there [this document](pathname:///downloads/memory-bank.md)
4. Ask Kilo Code to "initialize memory bank"
5. Follow the guided setup process

### Project Brief Tips

- Start simple - it can be as detailed or high-level as you like
- Focus on what matters most to you
- Kilo Code will help fill in gaps and ask questions
- You can update it as your project evolves

Sample prompt that delivers a reasonably good brief:

```
Provide a concise and comprehensive description of this project, highlighting its main objectives, key features, used technologies and significance. Then, write this description into a text file named appropriately to reflect the project's content, ensuring clarity and professionalism in the writing. Stay brief and short.
```

## Working with Memory Bank

### Core Workflows

### Key Commands

- `initialize memory bank` - Use when starting a new project
- `update memory bank` - Initiates a comprehensive re-analysis of the contextual documentation for the current task. **Caution:** This is resource-intensive and not recommended for "lightweight" models due to potentially reduced effectiveness.

### Documentation Updates

Memory Bank updates should automatically occur when:
- You discover new patterns in your project
- After implementing significant changes
- When you explicitly request with `update memory bank`
- When you feel context needs clarification

## Frequently Asked Questions

### Where are the memory bank files stored?
The Memory Bank files are regular markdown files stored in your project repository, typically in a `.kilocode/rules/memory-bank/` folder. They're not hidden system files - they're designed to be part of your project documentation.

### Managing Context Windows
As you work with Kilo Code, your context window will eventually fill up. When you notice responses slowing down or references becoming less accurate:
1. Ask Kilo Code to "update memory bank" to document the current state
2. Start a new conversation/task
3. Kilo Code will automatically access your Memory Bank in the new conversation

### How often should I update the memory bank?
Update the Memory Bank after significant milestones or changes in direction. For active development, updates every few sessions can be helpful. Use the "update memory bank" command when you want to ensure all context is preserved.

## Best Practices

### Getting Started
- Start with a basic project brief and let the structure evolve
- Let Kilo Code help create the initial structure
- Review and adjust files as needed to match your workflow

### Ongoing Work
- Let patterns emerge naturally as you work
- Don't force documentation updates - they should happen organically
- Trust the process - the value compounds over time
- Watch for context confirmation at the start of sessions

### Documentation Flow
- `brief.md` is your foundation
- `context.md` changes most frequently
- All files collectively maintain project intelligence

## Remember
The Memory Bank is Kilo Code's only link to previous work. Its effectiveness depends entirely on maintaining clear, accurate documentation and confirming context preservation in every interaction.