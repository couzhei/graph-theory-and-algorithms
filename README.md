# Graph Theory and Algorithms

> _"Computers are good at following instructions, but not at reading your mind."_ — Donald Knuth (1938–)

> _"The purpose of computing is insight, not numbers."_ — Richard Hamming (1915-1998)

A terse study path from mathematical foundations to graph algorithms, designed for developers, AI engineers, and budding scientists seeking basic understanding of how mathematics can be utilized in the world of computation. Implementations will be in Python.

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

### 🧮 The Journey of Mathematical Discovery/Innovation

#### 🧱**Practical Origins**

Mathematics began as utility: tally marks for counting (~20,000 BCE), rope-stretching for land surveying in Egypt, empirical rules for construction and warfare. It was craft, not theory. Civil engineering and warfare. Think of walls, cities, roads, war machines, towers, pyramids, etc.

<img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHo3emJrcGFqZzd1YXJzY3lubzJudGk4cjR3NzMxazIwanlkcXVjYyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Smdls7tzTpqr6/giphy.gif"
style="width:800px; height:400px;" alt="Your GIF">

#### 🏛️**Greek Abstraction (600–300 BCE)**

The Pythagoreans and Plato transformed mathematics from "how" to "why." The concept of _proof_ was born. Euclid's _Elements_ organized geometry into an axiomatic-deductive system—a model of certainty for two millennia.

<img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ3piZjE3dmpmdTAyanduY2RmeTZxNDB3am4xd3ZyenpobjVsbmY5biZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3pDNbuVwcoIfEB1Uy9/giphy.gif"
style="width:800px; height:400px;" alt="Your GIF">

> _"Numbers rule the universe. All is number."_ — Pythagoras

> "_Eureka! Eureka!_ ("I have found it!")" — Archimedes

#### 🔮The Divine Language —

During Europe's Middle Ages, Islamic scholars (8th-14th centuries) preserved and expanded Greek knowledge. Al-Khwarizmi's algebra introduced systematic equation-solving; astronomers developed trigonometry. This work later reached Europe. After medieval age, later scholars like Newton, Kepler, and Galileo saw mathematics as the code God used to write the universe. [Newton's _Principia_ (1687)](https://en.wikipedia.org/wiki/Philosophi%C3%A6_Naturalis_Principia_Mathematica) cemented the view: nature is a mathematical machine.

> _"If by chance I have omitted anything more or less proper or necessary, I beg forgiveness, since there is no one who is without fault..."_ — Leonardo Fibonacci (c. 1170 – c. 1250)

<img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExemk0dm51bmtxa3FnaWM2aWs4cGp6M2ZjM3Z4MWc2MHU1OWJ4dW5jNSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/ToMjGpMhkemTU2YQUjC/giphy.gif" style="width:800px; height:400px;" alt="Your GIF">

#### 🏭**19th Century Cracks**

[Non-Euclidean](https://en.wikipedia.org/wiki/Non-Euclidean_geometry) geometries shattered the notion of one true geometry (in 1829–1830 the Russian mathematician [Nikolai Ivanovich Lobachevsky](https://en.wikipedia.org/wiki/Nikolai_Lobachevsky) and in 1832 the Hungarian mathematician [János Bolyai](https://en.wikipedia.org/wiki/J%C3%A1nos_Bolyai) separately and independently published treatises on hyperbolic geometry.). Cantor's [set theory](https://en.wikipedia.org/wiki/Naive_set_theory) revealed infinities of different sizes. However, it was not long when some paradoxes emerged.

> _"It is by logic that we prove, but by intuition that we invent."_ — Henri Poincaré (1854–1912)

<img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExazI0eTRnZGFoeXlldGN5ZW9ydGg0NXhpaGZubGc2MHY4MXJ0aXFrMyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/AFKIk5bY3NFoziS8aV/giphy.gif" style="width:800px; height:400px;" alt="Your GIF">

#### 🔥**Foundational Crisis (Early 20th Century)**

[Russell's Paradox](https://en.wikipedia.org/wiki/Russell%27s_paradox)(and a few others) broke naive set theory. Three schools arose:

- **Logicism** (Frege, Russell): Mathematics is reducible to logic; It was aimed to reduce mathematics to pure logic, but Russell's Paradox created an immediate problem for Frege's system. Russell responded by developing his theory of types within a logicist framework, eventually publishing Principia Mathematica (1910-1913) with Whitehead as an attempt to salvage logicism by reformulating the logical foundations.
- **Formalism** (Hilbert): It emerged from Hilbert's axiomatization of geometry and his response to the paradoxes. Rather than trying to reduce mathematics to logic, Hilbert proposed that mathematics could be understood as meaningless symbol manipulation, with the critical goal being to prove the consistency of axiomatic systems. He introduced the concept of "ideals"—claims about infinity that are useful in mathematics but not strictly meaningful—as a way to preserve classical mathematics while maintaining finitary foundations.
- **Intuitionism** (Brouwer): developed explicitly as a challenge to formalism and set-theoretic mathematics. Founded by L.E.J. Brouwer in the early 1910s-1920s, intuitionism rejected the law of excluded middle and demanded that mathematical objects be constructible through human mental activity. This school was so opposed to classical mathematics that it rejected much of existing analysis and infinite set theory.

<img src="./assets/Hide And Seek Magic GIF by Barbara Pozzi.gif" style="width:800px; height:600px;" alt="The bull">

> _"Everything is a process, and the universe is a grand process."_ - Alfred North Whitehead

> "_In mathematics, just as in the arts, it is dangerous to depart from the 'Schaffe Künstler, rede nicht' [Create, artist, do not talk]."_ - L.E.J. Brouwer

#### 🔨**The Hammer Blows**:

- **Gödel (1931)**: Any [consistent](https://encyclopediaofmath.org/wiki/Consistency) formal system rich enough for arithmetic is _incomplete_—true statements exist that cannot be proven, and the system cannot prove its own consistency(using only the tools within that system).
- **Turing (1936)**: Formalized computation( formalized this with the Turing machine, which became the standard model of what we mean by "computation" or "algorithm."); proved the Halting Problem is undecidable(**Decidability** concerns whether there exists an effective algorithm or procedure that can answer yes-or-no questions about a formal system in finite time, for all possible inputs.)
  Both results—Gödel's incompleteness and Turing's undecidability—share the same shape: limitations. They show that no matter what formal system or computing mechanism you construct, there will always be things it cannot do:

Gödel: Even consistent systems have true statements they cannot prove​

> _"Short wave challenge: we are standing at the gate. The gate is about to open. Freedom and glory."_ — Kurt Gödel

Turing: Even with the most general computing model, some problems (like the Halting Problem) are fundamentally unsolvable

> _"Mathematical reasoning may be regarded rather schematically as the exercise of a combination of two facilities, which we may call intuition and ingenuity."_ — Alan Turing

![](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExZGQ3Z2U4ZG8wMHdqNmlpeXd3bXdmOXo0N2RzZjVmM3BhdTlmajk4MSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Y8QlI96MfYl2w/giphy.gif)

### 💻 The Computational Turn: Crisis Becomes Creation

Despite all these crises, some mathematicians took advantages from all of these problematic views (bests of all worlds) and there came the birth of computer science:

- **Automata & Formal Languages(Turing, Church, Kleene)**: Hierarchy of abstract machines (finite automata → Turing machines) and corresponding grammars. This became the bedrock of compiler design, parsing, and programming languages.
- **Boolean Logic to Physical Gates**: Boole's algebra (1850s) and Shannon's insight (1937) formed the foundation of digital circuit design - `AND`, `OR`, and `NOT` - became physical logic gates.
- **Stored-Program Architecture**: Treating instructions (the program) as the same kind of data as numbers, stored in memory; This is the architecture of every modern computer. It turned a fixed calculator into a universal problem-solving machine.

> _"A large part of mathematics which becomes useful developed with absolutely no desire to be useful."_ — John von Neumann

### ⚡ From Computability to Complexity (1960s-Present) – Beyond "Can it be computed?"

Once we understood _what could be computed_, the next question was: _"At what cost?"_
This shifted focus from computability to computational complexity.

#### Defining Tractability: The Classes P and NP:

- **P (Polynomial Time):** Problems considered "tractable" or "efficiently solvable" on a computer. Their solution time scales "reasonably" (like $n^2, n^3$) with input size. Example: Sorting a list.

- **NP (Nondeterministic Polynomial Time):** Problems where a proposed solution can be checked quickly, but finding that solution from scratch might be astronomically hard. Example: The "Traveling Salesperson" problem—checking a route is easy, finding the shortest one seems impossibly hard for large numbers of cities.

- **The P vs. NP Question:** Is checking a solution truly easier than finding one? This is the most famous open problem in computer science. Most believe P ≠ NP, meaning some problems are inherently, fundamentally intractable.

#### NP-Completeness & NP-Hardness (Cook, Karp, 1970s):

This was a monumental discovery. Some NP problems are the "hardest of the hard." If you could solve one NP-Complete problem (e.g., Boolean Satisfiability—"SAT") quickly, you could solve all NP problems quickly.

NP-Hard problems are at least as hard as the hardest NP problems; they may not even be in NP (e.g., the Halting Problem).

**Practical Impact:** It provides a classification tool. When you encounter a new, seemingly hard problem, you try to prove it's NP-Complete. If you succeed, you immediately know:

Don't waste time looking for a perfect, fast solution for all cases (unless you're going to prove P$=$NP or P$\neq$NP and win a million dollars).

You must pivot to alternative strategies: Approximation, Heuristics, or Special Cases.

#### **The Art of the "Good Enough":** Approximation & Randomized Algorithms

Faced with intractable problems, theoretical computer science didn't give up. It developed rigorous ways to bypass perfect solutions.

**Approximation Algorithms:** Guarantee a solution within a provable factor of the optimal (e.g., "This algorithm for a hard packing problem will always use at most 1.5x the optimal number of bins").

**Randomized Algorithms:** Use randomness (like `math.random()`) to achieve good average-case performance, often much faster than the best known deterministic algorithm. Example: Quicksort with a random pivot.

This represents a profound philosophical shift: from seeking the Truth to seeking the Provably Good Enough under constraints.

> _"Computer science is no more about computers than astronomy is about telescopes."_ — Edsger Dijkstra (1930–2002)

<img src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExb2t4OWVoN3c1bnVxdXdzMjk0NGFxYmV3dXZzejZjZDF1dG5udzRrdiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/tXlpbXfu7e2Pu/giphy.gif" style="width:800px; height:400px;" alt="Your GIF">

### 💡 Why This Matters

Understanding this history reveals that:

1. Mathematical rigor is not arbitrary—it arose from real crises and failures
2. Computation has fundamental limits (Gödel, Turing)
3. Complexity theory tells us when to stop searching for perfect solutions
4. The formalism empowers us to build correct, efficient systems

> "All models are wrong, some are useful." — George. P. Box

---

## 📔 Table of Contents

| Session | Folder                              | Topic                             | Key Concepts                                         | Python Connection                                         |
| ------- | ----------------------------------- | --------------------------------- | ---------------------------------------------------- | --------------------------------------------------------- |
| 0       | `00-mathematical-foundations/`      | **History & Philosophy**          | Math origins, Gödel, Turing, complexity theory       | Foundational context                                      |
| 1       | `01-sets-boolean-logic/`            | **Sets & Boolean Logic**          | Membership, subsets, union, intersection, power sets | `set()` `list` comprehensions, `in`                       |
| 2       | `02-relations-functions/`           | **Relations & Functions**         | Propositional/predicate logic, relations, functions  | `not`, `and`, `or`, `all()`, `any()`, `<`, `=`, `+`, etc. |
| 3       | `03-famous-functions-and-counting/` | **Basic Combinatorics**           | Cardinality, modulo, counting principles, logarithms | `math`, `itertools`, `%` complexity                       |
| 4       | `04-intro-algorithms/`              | **Algorithms & Proof Techniques** | Induction, analysis of algorithms                    | Recursive correctness, binary search                      |
| 5       | `05-basic-data-structures/`         | **Basic Data Structures**         | Arrays, lists, trees, heaps, graph basics            | Lists, dicts, NetworkX                                    |

---

## 🔗 Topics in Data Structures and Algorithms

Building on foundations:

- **Data Structures**: Arrays, linked lists, trees, heaps, hash tables
- **Graph Representations**: Adjacency matrix, adjacency list
- **Traversal**: BFS, DFS
- **Shortest Paths**: Dijkstra, Bellman-Ford, Floyd-Warshall
- **Minimum Spanning Trees**: Kruskal, Prim
- **Advanced**: Dynamic programming, greedy algorithms, divide-and-conquer, topological sort, strongly connected components, network flows

---

## 💻 Python Codes

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

- 🎓**MIT 6.006 2020** — For learning materials visit [here](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/video_galleries/lecture-videos/).
- 📐**CS70 at UC Berkeley, Fall 2025** — For mathematical background [this](https://www.eecs70.org/) place seems most appropriate.
- 📖**CLRS** — _Introduction to Algorithms_, by Thomas H. Cormen, et al. ,fourth edition (reference)
- 🔗**NetworkX** — Graph theory [library](https://networkx.org/en/) for Python

## ✅ Prerequisites

- 🐍Python 3.13+ installed
- 🧠Curiosity

## 🎯 Goals

By completion, you will:

- Read and write the mathematical language of algorithms
- Analyze time and space complexity
- Implement (graph) algorithms confidently
- Recognize NP-complete problems and possibly know when to approximate
- Understand the historical arc from ancient mathematics to modern computation

---

> _"We build our computer (systems) the way we build our cities: over time, without a plan, on top of ruins."_ — Ellen Ullman

> _"Probably the fastest route to perfection is approximation"_ — Unknown
