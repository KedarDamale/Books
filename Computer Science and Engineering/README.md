# Computer science and engineering study map

This is a knowledge-first reading and experimentation atlas: **35 domains, 100 areas, and 322 focused study units**, from first programs and digital circuits through advanced theory, engineering, and research-facing topics. Study for understanding, proofs, working implementations, and informed judgment. Progress is demonstrated by the completion tasks.

The [complete topic index](TOPIC_INDEX.md) links to every unit. The [source catalog](SOURCES.md) names legitimate books, open texts, university materials, and official framework documentation. The [repository rules](../AGENTS.md) explain how to extend the atlas. A finite map cannot exhaust computer science or its evolving research frontiers.

## How to use a unit

1. Check its domain prerequisites below and the area's earlier units in the topic index. At the start of a new area, return to the domain map rather than assuming the previous area supplied every prerequisite.
2. Read the named section titles or chapter themes. A recurring book is read in selected portions; it is never an instruction to read that entire book again. Page numbers are omitted because editions and electronic layouts vary.
3. Work through the six ordered checklist objectives. Keep definitions, assumptions, examples, invariants or proofs, and failure cases alongside the code or calculations.
4. Finish the completion task. Preserve inputs, environment versions, evidence, and one limitation or counterexample. Revisit prerequisites when you cannot explain a result.
5. Use an `Extension book` only for optional depth. A `Required second source` supplies specific material missing from the primary reading.

The historical `Primary book` field is retained in every `book_name.txt`. For a framework, protocol, or research frontier it may name an official online handbook, university course text, or original paper; `Source type` makes that distinction explicit. No book files or solution manuals are included.

## Primary languages and application stack

**Python, TypeScript, and Rust are the primary implementation languages throughout the atlas.** Begin in Python if programming is new, then study TypeScript and Rust using the explicit tracks in domain 01. Their order within domain 01 is a useful default, not a dependency between all three languages. A learner may begin discrete mathematics and data structures after the Python foundations while the other languages develop in parallel.

| Role | Main tools | Where to deepen them |
| --- | --- | --- |
| Python applications and model APIs | Python, FastAPI, Pydantic | 01, 21, 33 |
| TypeScript applications | TypeScript, NestJS, React, Astro | 01, 21 |
| Rust services and systems | Rust, Tokio, Axum | 01, 07, 16, 21, 29 |
| Web documents and styling | HTML, CSS, Tailwind CSS | 21, 22 |
| Numerical and tabular data | NumPy, Pandas, Polars, DuckDB, SQL | 02, 10, 23 |
| Statistical learning | scikit-learn, XGBoost | 25 |
| Neural and visual learning | PyTorch, YOLO | 26, 28 |
| Retrieval and agent workflows | LangChain, LangGraph, MCP, human review | 27 |
| Data and AI operations | MLflow, Databricks, Docker, AWS, CI/CD | 19, 23, 33 |

The deeper data and AI routes use this current stack. Core algorithms, architecture, operating systems, networks, databases, theory, security, and engineering retain their subject-driven scope. Implementation examples and projects should use the three primary languages whenever the platform permits.

Some excellent systems and compiler texts illustrate concepts in C, C++, Java, Scheme, or R. Read the minimal notation needed to understand their diagrams and algorithms, and implement exercises in Python, TypeScript, or Rust. This is code-reading literacy rather than a separate primary-language curriculum. HDL, assembly, SQL, shell commands, TLA+, and proof-assistant notation serve local hardware, querying, tooling, specification, or proof tasks. A CPU simulator, synthetic data, and local mock services are sufficient for the initial projects; paid cloud services and physical hardware are optional.

## Entry requirements and mathematics bridges

Start with basic arithmetic, algebra, file management, and willingness to trace a short program. If needed, use the [Mathematics study map](../Mathematics/README.md) before the CS-specific bridges in domain 02. Do not postpone learning to program until you have finished all of mathematics.

| Needed understanding | Mathematics prerequisite or continuation | Main uses |
| --- | --- | --- |
| Arithmetic and algebra | [Arithmetic and algebra](../Mathematics/03_Algebra_Functions) | Expressions, functions, units, and quantitative reasoning throughout the core. |
| Proof and discrete mathematics | [Proof and discrete mathematics](../Mathematics/05_Proof_Discrete) | Invariants, algorithms, automata, complexity, and formal verification. |
| Calculus | [Calculus](../Mathematics/06_Calculus) | Circuit transients, gradients, physical models, graphics, and numerical methods. |
| Linear algebra | [Linear algebra](../Mathematics/07_Linear_Algebra) | Geometry, regression, neural networks, robotics, and quantum states. |
| Differential equations | [Differential equations](../Mathematics/08_ODE_Dynamics) | Dynamic circuits, robot motion, control, and simulation. |
| Probability and statistics | [Probability and statistics](../Mathematics/15_Probability_Statistics) | Randomized algorithms, queueing, inference, learning, and uncertain systems. |
| Optimization and control | [Optimization and control](../Mathematics/17_Optimization_Control) | Learning objectives, control, approximation, and constrained design. |
| Numerical computation | [Numerical computation](../Mathematics/18_Numerical_Computation) | Conditioning, stable solvers, approximation, and scientific computation. |
| Fields and finite fields | [Fields and finite fields](../Mathematics/11_Abstract_Algebra/03_Fields_Galois) | Coding, cryptographic constructions, and algebraic representations. |
| Number theory | [Number theory](../Mathematics/12_Number_Theory) | Public-key tools and number-theoretic security assumptions. |
| Information, coding, and cryptography | [Information, coding, and cryptography](../Mathematics/24_Information_Coding_Crypto) | Further mathematical depth for information, codes, and cryptography. |

Finite probability and proof are sufficient for the core discrete path. Continuous queueing, statistical inference, and learning need the probability and calculus branches when those concepts first appear. For circuit differential equations, robot dynamics, and PDE experiments, finish the relevant calculus and ODE units first. Quantum examples also require complex numbers and tensor products; cryptographic and coding proofs require the stated modular-arithmetic and finite-field prerequisites.

## Branching routes

The numbers organize material; they are not a rigid calendar. Study a branch after its listed dependencies, and use the area lists for the next concrete unit. Domain-level dependencies describe background for a whole branch. Its elementary units may be started sooner: HTML and CSS after basic file skills, dataframe work after Python collections, and testing after a small working program. For security, distributed execution, or deployment tasks, bring in those additional branch prerequisites when they appear. Capstones require the particular units selected for the project.

- **New to computing:** [00 Learning practice and computing tools](00_Orientation_and_Tools) → [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages) → [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) → [03 Data structures and representation tradeoffs](03_Data_Structures) → [04 Algorithm design, correctness, and limits](04_Algorithms). Begin with Python foundations. Add basic engineering practice from 14 and continue into hardware or software branches.
- **Bottom-up machine understanding:** [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics) → [06 Computer organization and advanced architecture](06_Computer_Architecture) → [07 Systems programming and machine interfaces](07_Systems_Programming) → [08 Operating systems and resource management](08_Operating_Systems) → [09 Computer networks and Internet protocols](09_Computer_Networks) → [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage). Move from circuits and instructions to protected execution, communication, and storage.
- **Theory and language implementation:** [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) → [04 Algorithm design, correctness, and limits](04_Algorithms) → [11 Programming language semantics and abstraction](11_Programming_Language_Theory) → [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes) → [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity) → [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods). Pair mathematical proofs with small interpreters, compilers, and model checkers.
- **Software and distributed-system design:** [14 Software engineering and system evolution](14_Software_Engineering) → [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods) → [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism) → [17 Distributed systems and failure semantics](17_Distributed_Systems) → [18 System design and software architecture](18_System_Design_and_Architecture) → [19 Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability) → [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography). Bring the relevant machine, network, and database foundations before evaluating architectures.
- **Applications with the chosen stack:** [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages) → [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage) → [14 Software engineering and system evolution](14_Software_Engineering) → [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography) → [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering) → [22 Human-computer interaction and accessibility](22_Human_Computer_Interaction). Build one coherent backend first. Compare FastAPI, NestJS, and Axum through the same contracts, with React or Astro as appropriate.
- **Current data science and AI depth:** [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) → [23 Data science and data engineering](23_Data_Science_and_Data_Engineering) → [24 Artificial intelligence and decision-making](24_Artificial_Intelligence) → [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning) → [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch) → [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems) → [28 Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision) → [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering). Use the selected Python stack. Bring systems dependencies from 16–21 for deployed models and durable agent workflows.
- **Computer engineering and physical systems:** [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics) → [06 Computer organization and advanced architecture](06_Computer_Architecture) → [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism) → [29 Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics) → [30 Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing). Add calculus, differential equations, signals, and control as the physical models require.
- **Information and quantum theory:** [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) → [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity) → [31 Information theory, coding, and quantum computation](31_Information_Coding_and_Quantum_Computation). Continue through the linked mathematics and read the exact assumptions behind limits and speedups.
- **History, ethics, and research:** [32 History, ethics, and social context of computing](32_History_Ethics_and_Social_Context) → [34 Research practice and integrative projects](34_Research_and_Integrative_Projects). Study history and ethics alongside every technical branch; choose a capstone after its implementation prerequisites.

## Domain dependency map

Each domain link opens its directory. The topic index below is the direct route to every `book_name.txt`. Mathematical links denote prerequisite knowledge, which can be refreshed just before a relevant unit.

| Order | Domain and purpose | CS background | Additional mathematics |
| --- | --- | --- | --- |
| 00 | [Learning practice and computing tools](00_Orientation_and_Tools). Learn to investigate programs, reproduce results, and operate a development environment. | none | basic arithmetic |
| 01 | [Programming in Python, TypeScript, and Rust](01_Programming_Languages). Build fluency in the three primary languages and understand their execution and data models. | [00 Learning practice and computing tools](00_Orientation_and_Tools) | basic arithmetic and algebra |
| 02 | [Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations). Develop the proof and quantitative tools needed to explain algorithms and systems. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages) | [Arithmetic and algebra](../Mathematics/03_Algebra_Functions), [Proof and discrete mathematics](../Mathematics/05_Proof_Discrete) |
| 03 | [Data structures and representation tradeoffs](03_Data_Structures). Implement collections and justify their invariants, costs, and failure cases. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) | core mathematics from 02 as needed |
| 04 | [Algorithm design, correctness, and limits](04_Algorithms). Learn design methods and proofs alongside implementations and empirical comparisons. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [03 Data structures and representation tradeoffs](03_Data_Structures) | core mathematics from 02 as needed |
| 05 | [Digital logic and electronic foundations](05_Digital_Logic_and_Electronics). Connect abstract bits to circuits, state, physical timing, and hardware implementation. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) | [Arithmetic and algebra](../Mathematics/03_Algebra_Functions), [Calculus](../Mathematics/06_Calculus) |
| 06 | [Computer organization and advanced architecture](06_Computer_Architecture). Explain how instructions execute and how memory, parallelism, and energy constrain machines. | [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics) | core mathematics from 02 as needed |
| 07 | [Systems programming and machine interfaces](07_Systems_Programming). Use Rust to investigate memory, processes, binary interfaces, and operating-system services. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [06 Computer organization and advanced architecture](06_Computer_Architecture) | core mathematics from 02 as needed |
| 08 | [Operating systems and resource management](08_Operating_Systems). Study virtualization, concurrency, persistence, and kernel design as mechanisms and policies. | [06 Computer organization and advanced architecture](06_Computer_Architecture), [07 Systems programming and machine interfaces](07_Systems_Programming) | core mathematics from 02 as needed |
| 09 | [Computer networks and Internet protocols](09_Computer_Networks). Trace communication across layers and reason about routing, reliability, congestion, and application protocols. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [07 Systems programming and machine interfaces](07_Systems_Programming), [08 Operating systems and resource management](08_Operating_Systems) | core mathematics from 02 as needed |
| 10 | [Databases, storage engines, and transaction theory](10_Databases_and_Storage). Connect data models and queries to storage layouts, optimization, isolation, and recovery. | [03 Data structures and representation tradeoffs](03_Data_Structures), [04 Algorithm design, correctness, and limits](04_Algorithms), [08 Operating systems and resource management](08_Operating_Systems) | core mathematics from 02 as needed |
| 11 | [Programming language semantics and abstraction](11_Programming_Language_Theory). Understand language features through interpreters, evaluation rules, and explicit contracts. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations) | core mathematics from 02 as needed |
| 12 | [Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes). Construct language implementations and study transformations that preserve program behavior. | [03 Data structures and representation tradeoffs](03_Data_Structures), [04 Algorithm design, correctness, and limits](04_Algorithms), [06 Computer organization and advanced architecture](06_Computer_Architecture), [07 Systems programming and machine interfaces](07_Systems_Programming), [11 Programming language semantics and abstraction](11_Programming_Language_Theory) | core mathematics from 02 as needed |
| 13 | [Computability, complexity, and fundamental limits](13_Computability_and_Complexity). Prove what computation can do and distinguish impossibility from resource limits. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [04 Algorithm design, correctness, and limits](04_Algorithms), [11 Programming language semantics and abstraction](11_Programming_Language_Theory) | core mathematics from 02 as needed |
| 14 | [Software engineering and system evolution](14_Software_Engineering). Learn requirements, modularity, collaboration, and maintainability over a system lifetime. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [03 Data structures and representation tradeoffs](03_Data_Structures) | core mathematics from 02 as needed |
| 15 | [Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods). Combine experiments and proofs while understanding the guarantees and limits of each method. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [11 Programming language semantics and abstraction](11_Programming_Language_Theory), [14 Software engineering and system evolution](14_Software_Engineering) | core mathematics from 02 as needed |
| 16 | [Concurrent and parallel computation](16_Concurrency_and_Parallelism). Reason about interleavings, memory order, progress, task structure, and parallel speedup. | [04 Algorithm design, correctness, and limits](04_Algorithms), [06 Computer organization and advanced architecture](06_Computer_Architecture), [08 Operating systems and resource management](08_Operating_Systems) | core mathematics from 02 as needed |
| 17 | [Distributed systems and failure semantics](17_Distributed_Systems). Understand coordination and replicated state under delay, concurrency, crashes, and partitions. | [09 Computer networks and Internet protocols](09_Computer_Networks), [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism) | core mathematics from 02 as needed |
| 18 | [System design and software architecture](18_System_Design_and_Architecture). Design from requirements, invariants, failure models, quantitative evidence, and explicit tradeoffs. | [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [14 Software engineering and system evolution](14_Software_Engineering), [17 Distributed systems and failure semantics](17_Distributed_Systems) | [Probability and statistics](../Mathematics/15_Probability_Statistics) |
| 19 | [Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability). Understand deployment, resource isolation, observability, recovery, and operational tradeoffs. | [08 Operating systems and resource management](08_Operating_Systems), [09 Computer networks and Internet protocols](09_Computer_Networks), [18 System design and software architecture](18_System_Design_and_Architecture) | core mathematics from 02 as needed |
| 20 | [Security engineering and cryptographic foundations](20_Security_and_Cryptography). Reason from adversaries and security properties through protocols, implementation, and assurance. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [07 Systems programming and machine interfaces](07_Systems_Programming), [09 Computer networks and Internet protocols](09_Computer_Networks), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [18 System design and software architecture](18_System_Design_and_Architecture) | [Probability and statistics](../Mathematics/15_Probability_Statistics), [Number theory](../Mathematics/12_Number_Theory), [Fields and finite fields](../Mathematics/11_Abstract_Algebra/03_Fields_Galois) |
| 21 | [Web applications with the chosen language stacks](21_Web_and_Application_Engineering). Apply web and API principles using FastAPI, NestJS, React, Astro, and Axum. | [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [09 Computer networks and Internet protocols](09_Computer_Networks), [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [14 Software engineering and system evolution](14_Software_Engineering) | core mathematics from 02 as needed |
| 22 | [Human-computer interaction and accessibility](22_Human_Computer_Interaction). Study people, tasks, interaction design, and empirical usability rather than visual styling alone. | [14 Software engineering and system evolution](14_Software_Engineering), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering) | core mathematics from 02 as needed |
| 23 | [Data science and data engineering](23_Data_Science_and_Data_Engineering). Deepen the current Python data stack while studying measurement, inference, data quality, and pipelines. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Probability and statistics](../Mathematics/15_Probability_Statistics), [Calculus](../Mathematics/06_Calculus) |
| 24 | [Artificial intelligence and decision-making](24_Artificial_Intelligence). Study symbolic reasoning, search, planning, uncertainty, and rational decisions before model orchestration. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [04 Algorithm design, correctness, and limits](04_Algorithms), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity) | [Probability and statistics](../Mathematics/15_Probability_Statistics) |
| 25 | [Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning). Connect statistical learning principles to correct estimators, evaluation, and the current modeling stack. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [23 Data science and data engineering](23_Data_Science_and_Data_Engineering), [24 Artificial intelligence and decision-making](24_Artificial_Intelligence) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Probability and statistics](../Mathematics/15_Probability_Statistics), [Calculus](../Mathematics/06_Calculus), [Optimization and control](../Mathematics/17_Optimization_Control) |
| 26 | [Deep learning with PyTorch](26_Deep_Learning_with_PyTorch). Derive neural computations and learn to train, diagnose, evaluate, and optimize them in PyTorch. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Calculus](../Mathematics/06_Calculus), [Probability and statistics](../Mathematics/15_Probability_Statistics), [Optimization and control](../Mathematics/17_Optimization_Control) |
| 27 | [Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems). Study language modeling and retrieval foundations, then build explicit LangChain and LangGraph workflows. | [17 Distributed systems and failure semantics](17_Distributed_Systems), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [24 Artificial intelligence and decision-making](24_Artificial_Intelligence), [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning), [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch) | core mathematics from 02 as needed |
| 28 | [Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision). Understand image synthesis and visual inference, with PyTorch and YOLO for the current vision stack. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [04 Algorithm design, correctness, and limits](04_Algorithms), [06 Computer organization and advanced architecture](06_Computer_Architecture), [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Calculus](../Mathematics/06_Calculus), [Probability and statistics](../Mathematics/15_Probability_Statistics) |
| 29 | [Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics). Connect Rust programs to physical timing, peripherals, sensing, control, and robot motion. | [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics), [06 Computer organization and advanced architecture](06_Computer_Architecture), [07 Systems programming and machine interfaces](07_Systems_Programming), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Calculus](../Mathematics/06_Calculus), [Differential equations](../Mathematics/08_ODE_Dynamics), [Optimization and control](../Mathematics/17_Optimization_Control) |
| 30 | [Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing). Understand approximation error, numerical stability, simulation, and the cost of scientific computation. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [04 Algorithm design, correctness, and limits](04_Algorithms), [06 Computer organization and advanced architecture](06_Computer_Architecture), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism) | [Calculus](../Mathematics/06_Calculus), [Linear algebra](../Mathematics/07_Linear_Algebra), [Differential equations](../Mathematics/08_ODE_Dynamics), [Numerical computation](../Mathematics/18_Numerical_Computation) |
| 31 | [Information theory, coding, and quantum computation](31_Information_Coding_and_Quantum_Computation). Explore information limits, reliable coding, and quantum models without confusing them with universal speedups. | [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity) | [Linear algebra](../Mathematics/07_Linear_Algebra), [Probability and statistics](../Mathematics/15_Probability_Statistics), [Fields and finite fields](../Mathematics/11_Abstract_Algebra/03_Fields_Galois), [Information, coding, and cryptography](../Mathematics/24_Information_Coding_Crypto) |
| 32 | [History, ethics, and social context of computing](32_History_Ethics_and_Social_Context). Understand how technical systems inherit institutional choices and affect people over time. | [00 Learning practice and computing tools](00_Orientation_and_Tools) | core mathematics from 02 as needed |
| 33 | [MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering). Make the current data and AI stack reproducible, inspectable, deployable, and recoverable. | [19 Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering), [23 Data science and data engineering](23_Data_Science_and_Data_Engineering), [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning), [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch), [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems) | core mathematics from 02 as needed |
| 34 | [Research practice and integrative projects](34_Research_and_Integrative_Projects). Use the atlas to investigate new questions and demonstrate integrated understanding through substantial artifacts. | [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods), [18 System design and software architecture](18_System_Design_and_Architecture) | core mathematics from 02 as needed |

## Areas and their role in the learning path

### 00. Learning practice and computing tools

Learn to investigate programs, reproduce results, and operate a development environment.

- [Computing and learning practice](00_Orientation_and_Tools/01_First_principles) (2 units).
- [Shell, files, and version history](00_Orientation_and_Tools/02_Working_environment) (3 units).
- [Builds, debugging, and measurement](00_Orientation_and_Tools/03_Engineering_instruments) (2 units).

Continues into: [01 Programming in Python, TypeScript, and Rust](01_Programming_Languages), [32 History, ethics, and social context of computing](32_History_Ethics_and_Social_Context).

### 01. Programming in Python, TypeScript, and Rust

Build fluency in the three primary languages and understand their execution and data models.

- [First programming concepts in Python](01_Programming_Languages/01_Programming_foundations_in_Python) (4 units).
- [Python abstraction and execution](01_Programming_Languages/02_Python_depth) (3 units).
- [TypeScript and its JavaScript runtime](01_Programming_Languages/03_TypeScript) (4 units).
- [Rust ownership and systems abstraction](01_Programming_Languages/04_Rust) (6 units).

Continues into: [02 Discrete mathematics and mathematical bridges](02_Discrete_and_Mathematical_Foundations), [03 Data structures and representation tradeoffs](03_Data_Structures), [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics), [07 Systems programming and machine interfaces](07_Systems_Programming), [11 Programming language semantics and abstraction](11_Programming_Language_Theory), [14 Software engineering and system evolution](14_Software_Engineering), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering).

### 02. Discrete mathematics and mathematical bridges

Develop the proof and quantitative tools needed to explain algorithms and systems.

- [Logic, sets, and proof](02_Discrete_and_Mathematical_Foundations/01_Logic_and_proof) (2 units).
- [Counting, graphs, and recurrence models](02_Discrete_and_Mathematical_Foundations/02_Discrete_structures) (3 units).
- [Linear algebra, calculus, probability, and optimization bridges](02_Discrete_and_Mathematical_Foundations/03_Quantitative_bridges) (3 units).

Continues into: [03 Data structures and representation tradeoffs](03_Data_Structures), [04 Algorithm design, correctness, and limits](04_Algorithms), [05 Digital logic and electronic foundations](05_Digital_Logic_and_Electronics), [09 Computer networks and Internet protocols](09_Computer_Networks), [11 Programming language semantics and abstraction](11_Programming_Language_Theory), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [23 Data science and data engineering](23_Data_Science_and_Data_Engineering), [24 Artificial intelligence and decision-making](24_Artificial_Intelligence), [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning), [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch), [28 Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision), [30 Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing), [31 Information theory, coding, and quantum computation](31_Information_Coding_and_Quantum_Computation).

### 03. Data structures and representation tradeoffs

Implement collections and justify their invariants, costs, and failure cases.

- [Sequences, hashing, and priority queues](03_Data_Structures/01_Sequences_and_dictionaries) (4 units).
- [Ordered trees and graph storage](03_Data_Structures/02_Ordered_and_graph_structures) (3 units).
- [Storage-aware and specialized structures](03_Data_Structures/03_External_and_specialized_structures) (2 units).

Continues into: [04 Algorithm design, correctness, and limits](04_Algorithms), [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes), [14 Software engineering and system evolution](14_Software_Engineering).

### 04. Algorithm design, correctness, and limits

Learn design methods and proofs alongside implementations and empirical comparisons.

- [Basic design methods](04_Algorithms/01_Design_methods) (5 units).
- [Graph algorithms and optimization](04_Algorithms/02_Graph_optimization) (4 units).
- [Randomness, hardness, and large-scale algorithms](04_Algorithms/03_Advanced_algorithmic_thinking) (5 units).

Continues into: [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism), [24 Artificial intelligence and decision-making](24_Artificial_Intelligence), [28 Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision), [30 Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing).

### 05. Digital logic and electronic foundations

Connect abstract bits to circuits, state, physical timing, and hardware implementation.

- [Circuits and the digital abstraction](05_Digital_Logic_and_Electronics/01_Physical_foundations) (2 units).
- [Gates, arithmetic, and state machines](05_Digital_Logic_and_Electronics/02_Combinational_and_sequential_logic) (4 units).
- [Memory and processor building blocks](05_Digital_Logic_and_Electronics/03_Hardware_construction) (4 units).

Continues into: [06 Computer organization and advanced architecture](06_Computer_Architecture), [29 Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics).

### 06. Computer organization and advanced architecture

Explain how instructions execute and how memory, parallelism, and energy constrain machines.

- [Instruction sets and pipelines](06_Computer_Architecture/01_Instruction_execution) (4 units).
- [Memory hierarchies and parallel machines](06_Computer_Architecture/02_Memory_and_parallel_hardware) (4 units).

Continues into: [07 Systems programming and machine interfaces](07_Systems_Programming), [08 Operating systems and resource management](08_Operating_Systems), [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism), [28 Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision), [29 Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics), [30 Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing).

### 07. Systems programming and machine interfaces

Use Rust to investigate memory, processes, binary interfaces, and operating-system services.

- [Representations and program construction](07_Systems_Programming/01_Representation_and_toolchains) (3 units).
- [Processes, I/O, and network services](07_Systems_Programming/02_Operating_system_interfaces) (3 units).

Continues into: [08 Operating systems and resource management](08_Operating_Systems), [09 Computer networks and Internet protocols](09_Computer_Networks), [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [29 Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics).

### 08. Operating systems and resource management

Study virtualization, concurrency, persistence, and kernel design as mechanisms and policies.

- [Processes, scheduling, and virtual memory](08_Operating_Systems/01_CPU_and_address_space_virtualization) (4 units).
- [Locks and coordination](08_Operating_Systems/02_Concurrency_mechanisms) (2 units).
- [Storage, filesystems, and isolation](08_Operating_Systems/03_Persistence_and_isolation) (4 units).

Continues into: [09 Computer networks and Internet protocols](09_Computer_Networks), [10 Databases, storage engines, and transaction theory](10_Databases_and_Storage), [16 Concurrent and parallel computation](16_Concurrency_and_Parallelism), [19 Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability).

### 09. Computer networks and Internet protocols

Trace communication across layers and reason about routing, reliability, congestion, and application protocols.

- [Links, addressing, and routing](09_Computer_Networks/01_Links_and_internetworking) (4 units).
- [Transport reliability and application protocols](09_Computer_Networks/02_Transport_and_applications) (4 units).

Continues into: [17 Distributed systems and failure semantics](17_Distributed_Systems), [19 Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering).

### 10. Databases, storage engines, and transaction theory

Connect data models and queries to storage layouts, optimization, isolation, and recovery.

- [Relational modeling and SQL](10_Databases_and_Storage/01_Data_models_and_queries) (4 units).
- [Physical layout, indexes, and optimization](10_Databases_and_Storage/02_Storage_and_query_engines) (3 units).
- [Isolation, concurrency control, and durability](10_Databases_and_Storage/03_Transactions_and_recovery) (3 units).
- [Distributed databases and analytical systems](10_Databases_and_Storage/04_Distributed_and_analytical_data) (2 units).

Continues into: [17 Distributed systems and failure semantics](17_Distributed_Systems), [18 System design and software architecture](18_System_Design_and_Architecture), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering), [23 Data science and data engineering](23_Data_Science_and_Data_Engineering).

### 11. Programming language semantics and abstraction

Understand language features through interpreters, evaluation rules, and explicit contracts.

- [Functions, environments, and effects](11_Programming_Language_Theory/01_Evaluation_and_abstraction) (4 units).
- [Type systems and program behavior](11_Programming_Language_Theory/02_Types_and_semantic_guarantees) (3 units).

Continues into: [12 Compilers, interpreters, and runtimes](12_Compilers_and_Runtimes), [13 Computability, complexity, and fundamental limits](13_Computability_and_Complexity), [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods).

### 12. Compilers, interpreters, and runtimes

Construct language implementations and study transformations that preserve program behavior.

- [Lexing, parsing, and semantic analysis](12_Compilers_and_Runtimes/01_Frontends) (3 units).
- [Bytecode, closures, and memory management](12_Compilers_and_Runtimes/02_Backends_and_runtime_services) (2 units).
- [IR, dataflow, and dynamic compilation](12_Compilers_and_Runtimes/03_Optimizing_compilers) (2 units).

### 13. Computability, complexity, and fundamental limits

Prove what computation can do and distinguish impossibility from resource limits.

- [Automata, grammars, and universality](13_Computability_and_Complexity/01_Computation_models) (4 units).
- [Complexity classes and advanced directions](13_Computability_and_Complexity/02_Resource_bounded_computation) (4 units).

Continues into: [17 Distributed systems and failure semantics](17_Distributed_Systems), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [24 Artificial intelligence and decision-making](24_Artificial_Intelligence), [31 Information theory, coding, and quantum computation](31_Information_Coding_and_Quantum_Computation), [34 Research practice and integrative projects](34_Research_and_Integrative_Projects).

### 14. Software engineering and system evolution

Learn requirements, modularity, collaboration, and maintainability over a system lifetime.

- [Requirements and models](14_Software_Engineering/01_Problem_definition_and_modeling) (2 units).
- [Maintainable code and team practice](14_Software_Engineering/02_Implementation_and_collaboration) (3 units).
- [Builds, releases, and dependable engineering](14_Software_Engineering/03_Delivery_and_dependability) (2 units).

Continues into: [15 Testing, program analysis, and formal methods](15_Testing_and_Formal_Methods), [18 System design and software architecture](18_System_Design_and_Architecture), [21 Web applications with the chosen language stacks](21_Web_and_Application_Engineering), [22 Human-computer interaction and accessibility](22_Human_Computer_Interaction).

### 15. Testing, program analysis, and formal methods

Combine experiments and proofs while understanding the guarantees and limits of each method.

- [Tests, properties, and generated inputs](15_Testing_and_Formal_Methods/01_Test_design) (3 units).
- [Proofs, semantics, and heap reasoning](15_Testing_and_Formal_Methods/02_Program_reasoning) (3 units).
- [State machines, model checking, and analysis](15_Testing_and_Formal_Methods/03_System_specifications) (2 units).

Continues into: [34 Research practice and integrative projects](34_Research_and_Integrative_Projects).

### 16. Concurrent and parallel computation

Reason about interleavings, memory order, progress, task structure, and parallel speedup.

- [Concurrent objects and memory models](16_Concurrency_and_Parallelism/01_Correctness_and_progress) (3 units).
- [Async coordination and parallel algorithms](16_Concurrency_and_Parallelism/02_Structured_tasks_and_parallel_work) (3 units).

Continues into: [17 Distributed systems and failure semantics](17_Distributed_Systems), [29 Embedded systems, real-time computation, and robotics](29_Embedded_Systems_and_Robotics), [30 Numerical, scientific, and high-performance computing](30_Scientific_and_High_Performance_Computing).

### 17. Distributed systems and failure semantics

Understand coordination and replicated state under delay, concurrency, crashes, and partitions.

- [Communication and partial failure](17_Distributed_Systems/01_Communication_time_and_failure) (3 units).
- [Consistency, consensus, and replicated state](17_Distributed_Systems/02_Replication_and_agreement) (4 units).
- [Partitioned processing and adversarial agreement](17_Distributed_Systems/03_Distributed_data_and_trust) (3 units).

Continues into: [18 System design and software architecture](18_System_Design_and_Architecture), [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems).

### 18. System design and software architecture

Design from requirements, invariants, failure models, quantitative evidence, and explicit tradeoffs.

- [Boundaries, requirements, and design evidence](18_System_Design_and_Architecture/01_Architecture_reasoning) (4 units).
- [State, APIs, caches, and asynchronous workflows](18_System_Design_and_Architecture/02_Data_and_request_architecture) (4 units).
- [Failure containment and architecture assessment](18_System_Design_and_Architecture/03_Failure_security_and_evaluation) (3 units).

Continues into: [19 Cloud computing, operations, and reliability](19_Cloud_Operations_and_Reliability), [20 Security engineering and cryptographic foundations](20_Security_and_Cryptography), [34 Research practice and integrative projects](34_Research_and_Integrative_Projects).

### 19. Cloud computing, operations, and reliability

Understand deployment, resource isolation, observability, recovery, and operational tradeoffs.

- [Containers and cloud infrastructure](19_Cloud_Operations_and_Reliability/01_Deployment_foundations) (3 units).
- [Objectives, observability, and recovery](19_Cloud_Operations_and_Reliability/02_Reliability_engineering) (5 units).

Continues into: [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 20. Security engineering and cryptographic foundations

Reason from adversaries and security properties through protocols, implementation, and assurance.

- [Threats, identities, and software boundaries](20_Security_and_Cryptography/01_Security_models_and_implementation) (4 units).
- [Cryptographic definitions and constructions](20_Security_and_Cryptography/02_Modern_cryptography) (6 units).
- [Side channels, privacy, and security evidence](20_Security_and_Cryptography/03_Privacy_and_assurance) (2 units).

Continues into: [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems).

### 21. Web applications with the chosen language stacks

Apply web and API principles using FastAPI, NestJS, React, Astro, and Axum.

- [HTML, CSS, and Tailwind foundations](21_Web_and_Application_Engineering/01_HTML_CSS_and_Tailwind) (3 units).
- [TypeScript user interfaces and rendering](21_Web_and_Application_Engineering/02_React_and_Astro) (4 units).
- [Python APIs with FastAPI and Pydantic](21_Web_and_Application_Engineering/03_Python_FastAPI) (3 units).
- [TypeScript APIs with NestJS](21_Web_and_Application_Engineering/04_TypeScript_NestJS) (3 units).
- [Rust APIs with Axum](21_Web_and_Application_Engineering/05_Rust_Axum) (2 units).
- [Contracts and integration across the selected stacks](21_Web_and_Application_Engineering/06_Cross_stack_contracts) (1 units).

Continues into: [22 Human-computer interaction and accessibility](22_Human_Computer_Interaction), [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 22. Human-computer interaction and accessibility

Study people, tasks, interaction design, and empirical usability rather than visual styling alone.

- [Cognition and interaction design](22_Human_Computer_Interaction/01_Humans_tasks_and_design) (3 units).
- [Accessibility and collaborative interfaces](22_Human_Computer_Interaction/02_Inclusive_and_collaborative_systems) (2 units).

### 23. Data science and data engineering

Deepen the current Python data stack while studying measurement, inference, data quality, and pipelines.

- [NumPy, Pandas, and Polars](23_Data_Science_and_Data_Engineering/01_Array_and_dataframe_models) (4 units).
- [DuckDB, files, lakehouses, and pipeline correctness](23_Data_Science_and_Data_Engineering/02_Analytical_storage_and_pipelines) (4 units).
- [Evidence, causality, and time-series modeling](23_Data_Science_and_Data_Engineering/03_Inference_and_forecasting) (6 units).

Continues into: [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning), [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 24. Artificial intelligence and decision-making

Study symbolic reasoning, search, planning, uncertainty, and rational decisions before model orchestration.

- [Search, games, constraints, and planning](24_Artificial_Intelligence/01_Search_constraints_and_planning) (4 units).
- [Probabilistic reasoning and learning to act](24_Artificial_Intelligence/02_Uncertainty_and_sequential_decisions) (3 units).

Continues into: [25 Statistical machine learning with scikit-learn and XGBoost](25_Machine_Learning), [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems).

### 25. Statistical machine learning with scikit-learn and XGBoost

Connect statistical learning principles to correct estimators, evaluation, and the current modeling stack.

- [Problem formulation and validation](25_Machine_Learning/01_Learning_and_validation) (3 units).
- [Classical estimators and their assumptions](25_Machine_Learning/02_Model_families) (4 units).
- [Interpretation, rare events, ranking, and learning theory](25_Machine_Learning/03_Reliability_and_specialized_learning) (4 units).

Continues into: [26 Deep learning with PyTorch](26_Deep_Learning_with_PyTorch), [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems), [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 26. Deep learning with PyTorch

Derive neural computations and learn to train, diagnose, evaluate, and optimize them in PyTorch.

- [Computation graphs and correct training loops](26_Deep_Learning_with_PyTorch/01_Tensors_autograd_and_training) (4 units).
- [CNNs, sequences, attention, and graph models](26_Deep_Learning_with_PyTorch/02_Representations_and_architectures) (6 units).
- [Memory, distributed training, and neural-model evaluation](26_Deep_Learning_with_PyTorch/03_Evaluation_and_performance) (4 units).

Continues into: [27 Language models, retrieval, and agent systems](27_Language_Models_and_Agent_Systems), [28 Graphics, geometry, image processing, and computer vision](28_Graphics_and_Computer_Vision), [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 27. Language models, retrieval, and agent systems

Study language modeling and retrieval foundations, then build explicit LangChain and LangGraph workflows.

- [Language, tokens, training, and inference](27_Language_Models_and_Agent_Systems/01_Language_model_foundations) (4 units).
- [Retrieval before generation](27_Language_Models_and_Agent_Systems/02_Information_retrieval_and_RAG) (3 units).
- [Typed models, tools, and agent loops](27_Language_Models_and_Agent_Systems/03_LangChain_components) (2 units).
- [State graphs, persistence, and human review](27_Language_Models_and_Agent_Systems/04_LangGraph_state_and_control) (3 units).
- [MCP, adversarial inputs, and agent evaluation](27_Language_Models_and_Agent_Systems/05_Protocol_security_and_evidence) (2 units).

Continues into: [33 MLOps and dependable AI applications](33_MLOps_and_AI_System_Engineering).

### 28. Graphics, geometry, image processing, and computer vision

Understand image synthesis and visual inference, with PyTorch and YOLO for the current vision stack.

- [Geometry, images, and cameras](28_Graphics_and_Computer_Vision/01_Geometry_and_image_formation) (2 units).
- [Ray tracing, light, and simulation](28_Graphics_and_Computer_Vision/02_Rendering_and_animation) (4 units).
- [Geometry inference and the YOLO workflow](28_Graphics_and_Computer_Vision/03_Visual_inference_and_detection) (3 units).

### 29. Embedded systems, real-time computation, and robotics

Connect Rust programs to physical timing, peripherals, sensing, control, and robot motion.

- [Bare-metal Rust and hardware interfaces](29_Embedded_Systems_and_Robotics/01_Embedded_execution) (3 units).
- [Sensing, dynamics, and feedback](29_Embedded_Systems_and_Robotics/02_Cyber_physical_models) (3 units).
- [Kinematics, planning, and localization](29_Embedded_Systems_and_Robotics/03_Robot_motion_and_autonomy) (2 units).

### 30. Numerical, scientific, and high-performance computing

Understand approximation error, numerical stability, simulation, and the cost of scientific computation.

- [Error, linear systems, and nonlinear equations](30_Scientific_and_High_Performance_Computing/01_Numerical_reliability) (3 units).
- [Simulation, discretization, and parallel scientific work](30_Scientific_and_High_Performance_Computing/02_Simulation_and_scaling) (3 units).

### 31. Information theory, coding, and quantum computation

Explore information limits, reliable coding, and quantum models without confusing them with universal speedups.

- [Compression and communication limits](31_Information_Coding_and_Quantum_Computation/01_Information_and_coding) (2 units).
- [Quantum states, algorithms, and limitations](31_Information_Coding_and_Quantum_Computation/02_Quantum_information_and_algorithms) (3 units).

### 32. History, ethics, and social context of computing

Understand how technical systems inherit institutional choices and affect people over time.

- [Historical development and professional judgment](32_History_Ethics_and_Social_Context/01_History_and_professional_responsibility) (2 units).
- [Fairness, privacy, and sustainable systems](32_History_Ethics_and_Social_Context/02_Responsible_data_and_automation) (2 units).

### 33. MLOps and dependable AI applications

Make the current data and AI stack reproducible, inspectable, deployable, and recoverable.

- [MLflow and reproducible model delivery](33_MLOps_and_AI_System_Engineering/01_Experiments_artifacts_and_release) (3 units).
- [Pipeline monitoring and recovery](33_MLOps_and_AI_System_Engineering/02_Data_and_model_operations) (3 units).
- [LLM traces and regression evidence](33_MLOps_and_AI_System_Engineering/03_Agent_observability_and_evaluation) (2 units).

### 34. Research practice and integrative projects

Use the atlas to investigate new questions and demonstrate integrated understanding through substantial artifacts.

- [Reading, reproducing, and extending results](34_Research_and_Integrative_Projects/01_Research_practice) (2 units).
- [Systems and theory synthesis](34_Research_and_Integrative_Projects/02_Systems_and_theory_projects) (3 units).
- [Data, AI, application, and hardware synthesis](34_Research_and_Integrative_Projects/03_Data_AI_and_embedded_projects) (3 units).

## Evidence of understanding

A useful portfolio contains proofs, failed hypotheses, benchmark inputs, recovery traces, and explanations of design tradeoffs alongside working code. Demonstrate invariants and failure behavior, compare alternatives under the same assumptions, and distinguish measured behavior from a general guarantee. The completion tasks provide focused checkpoints; the final projects combine them into larger studies.

Further work can extend specialized subfields and research directions without changing this structure. Add prerequisites, split unrelated objectives, verify source coverage, and update both the study map and topic index. Use official or legitimate sources and record the edition or documentation version used in each learning artifact.
