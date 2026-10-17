# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Student:** Sanskruti Sandeep Danole  
**PRN:** 25UAM059  
**Division:** A  
**System:** BFS and DFS Graph Search System

## Purpose

SLE-4 records and defends one important architecture decision from the BFS/DFS project. The selected decision is to keep BFS and DFS inside a dedicated **Search Engine** container and to decompose that container into clear components.

## Connection with Previous SLEs

- **SLE-1:** Built Agent / Search code + AI Contribution Log + README.
- **SLE-2:** Profiled the code and wrote a comparison report with numbers using repeated 10,000-run benchmarks.
- **SLE-3:** Drew C4 Architecture diagrams (Context, Container, Component and Code).
- **SLE-4:** Records the architecture decision, alternatives, justification, consequences and AI Contribution.

## ADR

See [`ADR/ADR-001-search-engine-container.md`](ADR/ADR-001-search-engine-container.md).

## Submission Document

- `SLE4_25UAM059.docx` / PDF version for Moodle submission.

## Previous Work

- SLE-1: https://github.com/danolesanskruti-lang/ai-workflow-assistant
- SLE-2: https://github.com/danolesanskruti-lang/IAI_SLE2
- SLE-3: https://github.com/danolesanskruti-lang/SLE-3-C4-model

## Design Decision Summary

The Search Engine is treated as the main container because it contains the core BFS/DFS traversal logic. The SLE-3 architecture separates Input/Control, Graph Data, Search Engine, Result/Trace and Python Runtime responsibilities. At Component level, traversal selection, frontier management, visited tracking, target checking and traversal output are separated so the design remains understandable and directly connected to the implementation.

## AI Contribution

**AI tool used:** ChatGPT.

**What AI helped with:** Organizing and refining the ADR structure, connecting SLE-1/SLE-2/SLE-3 work, improving the clarity of the rationale and consequences, and reviewing documentation consistency.

**What I did myself:** Provided the project context and previous work, selected and verified the architecture decision, reviewed and edited the AI-assisted content, and made the final decisions for the implementation and documentation.

**Ownership:** AI was used only as a support tool for documentation and refinement. The final technical work, decision, verification and submission are my responsibility.
