# Graph Theory and Algorithms

A study path from mathematical foundations to graph algorithms, designed for developers seeking deeper understanding. All implementations in **Python**.

## 📁 Repository Structure

```
graph-theory-and-algorithms/
├── 00-mathematical-foundations/
├── 01-sets-boolean-logic/
├── 02-relations-functions/
├── 03-famous-functions-and-counting/
├── 04-intro-algorithms/
├── 05-basic-data-structures/
└── ...
```

---

## 📜 Session 0: Mathematical Foundations — History & Philosophy

Before diving into algorithms, we ground ourselves in the _why_ behind mathematical reasoning.

### 🌍 The Journey of Mathematical Thought

**📍 Practical Origins** — Mathematics began as utility: tally marks for counting (~20,000 BCE), rope-stretching for land surveying in Egypt, empirical rules for construction and warfare. It was craft, not theory.

**Greek Abstraction (600–300 BCE)** — The Pythagoreans and Plato transformed mathematics from "how" to "why." The concept of _proof_ was born. Euclid's _Elements_ organized geometry into an axiomatic-deductive system—a model of certainty for two millennia.

**The Divine Language** — Medieval scholars and later Newton, Kepler, and Galileo saw mathematics as the code God used to write the universe. Newton's _Principia_ (1687) cemented the view: nature is a mathematical machine.

**19th Century Cracks** — Non-Euclidean geometries shattered the notion of one true geometry. Cantor's set theory revealed infinities of different sizes. Paradoxes emerged.

**Foundational Crisis (Early 20th Century)** — Russell's Paradox broke naive set theory. Three schools arose:

- **Logicism** (Frege, Russell): Mathematics is reducible to logic
- **Formalism** (Hilbert): Mathematics is symbol manipulation; prove consistency
- **Intuitionism** (Brouwer): Only constructible objects exist

**The Hammer Blows**:

- **Gödel (1931)**: Any consistent system rich enough for arithmetic is _incomplete_—true statements exist that cannot be proven
- **Turing (1936)**: Formalized computation; proved the Halting Problem undecidable

### 💻 The Computational Turn

These crises birthed computer science:

- **Automata & Formal Languages**: Finite automata, Turing machines, formal grammars—the bedrock of compilers and parsing
- **Boolean Logic to Gates**: Boole's algebra (1850s) + Shannon's insight (1937) = physical logic gates
- **Stored-Program Architecture**: Turing and von Neumann's key insight—treat programs as data

### ⚡ From Computability to Complexity

Once we knew _what_ could be computed, the question became _at what cost_:

- **P**: Problems solvable efficiently (polynomial time)
- **NP**: Solutions verifiable efficiently, but finding them may be hard
- **NP-Complete**: The hardest problems in NP; solve one fast, solve them all
- **P vs NP**: The most important open problem in computer science

**Modern Reality**: When facing intractable problems, we turn to approximation algorithms, heuristics, and randomized methods. The shift from "seeking Truth" to "seeking the Provably Good Enough."

### 💡 Why This Matters

Understanding this history reveals that:

1. Mathematical rigor is not arbitrary—it arose from real crises and failures
2. Computation has fundamental limits (Gödel, Turing)
3. Complexity theory tells us when to stop searching for perfect solutions
4. The formalism empowers us to build correct, efficient systems

_"All models are wrong, some are useful."_ — George. P. Box

---

## 🧮 Phase 1: Mathematical Foundations (Sessions 0–5)

| Session | Folder                              | Topic                             | Key Concepts                                         | Python Connection                       |
| ------- | ----------------------------------- | --------------------------------- | ---------------------------------------------------- | --------------------------------------- |
| 0       | `00-mathematical-foundations/`      | **History & Philosophy**          | Math origins, Gödel, Turing, complexity theory       | Foundational context                    |
| 1       | `01-sets-boolean-logic/`            | **Sets & Boolean Logic**          | Membership, subsets, union, intersection, power sets | `set`, `frozenset`, list comprehensions |
| 2       | `02-relations-functions/`           | **Relations & Functions**         | Propositional/predicate logic, bijections, relations | `and`, `or`, `all()`, `any()`           |
| 3       | `03-famous-functions-and-counting/` | **Functions & Counting**          | Cardinality, counting principles, logarithms         | Pure functions, `dict`, complexity      |
| 4       | `04-intro-algorithms/`              | **Algorithms & Proof Techniques** | Induction, modular arithmetic, recursion             | Recursive correctness, binary search    |
| 5       | `05-basic-data-structures/`         | **Basic Data Structures**         | Arrays, lists, trees, heaps, graph basics            | Lists, dicts, NetworkX                  |

---

## 🔗 Phase 2: Graph Algorithms

Building on foundations:

- **Data Structures**: Arrays, linked lists, trees, heaps, hash tables
- **Graph Representations**: Adjacency matrix, adjacency list
- **Traversal**: BFS, DFS
- **Shortest Paths**: Dijkstra, Bellman-Ford, Floyd-Warshall
- **Minimum Spanning Trees**: Kruskal, Prim
- **Advanced**: Topological sort, strongly connected components, network flows

---

## 💻 Code-First Approach

Abstract concepts connect to concrete Python:

```python
# Set operations
a = {1, 2, 3}
b = {3, 4, 5}
union = a | b                  # {1, 2, 3, 4, 5}
intersection = a & b           # {3}

# Predicate logic
all_positive = all(x > 0 for x in [1, 2, 3])       # ∀x, x > 0
exists_even = any(x % 2 == 0 for x in [1, 2, 3])  # ∃x, x mod 2 = 0
```

---

## 📚 Materials

- 📖**CLRS** — _Introduction to Algorithms_ (reference)
- 🎓**MIT 6.006** — Lecture notes
- 🐍**Python implementations** — All concepts with working code
- 🔗**NetworkX** — Graph theory library for Python

## ✅ Prerequisites

- 🐍Basic Python knowledge
- 🐍Python 3.13+ installed
- 🧠Curiosity

## 🎯 Goals

By completion, you will:

- Read and write the mathematical language of algorithms
- Analyze time and space complexity
- Implement graph algorithms confidently
- Recognize NP-complete problems and know when to approximate
- Understand the historical arc from ancient mathematics to modern computation

---

_"The purpose of computing is insight, not numbers."_ — Richard Hamming
