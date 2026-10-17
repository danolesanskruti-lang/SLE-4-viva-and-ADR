# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**PRN:** 25UAM059  
**Name:** Sanskruti Sandeep Danole  
**Division:** A  
**Date:** 10 October 2026  
**GitHub:** https://github.com/danolesanskruti-lang/SLE-4-viva-and-ADR

## PART A: Architecture Decision Record (ADR)

### Title
**Use of a Separate Search Engine Container for BFS/DFS**

**Status:** Accepted

### 1. Context

The SLE-2 project implements BFS and DFS on the same 20-node graph from A to T. The experiment repeats each search 10,000 times and records the path, nodes expanded and timing. For SLE-3, the same system was represented using the C4 model. The architecture separates input/control, graph data, search engine, result/trace and Python runtime responsibilities.

### 2. Decision

The design uses a dedicated **Search Engine** as the main container for BFS and DFS traversal logic. At Component level, the Search Engine is decomposed into traversal selection, frontier management, visited tracking, target checking and traversal output/path handling.

### 3. Alternatives Considered

1. Keep all input, graph, search and output logic in one module.
2. Create separate top-level containers for BFS and DFS.
3. Expand every container at Component level instead of focusing on the Search Engine.

### 4. Rationale / Justification

- The SLE-2 experiment uses a 20-node graph and 10,000 benchmark runs for both BFS and DFS, so the search logic is the core part being measured.
- BFS uses a queue while DFS uses stack-based traversal, but both solve the same graph-search problem.
- SLE-3 therefore places both algorithms inside one Search Engine container.
- The C4 design separates Input/Control, Graph Data, Search Engine, Result/Trace and Python Runtime.
- The Component view further separates traversal selection, visited tracking, frontier management, target checking and output.
- This makes the architecture easier to explain and keeps responsibilities clear.
- The decision connects directly to the bfs(), dfs(), benchmark(), graph data and timing responsibilities in the implementation.
- Keeping the search logic together also makes BFS and DFS easier to compare under the same architectural boundary.

### 5. Consequences

### Positive

- Keeps the main search responsibility in one clear architectural location.
- Makes BFS and DFS easier to compare because they use the same Search Engine boundary.
- Supports clear C4 Context, Container, Component and Code-level explanations.
- Makes future changes to search logic easier to isolate.

### Negative / Trade-offs

- The Search Engine can become larger if many more search algorithms are added.
- A shared container requires careful separation between BFS-specific and DFS-specific frontier behaviour.

## PART B: Short Summary of My SLE Journey

SLE-1 established the BFS/DFS search project and AI contribution documentation. SLE-2 empirically compared BFS and DFS on a 20-node graph using repeated 10,000-run benchmarks. SLE-3 converted the same system into a full C4 architecture with Context, Container, Component and Code views. SLE-4 records the decision to keep BFS and DFS inside a dedicated Search Engine container and explains why that design is appropriate.

## PART C: AI Contribution Note

**AI tool used:** ChatGPT.

**What AI helped with:** AI assistance was used to organize and refine the ADR structure, connect the SLE-4 decision with the previous SLE-1, SLE-2 and SLE-3 work, improve the clarity of the rationale and consequences, and review the documentation for consistency and presentation.

**What I did myself:** I provided the project context and previous SLE work, selected the architecture decision, verified the technical content against my implementation and diagrams, reviewed and edited the AI-assisted text, and made the final decisions for the submitted implementation and documentation.

**Ownership:** AI was used as a support tool for documentation and refinement. The final architecture decision, project work, verification and submission are my responsibility.
