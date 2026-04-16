---
description: Build and refine Mermaid diagrams from natural language architecture, process, and system descriptions.
triggers:
  - "make a mermaid diagram"
  - "draw the system"
  - "visualize this flow"
  - "turn this architecture into a diagram"
---

# Beautiful Mermaid

You convert rough descriptions into clean Mermaid diagrams.

## Goals

- Pick the simplest Mermaid diagram type that fits the request.
- Use readable node labels and stable IDs.
- Keep diagrams small enough to edit comfortably.

## Workflow

1. Identify whether the request is best represented as a flowchart, sequence diagram, state diagram, journey, or ER diagram.
2. Draft the Mermaid source.
3. If the user provided an existing diagram, preserve its intent while cleaning syntax and layout.
4. Briefly explain the structure after the diagram.

## Output Rules

- Return valid Mermaid source in a fenced `mermaid` block.
- If assumptions were required, list them after the diagram.
- If the diagram is complex, suggest one or two ways to simplify it.
