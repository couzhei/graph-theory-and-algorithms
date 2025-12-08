# Graph Theory and Algorithms

A study path from mathematical foundations to graph algorithms, designed for developers seeking deeper understanding. All implementations in **Rust**.

## Repository Structure

```
graph-theory-and-algorithms/
├── sessions/
│   ├── 00-mathematical-foundations/
│   ├── 01-sets-boolean-logic/
│   ├── 02-logic-relations/
│   ├── 03-functions-counting/
│   ├── 04-proof-techniques/
│   ├── 05-combinatorics-graphs-intro/
│   └── ...
├── algorithms/
│   ├── data-structures/
│   ├── graph-theory/
│   └── complexity/
├── examples/
└── exercises/
```

---

## Session 0: Mathematical Foundations — History & Philosophy

Before diving into algorithms, we ground ourselves in the *why* behind mathematical reasoning.

### The Journey of Mathematical Thought

**Practical Origins** — Mathematics began as utility: tally marks for counting (~20,000 BCE), rope-stretching for land surveying in Egypt, empirical rules for construction and warfare. It was craft, not theory.

**Greek Abstraction (600–300 BCE)** — The Pythagoreans and Plato transformed mathematics from "how" to "why." The concept of *proof* was born. Euclid's *Elements* organized geometry into an axiomatic-deductive system—a model of certainty for two millennia.

**The Divine Language** — Medieval scholars and later Newton, Kepler, and Galileo saw mathematics as the code God used to write the universe. Newton's *Principia* (1687) cemented the view: nature is a mathematical machine.

**19th Century Cracks** — Non-Euclidean geometries shattered the notion of one true geometry. Cantor's set theory revealed infinities of different sizes. Paradoxes emerged.

**Foundational Crisis (Early 20th Century)** — Russell's Paradox broke naive set theory. Three schools arose:
- **Logicism** (Frege, Russell): Mathematics is reducible to logic
- **Formalism** (Hilbert): Mathematics is symbol manipulation; prove consistency
- **Intuitionism** (Brouwer): Only constructible objects exist

**The Hammer Blows**:
- **Gödel (1931)**: Any consistent system rich enough for arithmetic is *incomplete*—true statements exist that cannot be proven
- **Turing (1936)**: Formalized computation; proved the Halting Problem undecidable

### The Computational Turn

These crises birthed computer science:
- **Automata & Formal Languages**: Finite automata, Turing machines, formal grammars—the bedrock of compilers and parsing
- **Boolean Logic to Gates**: Boole's algebra (1850s) + Shannon's insight (1937) = physical logic gates
- **Stored-Program Architecture**: Turing and von Neumann's key insight—treat programs as data

### From Computability to Complexity

Once we knew *what* could be computed, the question became *at what cost*:
- **P**: Problems solvable efficiently (polynomial time)
- **NP**: Solutions verifiable efficiently, but finding them may be hard
- **NP-Complete**: The hardest problems in NP; solve one fast, solve them all
- **P vs NP**: The most important open problem in computer science

**Modern Reality**: When facing intractable problems, we turn to approximation algorithms, heuristics, and randomized methods. The shift from "seeking Truth" to "seeking the Provably Good Enough."

### Why This Matters

Understanding this history reveals that:
1. Mathematical rigor is not arbitrary—it arose from real crises and failures
2. Computation has fundamental limits (Gödel, Turing)
3. Complexity theory tells us when to stop searching for perfect solutions
4. The formalism empowers us to build correct, efficient systems

*"All models are wrong, some are useful."* — George. P. Box

---

## Phase 1: Mathematical Foundations (Sessions 1–5)

| Session | Topic | Key Concepts | Rust Connection |
|---------|-------|--------------|-----------------|
| 1 | **Sets & Boolean Logic** | Membership, subsets, union, intersection, power sets | `HashSet`, `BTreeSet`, iterators |
| 2 | **Logic & Relations** | Propositional/predicate logic, equivalence relations | `&&`, `\|\|`, `.all()`, `.any()` |
| 3 | **Functions & Counting** | Bijections, cardinality, counting principles | Pure functions, `HashMap`, complexity |
| 4 | **Proof Techniques** | Induction, modular arithmetic, logarithms | Recursive correctness, binary search |
| 5 | **Combinatorics & Graph Intro** | Permutations, combinations, graph basics | Iterators, graph representations |

### Session Format (60–75 min)
1. **Historical Hook** (5 min) — Why these ideas emerged
2. **Core Concepts** (30 min) — Definitions with examples
3. **Rust Implementation** (20 min) — Code that demonstrates the concept
4. **Algorithmic Application** (10 min) — Connection to real algorithms
5. **Discussion** (10 min)

---

## Phase 2: Graph Algorithms

Building on foundations:

- **Data Structures**: Arrays, linked lists, trees, heaps, hash tables
- **Graph Representations**: Adjacency matrix, adjacency list
- **Traversal**: BFS, DFS
- **Shortest Paths**: Dijkstra, Bellman-Ford, Floyd-Warshall
- **Minimum Spanning Trees**: Kruskal, Prim
- **Advanced**: Topological sort, strongly connected components, network flows

---

## Code-First Approach

Abstract concepts connect to concrete Rust:

```rust
use std::collections::HashSet;

// Set operations
let a: HashSet<i32> = [1, 2, 3].into_iter().collect();
let b: HashSet<i32> = [3, 4, 5].into_iter().collect();
let union: HashSet<_> = a.union(&b).collect();         // {1, 2, 3, 4, 5}
let intersection: HashSet<_> = a.intersection(&b).collect(); // {3}

// Predicate logic
let all_positive = vec![1, 2, 3].iter().all(|&x| x > 0);  // ∀x, x > 0
let exists_even = vec![1, 2, 3].iter().any(|&x| x % 2 == 0); // ∃x, x mod 2 = 0
```

---

## Materials

- **CLRS** — *Introduction to Algorithms* (reference)
- **MIT 6.006** — Lecture notes
- **Rust implementations** — All concepts with working code

## Prerequisites

- Basic programming knowledge
- Rust installed (`rustup`)
- Curiosity

## Goals

By completion, you will:
- Read and write the mathematical language of algorithms
- Analyze time and space complexity
- Implement graph algorithms confidently
- Recognize NP-complete problems and know when to approximate
- Understand the historical arc from ancient mathematics to modern computation

---

*"The purpose of computing is insight, not numbers."* — Richard Hamming
