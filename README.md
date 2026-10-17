# SLE-4: Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Student:** Sanskruti Sandeep Danole  
**PRN:** 25UAM059  
**Division:** A  
**System:** BFS and DFS Graph Search System

## Purpose

SLE-4 records and defends one important architecture decision from the BFS/DFS project. The selected decision is to keep BFS and DFS inside a dedicated **Search Engine** container and to decompose that container into clear components.

## Connection with Previous SLEs

- **SLE-1:** Built the BFS/DFS search project and maintained the AI contribution documentation.
- **SLE-2:** Empirically compared BFS and DFS on the same 20-node graph using repeated 10,000-run benchmarks.
- **SLE-3:** Represented the same system using the full C4 model: Context, Container, Component and Code.
- **SLE-4:** Records the architecture decision, alternatives, justification and consequences.

## ADR

See [`ADR/ADR-001-search-engine-container.md`](ADR/ADR-001-search-engine-container.md).

## Submission Documents

- [`SLE4_25UAM059_Sanskruti_Danole.pdf`](SLE4_25UAM059_Sanskruti_Danole.pdf)
- [`SLE4_25UAM059_Sanskruti_Danole.docx`](SLE4_25UAM059_Sanskruti_Danole.docx)

## Previous Work

- SLE-1: https://github.com/danolesanskruti-lang/ai-workflow-assistant
- SLE-2: https://github.com/danolesanskruti-lang/IAI_SLE2
- SLE-3: https://github.com/danolesanskruti-lang/SLE-3-C4-model

## Design Decision Summary

The Search Engine is treated as the main container because it contains the core BFS/DFS traversal logic. The SLE-3 architecture separates Input/Control, Graph Data, Search Engine, Result/Trace and Python Runtime responsibilities. At Component level, traversal selection, frontier management, visited tracking, target checking and traversal output are separated so the design remains understandable and directly connected to the implementation.

## AI Contribution

**AI tool used:** ChatGPT.

AI assistance was used to organize and refine the ADR structure, connect the architecture decision with the previous SLE-1, SLE-2 and SLE-3 work, improve the clarity of the rationale and consequences, and review the documentation for consistency. The student provided the project context and previous work, reviewed the generated content, made the final decisions and is responsible for the submitted implementation and documentation.
