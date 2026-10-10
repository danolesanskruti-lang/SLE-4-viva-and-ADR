# SLE-4 Viva Preparation

## 1. Why did you choose a separate Search Engine container?

I chose a separate Search Engine container because BFS and DFS contain the core traversal logic. Keeping that responsibility together makes the architecture clear and matches the C4 design from SLE-3.

## 2. Why are BFS and DFS kept in the same Search Engine?

Both algorithms solve the same graph-search problem. They differ mainly in frontier behaviour: BFS uses a queue and DFS uses stack-based traversal. A shared Search Engine gives them the same architectural boundary for comparison.

## 3. What alternatives did you consider?

I considered putting all logic in one module, creating separate top-level containers for BFS and DFS, and expanding every container at Component level. The selected design gave clearer responsibilities without unnecessary duplication.

## 4. How does SLE-2 support your decision?

SLE-2 compares BFS and DFS on the same 20-node graph and repeats each search 10,000 times. This makes the search engine the central part of the experiment and provides a clear reason to keep the traversal logic in one architectural container.

## 5. How does SLE-3 support your decision?

SLE-3 separates the system into Input/Control, Graph Data, Search Engine, Result/Trace and Python Runtime. The Search Engine is then expanded into traversal selection, frontier management, visited tracking, target checking and traversal output.

## 6. What are the advantages of the decision?

It improves readability, keeps the core search responsibility in one place, makes BFS/DFS comparison easier and provides a clean connection between the C4 diagrams and the Python implementation.

## 7. What are the trade-offs?

The Search Engine could become larger if many more algorithms are added. Also, BFS-specific and DFS-specific frontier behaviour must remain clearly separated.

## 8. Explain your SLE journey in short.

SLE-1 established the search project and AI contribution documentation. SLE-2 measured and compared BFS and DFS. SLE-3 represented the system using the full C4 model. SLE-4 records and defends an important architecture decision from that work.

## 9. What did AI help with?

ChatGPT helped organize the ADR, connect the previous SLE work, structure the documentation and prepare viva questions. I provided and reviewed my BFS/DFS project and am responsible for understanding and defending the decision.

## 10. What if the problem size becomes larger?

The same architectural separation can still be used, but the Search Engine and performance considerations may need further optimization depending on graph size and search requirements.
