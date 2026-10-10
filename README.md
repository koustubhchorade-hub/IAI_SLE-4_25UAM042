
---

## 📄 Submission Contents

| Part | Content |
|------|---------|
| **Part A** | Architecture Decision Record (ADR) — BFS vs DFS |
| **Part B** | Short Summary of My SLE Journey (SLE-2 → SLE-3 → this decision) |
| **Part C** | AI Contribution Note |
| **Part D** | Viva Preparation Notes |

---

## 🔗 Related SLE Work

| SLE | Description | Link |
|-----|-------------|------|
| SLE-2 | Profiling of BFS vs DFS (py-spy) | — |
| SLE-3 | C4 Architecture of BFS vs DFS Graph Search System | — |
| **SLE-4** | **ADR + Viva Defense (this repo)** | — |

---

## 🧠 Key Points from the ADR

### Decision
Selected **BFS** as the primary search algorithm for the Graph Search System.

### Alternatives Considered
- **DFS** — Slower (24.23 ms) and expanded more nodes (54,472)
- **Bidirectional Search** — Needs a known goal state; complicates architecture
- **IDDFS** — Re-explores nodes at each depth limit; wastes work

### Rationale
- SLE-2 profiling: BFS was **~4.5× faster** and expanded **~3.6× fewer nodes**
- SLE-3 design: Search Controller dispatches to BFS/DFS; Frontier module uses a queue for BFS

### Consequences
**Positive:**
- Guarantees shortest path in unweighted graph
- Measurably faster and more node-efficient
- Cleanly fits the queue-based Frontier module

**Negative / Trade-offs:**
- Higher memory usage (O(b^d))
- Not optimal for weighted graphs (Dijkstra needed)

---

## 🤖 AI Contribution Note

**AI tools used:** ChatGPT and Claude

**What AI helped with:**
- Understanding BFS, DFS, and py-spy concepts
- Organizing the C4 architecture levels
- Preparing explanations for diagrams

**What I did myself:**
- Wrote and ran the Python program for BFS and DFS
- Executed profiling using py-spy and collected real numbers
- Tested the program and verified results
- Made the final decision to choose BFS based on data

---

## 🎤 Viva Quick Answers

| Question | Answer |
|----------|--------|
| Why BFS? | 5.32 ms vs 24.23 ms; 15,000 vs 54,472 nodes |
| Why not DFS? | Slower and expanded more nodes |
| Why not Bidirectional? | Needs known goal + complex architecture |
| Why not IDDFS? | Re-explores nodes, wastes work |
| What did AI do? | Helped understand concepts only |
| What did you do? | Code, profiling, testing, decision |

---

## 📚 References

- SLE-2 Report: Profiling of BFS vs DFS (py-spy, 5 runs)
- SLE-3 Report: C4 Architecture of BFS vs DFS Graph Search System

---

## 📌 Course Information

**Department of CSE (AI & ML)**  
**02AML204 — Introduction to Artificial Intelligence**  
**SLE-4 Student Guideline** | Record the decision, justify it, defend it.

---

