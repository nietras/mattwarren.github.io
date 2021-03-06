---
layout: post
title: Research based on the .NET Runtime
comments: false
tags: [.NET, Mono, Open Source, Research]
codeproject: false
---

Over the last few years, I've come across more and more research papers based, in some way, on the 'Common Language Runtime' (CLR).

So armed with [Google Scholar](https://scholar.google.com/) and ably assisted by [Semantic Scholar](https://www.semanticscholar.org/), I put together the list below.

**Note:** I put the papers into the following categories to make them easier to navigate (papers in each category are sorted by date, newest -> oldest):

- Using the .NET Runtime as a ***case-study***
  - to prove its *correctness*, study *how it works* or analyse its *behaviour*
- Research carried out by [**Microsoft Research**](https://www.microsoft.com/en-us/research/), the research subsidiary of Microsoft.
  - "*It was formed in 1991, with the intent to advance state-of-the-art computing and solve difficult world problems through technological innovation in collaboration with academic, government, and industry researchers*" ([according to Wikipedia](https://en.wikipedia.org/wiki/Microsoft_Research))
- Papers based on the [**Mono Runtime**](https://www.mono-project.com/)
  - a '*Cross-Platform, open-source .NET framework*'
- Using [**'Rotor'**](https://blogs.msdn.microsoft.com/jasonz/2006/03/23/rotor-sscli-2-0-ships/), real name 'Shared Source CLI (SSCLI)'
  - from [Wikipedia](https://en.wikipedia.org/wiki/Shared_Source_Common_Language_Infrastructure) "*Microsoft provides the Shared Source CLI as a reference CLI implementation suitable for educational use*"

**Any papers I've missed? If so, please let me know in the comments or on [Twitter](https://twitter.com/matthewwarren)**

----

- [**.NET Runtime as a Case-Study**](#net-runtime-as-a-case-study)
  - [**Pitfalls of C# Generics and Their Solution Using Concepts** (Belyakova & Mikhalkovich, 2015)](#pitfalls-of-c-generics-and-their-solution-using-concepts-belyakova--mikhalkovich-2015)
  - [**Efficient Compilation of .NET Programs for Embedded Systems** (Sallenaveab & Ducournaub, 2011)](#efficient-compilation-of-net-programs-for-embedded-systems-sallenaveab--ducournaub-2011)
  - [**Type safety of C# and .Net CLR** (Fruja, 2007)](#type-safety-of-c-and-net-clr-fruja-2007)
  - [**Modeling the .NET CLR Exception Handling Mechanism for a Mathematical Analysis** (Fruja & Börger, 2006)](#modeling-the-net-clr-exception-handling-mechanism-for-a-mathematical-analysis-fruja--b%c3%b6rger-2006)
  - [**Analysis of the .NET CLR Exception Handling Mechanism** (Fruja & Börger, 2005)](#analysis-of-the-net-clr-exception-handling-mechanism-fruja--b%c3%b6rger-2005)
  - [**A Modular Design for the Common Language Runtime (CLR) Architecture** (Fruja, 2005)](#a-modular-design-for-the-common-language-runtime-clr-architecture-fruja-2005)
  - [**Cross-language Program Slicing in the .NET Framework** (Pócza, Biczó & Porkoláb, 2005)](#cross-language-program-slicing-in-the-net-framework-p%c3%b3cza-bicz%c3%b3--porkol%c3%a1b-2005)
  - [**Design and Implementation of a high-level multi-language . NET Debugger** (Strein, 2005)](#design-and-implementation-of-a-high-level-multi-language--net-debugger-strein-2005)
  - [**A High-Level Modular Definition of the Semantics of C#** (Börger, Fruja, Gervasi & Stärk, 2004)](#a-high-level-modular-definition-of-the-semantics-of-c-b%c3%b6rger-fruja-gervasi--st%c3%a4rk-2004)
  - [**An ASM Specification of C# Threads and the .NET Memory Model** (Stärk and Börger, 2004)](#an-asm-specification-of-c-threads-and-the-net-memory-model-st%c3%a4rk-and-b%c3%b6rger-2004)
  - [**Common Language Runtime : a new virtual machine** (Ferreira, 2004)](#common-language-runtime--a-new-virtual-machine-ferreira-2004)
  - [**JVM versus CLR: a comparative study** (Singer, 2003)](#jvm-versus-clr-a-comparative-study-singer-2003)
  - [**Runtime Code Generation with JVM And CLR** (Sestoft, 2002)](#runtime-code-generation-with-jvm-and-clr-sestoft-2002)
- [**Microsoft Research**](#microsoft-research)
  - [**Project Snowflake: Non-blocking safe manual memory management in .NET** (Parkinson, Vaswani, Costa, Deligiannis, Blankstein, McDermott, Balkind & Vytiniotis, 2017)](#project-snowflake-non-blocking-safe-manual-memory-management-in-net-parkinson-vaswani-costa-deligiannis-blankstein-mcdermott-balkind--vytiniotis-2017)
  - [**Simple, Fast and Safe Manual Memory Management** (Kedia, Costa, Vytiniotis, Parkinson, Vaswani & Blankstein, 2017)](#simple-fast-and-safe-manual-memory-management-kedia-costa-vytiniotis-parkinson-vaswani--blankstein-2017)
  - [**Uniqueness and Reference Immutability for Safe Parallelism** (Gordon, Parkinson, Parsons, Bromfield & Duffy, 2012)](#uniqueness-and-reference-immutability-for-safe-parallelism-gordon-parkinson-parsons-bromfield--duffy-2012)
  - [**A study of concurrent real-time garbage collectors** (Pizlo, Petrank & Steensgaard, 2008)](#a-study-of-concurrent-real-time-garbage-collectors-pizlo-petrank--steensgaard-2008)
  - [**Optimizing concurrency levels in the. net threadpool: A case study of controller design and implementation** (Hellerstein, Morrison & Eilebrecht, 2008)](#optimizing-concurrency-levels-in-the-net-threadpool-a-case-study-of-controller-design-and-implementation-hellerstein-morrison--eilebrecht-2008)
  - [**Stopless: a real-time garbage collector for multiprocessors.** (Pizlo, Frampton, Petrank & Steensgaard, 2007)](#stopless-a-real-time-garbage-collector-for-multiprocessors-pizlo-frampton-petrank--steensgaard-2007)
  - [**Securing the .NET Programming Model** (Kennedy, 2006)](#securing-the-net-programming-model-kennedy-2006)
  - [**Combining Generics, Pre-compilation and Sharing Between Software-Based Processes** (Syme & Kennedy, 2004)](#combining-generics-pre-compilation-and-sharing-between-software-based-processes-syme--kennedy-2004)
  - [**Formalization of Generics for the .NET Common Language Runtime** (Yu, Kennedy & Syme, 2004)](#formalization-of-generics-for-the-net-common-language-runtime-yu-kennedy--syme-2004)
  - [**Runtime Verification of .NET Contracts** (Barnett & Schulte, 2003)](#runtime-verification-of-net-contracts-barnett--schulte-2003)
  - [**Design and Implementation of Generics for the .NET Common Language Runtime** (Kennedy & Syme, 2001)](#design-and-implementation-of-generics-for-the-net-common-language-runtime-kennedy--syme-2001)
  - [**Typing a Multi-Language Intermediate Code** (Gordon & Syme, 2001)](#typing-a-multi-language-intermediate-code-gordon--syme-2001)
- [**Mono Runtime**](#mono-runtime)
  - [**Static and Dynamic Analysis of Android Malware and Goodware Written with Unity Framework** (Shim, Lim, Cho, Han & Park, 2018)](#static-and-dynamic-analysis-of-android-malware-and-goodware-written-with-unity-framework-shim-lim-cho-han--park-2018)
  - [**Reducing startup time of a deterministic virtualizing runtime environment** (Däumler & Werner, 2013)](#reducing-startup-time-of-a-deterministic-virtualizing-runtime-environment-d%c3%a4umler--werner-2013)
  - [**Detecting Clones Across Microsoft .NET Programming Languages** (Al-Omari, Keivanloo, Roy & Rilling, 2012)](#detecting-clones-across-microsoft-net-programming-languages-al-omari-keivanloo-roy--rilling-2012)
  - [**Language-independent sandboxing of just-in-time compilation and self-modifying code** (Ansel & Marchenko, 2012)](#language-independent-sandboxing-of-just-in-time-compilation-and-self-modifying-code-ansel--marchenko-2012)
  - [**VMKit: a Substrate for Managed Runtime Environments** (Geoffray, Thomas, Lawall, Muller & Folliot, 2010)](#vmkit-a-substrate-for-managed-runtime-environments-geoffray-thomas-lawall-muller--folliot-2010)
  - [**MMC: the Mono Model Checker** (Ruys & Aan de Brugh, 2007)](#mmc-the-mono-model-checker-ruys--aan-de-brugh-2007)
  - [**Numeric performance in C, C# and Java** (Sestoft, 2007)](#numeric-performance-in-c-c-and-java-sestoft-2007)
  - [[**Mono versus .Net: A Comparative Study of Performance for Distributed Processing.** (Blajian, Eggen, Eggen & Pitts, 2006)]()](#mono-versus-net-a-comparative-study-of-performance-for-distributed-processing-blajian-eggen-eggen--pitts-2006)
  - [**Mono versus .Net: A Comparative Study of Performance for Distributed Processing.** (Blajian, Eggen, Eggen & Pitts, 2006)](#mono-versus-net-a-comparative-study-of-performance-for-distributed-processing-blajian-eggen-eggen--pitts-2006)
  - [**Automated detection of performance regressions: the mono experience** (Kalibera, Bulej & Tuma, 2005)](#automated-detection-of-performance-regressions-the-mono-experience-kalibera-bulej--tuma-2005)
- [**Shared Source Common Language Infrastructure** (SSCLI) - a.k.a '**Rotor**'](#shared-source-common-language-infrastructure-sscli---aka-rotor)
  - [**Efficient virtual machine support of runtime structural reflection** (Ortina, Redondoa & Perez-Schofield, 2009)](#efficient-virtual-machine-support-of-runtime-structural-reflection-ortina-redondoa--perez-schofield-2009)
  - [**Extending the SSCLI to Support Dynamic Inheritance** (Redondo, Ortin & Perez-Schofield, 2008)](#extending-the-sscli-to-support-dynamic-inheritance-redondo-ortin--perez-schofield-2008)
  - [**Sampling profiler for Rotor as part of optimizing compilation system** (Chilingarova & Safonov, 2006)](#sampling-profiler-for-rotor-as-part-of-optimizing-compilation-system-chilingarova--safonov-2006)
  - [**To JIT or not to JIT: The effect of code-pitching on the performance of .NET framework** (Anthony, Leung & Srisa-an, 2005)](#to-jit-or-not-to-jit-the-effect-of-code-pitching-on-the-performance-of-net-framework-anthony-leung--srisa-an-2005)
  - [**Adding structural reflection to the SSCLI** (Ortin, Redondo, Vinuesa & Lovelle, 2005)](#adding-structural-reflection-to-the-sscli-ortin-redondo-vinuesa--lovelle-2005)
  - [**Static Analysis for Identifying and Allocating Clusters of Immortal Objects** (Ravindar & Srikant, 2005)](#static-analysis-for-identifying-and-allocating-clusters-of-immortal-objects-ravindar--srikant-2005)
  - [**An Optimizing Just-InTime Compiler for Rotor** (Trindade & Silva, 2005)](#an-optimizing-just-intime-compiler-for-rotor-trindade--silva-2005)
  - [**Software Interactions into the SSCLI platform** (Charfi & Emsellem, 2004)](#software-interactions-into-the-sscli-platform-charfi--emsellem-2004)
  - [**Experience Integrating a New Compiler and a New Garbage Collector Into Rotor** (Anderson, Eng, Glew, Lewis, Menon & Stichnoth, 2004)](#experience-integrating-a-new-compiler-and-a-new-garbage-collector-into-rotor-anderson-eng-glew-lewis-menon--stichnoth-2004)

----

## **.NET Runtime as a Case-Study**

### [**Pitfalls of C# Generics and Their Solution Using Concepts** (Belyakova & Mikhalkovich, 2015)](https://www.researchgate.net/publication/277564142_Pitfalls_of_C_Generics_and_Their_Solution_Using_Concepts)

**Abstract**

In comparison with Haskell type classes and C ++ concepts, such object-oriented languages as C# and Java provide much limited mechanisms of generic programming based on F-bounded polymorphism. Main pitfalls of C# generics are considered in this paper. Extending C# language with concepts which can be simultaneously used with interfaces is proposed to solve the problems of generics; a design and translation of concepts are outlined.

### [**Efficient Compilation of .NET Programs for Embedded Systems** (Sallenaveab & Ducournaub, 2011)](https://www.researchgate.net/publication/260107282_Efficient_Compilation_of_NET_Programs_for_Embedded_Systems)

**Abstract**

Compiling under the closed-world assumption (CWA) has been shown to be an appropriate way for implementing object-oriented languages such as Java on low-end embedded systems. In this paper, we explore the implications of using whole program optimizations such as Rapid Type Analysis (RTA) and coloring on programs targeting the .NET infrastructure. We extended RTA so that it takes into account .NET specific features such as (i) array covariance, a language feature also supported in Java, (ii) generics, whose specifications in .Net impacts type analysis and (iii) delegates, which encapsulate methods within objects. We also use an intraprocedural control flow analysis in addition to RTA . We eval-uated the optimizations that we implemented on programs written in C#. Preliminary results show a noticeable reduction of the code size, class hierarchy and polymorphism of the programs we optimize. Array covariance is safe in almost all cases, and some delegate calls can be implemented as direct calls.

### [**Type safety of C# and .Net CLR** (Fruja, 2007)](https://www.research-collection.ethz.ch/handle/20.500.11850/72699)

**Abstract**

Type safety plays a crucial role in the security enforcement of any typed programming language. This thesis presents a formal proof of C#'s type safety. For this purpose, we develop an abstract
framework for C#, comprising formal specifications of the language's grammar, of the statically correct programs, and of the static and operational semantics. Using this framework, we prove that C# is type-safe, by showing that the execution of statically correct C# programs does not lead to type errors.

### [**Modeling the .NET CLR Exception Handling Mechanism for a Mathematical Analysis** (Fruja & Börger, 2006)](https://www.semanticscholar.org/paper/Modeling-the-.NET-CLR-Exception-Handling-Mechanism-Fruja-B%C3%B6rger/a6fe1d4763a70d5a5658f83e9f56135725c772a6)

**Abstract**

This work is part of a larger project which aims at establishing some important properties of C# and CLR by mathematical proofs. Examples are the correctness of the bytecode verifier of CLR, the type safety (along the lines of the first author's correctness proof for the definite assignment rules) of C#, the correctness of a general compilation scheme.

### [**Analysis of the .NET CLR Exception Handling Mechanism** (Fruja & Börger, 2005)](https://www.semanticscholar.org/paper/Analysis-of-the-.NET-CLR-Exception-Handling-Fruja-B%C3%83%C2%B6rger/0155d293eb444358542828e0405c8c754f543da0)

**Abstract**

We provide a complete mathematical model for the exception handling mechanism of the Common Language Runtime (CLR), the virtual machine underlying the interpretation of .NET programs. The goal is to use this rigorous model in the corresponding part of the still-to-be-developed soundness proof for the CLR bytecode verifier.

### [**A Modular Design for the Common Language Runtime (CLR) Architecture** (Fruja, 2005)](https://www.semanticscholar.org/paper/A-Modular-Design-for-the-Common-Language-Runtime-Fruja/b2bd42f6ff8970777ae3c1cc87a65d963c891082)

**Abstract**

This paper provides a modular high-level design of the Common Language Runtime (CLR) architecture. Our design is given in terms of Abstract State Machines (ASMs) and takes the form of an interpreter. We describe the CLR as a hierarchy of eight submachines, which correspond to eight submodules into which the Common Intermediate Language (CIL) instruction set can be decomposed.

### [**Cross-language Program Slicing in the .NET Framework** (Pócza, Biczó & Porkoláb, 2005)](https://www.semanticscholar.org/paper/Cross-language-Program-Slicing-in-the-.NET-P%C3%B3cza-Bicz%C3%B3/d0fffd3b754f2ab1181e108e7a416bb23c8612d7)

**Abstract**

Dynamic program slicing methods are very attractive for debugging because many statements can be ignored in the process of localizing a bug. Although language interoperability is a key concept in modern development platforms, current slicing techniques are still restricted to a single language. In this paper a cross-language dynamic program slicing technique is introduced for the .NET environment. The method is utilizing the CLR Debugging Services API, hence it can be applied to large multi-language applications.

### [**Design and Implementation of a high-level multi-language . NET Debugger** (Strein, 2005)](https://www.semanticscholar.org/paper/Design-and-Implementation-of-a-high-level-.-NET-Strein/811ae0dcda26249f7722a7315e9970be4f830b93)

**Abstract**

The Microsoft .NET Common Language Runtime (CLR) provides a low-level debugging application programmers interface (API), which can be used to implement traditional source code debuggers but can also be useful to implement other dynamic program introspection tools. This paper describes our experience in using this API for the implementation of a high-level debugger. The API is difficult to use from a technical point of view because it is implemented as a set of Component Object Model (COM) interfaces instead of a managed .NET API. Nevertheless, it is possible to implement a debugger in managed C# code using COM-interop. We describe our experience in taking this approach. We define a high-level debugging API and implement it in the C# language using COM-interop to access the low-level debugging API. Furthermore, we describe the integration of this high-level API in the multi-language development environment X-develop to enable source code debugging of .NET languages. This paper can be useful for anybody who wants to take the same approach to implement debuggers or other tools for dynamic program introspection.

### [**A High-Level Modular Definition of the Semantics of C#** (Börger, Fruja, Gervasi & Stärk, 2004)](https://www.sciencedirect.com/science/article/pii/S0304397504007765)

**Abstract**

We propose a structured mathematical definition of the semantics of  programs to provide a platform-independent interpreter view of the language for the  programmer, which can also be used for a precise analysis of the ECMA standard of the language and as a reference model for teaching. The definition takes care to reflect directly and faithfully—as much as possible without becoming inconsistent or incomplete—the descriptions in the  standard to become comparable with the corresponding models for Java in Stärk et al. (Java and Java Virtual Machine—Definition, Verification, Validation, Springer, Berlin, 2001) and to provide for implementors the possibility to check their basic design decisions against an accurate high-level model. The model sheds light on some of the dark corners of  and on some critical differences between the ECMA standard and the implementations of the language.

### [**An ASM Specification of C# Threads and the .NET Memory Model** (Stärk and Börger, 2004)](https://link.springer.com/chapter/10.1007/978-3-540-24773-9_4)

**Abstract**

We present a high-level ASM model of C# threads and the .NET memory model. We focus on purely managed, fully portable threading features of C#. The sequential model interleaves the computation steps of the currently running threads and is suitable for uniprocessors. The parallel model addresses problems of true concurrency on multiprocessor systems. The models provide a sound basis for the development of multi-threaded applications in C#. The thread and memory models complete the abstract operational semantics of C# in.

### [**Common Language Runtime : a new virtual machine** (Ferreira, 2004)](https://www.semanticscholar.org/paper/Common-Language-Runtime-%3A-a-new-virtual-machine-Ferreira/fec4a355450eb0c935fe3ccff9d296529b11b873)

**Abstract**

Virtual Machines provide a runtime execution platform combining bytecode portability with a performance close to native code. An overview of current approaches precedes an insight into Microsoft CLR (Common Language Runtime), comparing it to Sun JVM (Java Virtual Machine) and to a native execution environment (IA 32). A reference is also made to CLR in a Unix platform and to techniques on how CLR improves code execution.

### [**JVM versus CLR: a comparative study** (Singer, 2003)](https://www.semanticscholar.org/paper/JVM-versus-CLR%3A-a-comparative-study-Singer/b57aaf581e043fb63c56ebd662720190e3121220)

**Abstract**

We present empirical evidence to demonstrate that there is little or no difference between the Java Virtual Machine and the .NET Common Language Runtime, as regards the compilation and execution of object-oriented programs. Then we give details of a case study that proves the superiority of the Common Language Runtime as a target for imperative programming language compilers (in particular GCC).

### [**Runtime Code Generation with JVM And CLR** (Sestoft, 2002)](https://www.researchgate.net/publication/2831690_Runtime_Code_Generation_with_JVM_And_CLR)

**Abstract**

Modern bytecode execution environments with optimizing just-in-time compilers, such as Sun's Hotspot Java Virtual Machine, IBM's Java Virtual Machine, and Microsoft's Common Language Runtime, provide an infrastructure for generating fast code at runtime. Such runtime code generation can be used for efficient implementation of parametrized algorithms. More generally, with runtime code generation one can introduce an additional binding-time without performance loss. This permits improved performance and improved static correctness guarantees.

----

## **Microsoft Research**

### [**Project Snowflake: Non-blocking safe manual memory management in .NET** (Parkinson,  Vaswani, Costa, Deligiannis, Blankstein, McDermott, Balkind & Vytiniotis, 2017)](https://www.microsoft.com/en-us/research/publication/project-snowflake-non-blocking-safe-manual-memory-management-net/)

**Abstract**

Garbage collection greatly improves programmer productivity and ensures memory safety. Manual memory management on the other hand often delivers better performance but is typically unsafe and can lead to system crashes or security vulnerabilities. We propose integrating safe manual memory management with garbage collection in the .NET runtime to get the best of both worlds. In our design, programmers can choose between allocating objects in the garbage collected heap or the manual heap. All existing applications run unmodified, and without any performance degradation, using the garbage collected heap. Our programming model for manual memory management is flexible: although objects in the manual heap can have a single owning pointer, we allow deallocation at any program point and concurrent sharing of these objects amongst all the threads in the program. Experimental results from our .NET CoreCLR implementation on real-world applications show substantial performance gains especially in multithreaded scenarios: up to 3x savings in peak working sets and 2x improvements in runtime.

### [**Simple, Fast and Safe Manual Memory Management** (Kedia, Costa, Vytiniotis, Parkinson, Vaswani & Blankstein, 2017)](https://www.microsoft.com/en-us/research/publication/simple-fast-safe-manual-memory-management/)

**Abstract**

Safe programming languages are readily available, but many applications continue to be written in unsafe languages, because the latter are more efficient. As a consequence, many applications continue to have exploitable memory safety bugs. Since garbage collection is a major source of inefficiency in the implementation of safe languages, replacing it with safe manual memory management would be an important step towards solving this problem.

Previous approaches to safe manual memory management use programming models based on regions, unique pointers, borrowing of references, and ownership types. We propose a much simpler programming model that does not require any of these concepts. Starting from the design of an imperative type safe language (like Java or C#), we just add a delete operator to free memory explicitly and an exception which is thrown if the program dereferences a pointer to freed memory. We propose an efficient implementation of this programming model that guarantees type safety. Experimental results from our implementation based on the C# native compiler show that this design achieves up to 3x reduction in peak working set and run time.

### [**Uniqueness and Reference Immutability for Safe Parallelism** (Gordon,  Parkinson, Parsons, Bromfield & Duffy, 2012)](https://www.microsoft.com/en-us/research/publication/uniqueness-and-reference-immutability-for-safe-parallelism/)

**Abstract**

A key challenge for concurrent programming is that side-effects (memory operations) in one thread can affect the behavior of another thread. In this paper, we present a type system to restrict the updates to memory to prevent these unintended side-effects. We provide a novel combination of immutable and unique (isolated) types that ensures safe parallelism (race freedom and deterministic execution). The type system includes support for polymorphism over type qualifiers, and can easily create cycles of immutable objects. Key to the system’s flexibility is the ability to recover immutable or externally unique references after violating uniqueness without any explicit alias tracking. Our type system models a prototype extension to C# that is in active use by a Microsoft team. We describe their experiences building large systems with this extension. We prove the soundness of the type system by an embedding into a program logic.

### [**A study of concurrent real-time garbage collectors** (Pizlo, Petrank & Steensgaard, 2008)](https://www.semanticscholar.org/paper/A-study-of-concurrent-real-time-garbage-collectors-Pizlo-Petrank/9d3f2b64fef6b8e66a081eae760bf3afed086687)

**Abstract**

Concurrent garbage collection is highly attractive for real-time systems, because offloading the collection effort from the executing threads allows faster response, allowing for extremely short deadlines at the microseconds level. Concurrent collectors also offer much better scalability over incremental collectors. The main problem with concurrent real-time collectors is their complexity. The first concurrent real-time garbage collector that can support fine synchronization, STOPLESS, has recently been presented by Pizlo et al. In this paper, we propose two additional (and different) algorithms for concurrent real-time garbage collection: CLOVER and CHICKEN. Both collectors obtain reduced complexity over the first collector STOPLESS, but need to trade a benefit for it. We study the algorithmic strengths and weaknesses of CLOVER and CHICKEN and compare them to STOPLESS. Finally, we have implemented all three collectors on the Bartok compiler and runtime for C# and we present measurements to compare their efficiency and responsiveness.

### [**Optimizing concurrency levels in the. net threadpool: A case study of controller design and implementation** (Hellerstein, Morrison & Eilebrecht, 2008)](https://www.researchgate.net/publication/228977836_Optimizing_concurrency_levels_in_the_net_threadpool_A_case_study_of_controller_design_and_implementation)

**Abstract**

This paper presents a case study of developing a hill climb-ing concurrency controller (HC 3) for the .NET ThreadPool. The intent of the case study is to provide insight into soft-ware considerations for controller design, testing, and imple-mentation. The case study is structured as a series of issues encountered and approaches taken to their resolution. Ex-amples of issues and approaches include: (a) addressing the need to combine a hill climbing control law with rule-based techniques by the use of hybrid control; (b) increasing the ef-ficiency and reducing the variability of the test environment by using resource emulation; and (c) effectively assessing design choices by using test scenarios for which the optimal concurrency level can be computed analytically and hence desired test results are known a priori. We believe that these issues and approaches have broad application to controllers for resource management of software systems.

### [**Stopless: a real-time garbage collector for multiprocessors.** (Pizlo, Frampton, Petrank & Steensgaard, 2007)](https://www.researchgate.net/publication/221032935_Stopless_a_real-time_garbage_collector_for_multiprocessors)

**Abstract**

We present STOPLESS: a concurrent real-time garbage collector suitable for modern multiprocessors running parallel multithreaded applications. Creating a garbage-collected environment that sup- ports real-time on modern platforms is notoriously hard, especially if real-time implies lock-freedom. Known real-time collectors ei- ther restrict the real-time guarantees to uniprocessors only, rely on special hardware, or just give up supporting atomic operations (which are crucial for lock-free software). STOPLESS is the first collector that provides real-time responsiveness while preserving lock-freedom, supporting atomic operations, controlling fragmen- tation by compaction, and supporting modern parallel platforms. STOPLESS is adequate for modern languages such as C# or Java. It was implemented on top of the Bartok compiler and runtime for C# and measurements demonstrate high responsiveness (a factor of a 100 better than previously published systems), virtually no pause times, good mutator utilization, and acceptable overheads.

### [**Securing the .NET Programming Model** (Kennedy, 2006)](https://www.microsoft.com/en-us/research/publication/securing-the-net-programming-model/)

**Abstract**

The security of the .NET programming model is studied from the standpoint of fully abstract compilation of C#. A number of failures of full abstraction are identified, and fixes described. The most serious problems have recently been fixed for version 2.0 of the .NET Common Language Runtime.

### [**Combining Generics, Pre-compilation and Sharing Between Software-Based Processes** (Syme & Kennedy, 2004)](https://www.microsoft.com/en-us/research/publication/combining-generics-pre-compilation-and-sharing-between-software-based-processes/)

**Abstract**

We describe problems that have arisen when combining the proposed design for generics for the Microsoft .NET Common Language Runtime (CLR) with two resource-related features supported by the Microsoft CLR implementation: application domains and pre-compilation. Application domains are “software based processes” and the interaction between application domains and generics stems from the fact that code and descriptors are generated on a pergeneric-instantiation basis, and thus instantiations consume resources which are preferably both shareable and recoverable. Pre-compilation runs at install-time to reduce startup overheads. This interacts with application domain unloading: compilation units may contain shareable generated instantiations. The paper describes these interactions and the diﬀerent approaches that can be used to avoid or ameliorate the problems.

### [**Formalization of Generics for the .NET Common Language Runtime** (Yu, Kennedy & Syme, 2004)](https://www.microsoft.com/en-us/research/publication/formalization-of-generics-for-the-net-common-language-runtime/)

**Abstract**

We present a formalization of the implementation of generics in the .NET Common Language Runtime (CLR), focusing on two novel aspects of the implementation: mixed specialization and sharing, and efficient support for run-time types. Some crucial constructs used in the implementation are dictionaries and run-time type representations. We formalize these aspects type-theoretically in a way that corresponds in spirit to the implementation techniques used in practice. Both the techniques and the formalization also help us understand the range of possible implementation techniques for other languages, e.g., ML, especially when additional source language constructs such as run-time types are supported. A useful by-product of this study is a type system for a subset of the polymorphic IL proposed for the .NET CLR.

### [**Runtime Verification of .NET Contracts** (Barnett & Schulte, 2003)](https://www.microsoft.com/en-us/research/publication/runtime-verification-of-net-contracts/)

**Abstract**

We propose a method for implementing behavioral interface specifications on the .NET platform. Our interface specifications are expressed as executable model programs. Model programs can be run either as stand-alone simulations or used as contracts to check the conformance of an implementation class to its specification. We focus on the latter, which we call runtime verification.In our framework, model programs are expressed in the new specification language AsmL. We describe how AsmL can be used to describe contracts independently from any implementation language, how AsmL allows properties of component interaction to be specified using mandatory calls, and how AsmL is used to check the behavior of a component written in any of the .NET languages, such as VB, C#, or C++.

### [**Design and Implementation of Generics for the .NET Common Language Runtime** (Kennedy & Syme, 2001)](https://www.microsoft.com/en-us/research/publication/design-and-implementation-of-generics-for-the-net-common-language-runtime/)

**Abstract**

The Microsoft .NET Common Language Runtime provides a shared type system, intermediate language and dynamic execution environment for the implementation and inter-operation of multiple source languages. In this paper we extend it with direct support for parametric polymorphism (also known as generics), describing the design through examples written in an extended version of the C# programming language, and explaining aspects of implementation by reference to a prototype extension to the runtime. Our design is very expressive, supporting parameterized types, polymorphic static, instance and virtual methods, “F-bounded” type parameters, instantiation at pointer and value types, polymorphic recursion, and exact run-time types. The implementation takes advantage of the dynamic nature of the runtime, performing justin-time type specialization, representation-based code sharing and novel techniques for efﬁcient creation and use of run-time types. Early performance results are encouraging and suggest that programmers will not need to pay an overhead for using generics, achieving performance almost matching hand-specialized code.

### [**Typing a Multi-Language Intermediate Code** (Gordon & Syme, 2001)](https://www.microsoft.com/en-us/research/publication/typing-a-multi-language-intermediate-code/)

**Abstract**

The Microsoft .NET Framework is a new computing architecture designed to support a variety of distributed applications and web-based services. .NET software components are typically distributed in an object-oriented intermediate language, Microsoft IL, executed by the Microsoft Common Language Runtime. To allow convenient multi-language working, IL supports a wide variety of high-level language constructs, including class-based objects, inheritance, garbage collection, and a security mechanism based on type safe execution. This paper precisely describes the type system for a substantial fragment of IL that includes several novel features: certain objects may be allocated either on the heap or on the stack; those on the stack may be boxed onto the heap, and those on the heap may be unboxed onto the stack; methods may receive arguments and return results via typed pointers, which can reference both the stack and the heap, including the interiors of objects on the heap. We present a formal semantics for the fragment. Our typing rules determine well-typed IL instruction sequences that can be assembled and executed. Of particular interest are rules to ensure no pointer into the stack outlives its target. Our main theorem asserts type safety, that well-typed programs in our IL fragment do not lead to untrapped execution errors. Our main theorem does not directly apply to the product. Still, the formal system of this paper is an abstraction of informal and executable specifications we wrote for the full product during its development. Our informal specification became the basis of the product team’s working specification of type-checking. The process of writing this specification, deploying the executable specification as a test oracle, and applying theorem proving techniques, helped us identify several security critical bugs during development.

----

## **Mono Runtime**

### [**Static and Dynamic Analysis of Android Malware and Goodware Written with Unity Framework** (Shim, Lim, Cho, Han & Park, 2018)](https://www.semanticscholar.org/paper/Static-and-Dynamic-Analysis-of-Android-Malware-and-Shim-Lim/e270ebdde1988b4d99d7721d664c046ffaa366f1)

**Abstract**

Unity is the most popular cross-platform development framework to develop games for multiple platforms such as Android, iOS, and Windows Mobile. While Unity developers can easily develop mobile apps for multiple platforms, adversaries can also easily build malicious apps based on the “write once, run anywhere” (WORA) feature. Even thoughmalicious apps were discovered among Android apps written with Unity framework (Unity apps), little research has been done on analysing the malicious apps. We propose static and dynamic reverse engineering techniques for malicious Unity apps. We first inspect the executable file format of a Unity app and present an effective static analysis technique of the Unity app. Then, we also propose a systematic technique to analyse dynamically the Unity app. Using the proposed techniques, the malware analyst can statically and dynamically analyse Java code, native code in C or C ++, and the Mono runtime layer where the C# code is running.

### [**Reducing startup time of a deterministic virtualizing runtime environment** (Däumler & Werner, 2013)](https://dl.acm.org/citation.cfm?id=2463604)

**Abstract**

Virtualized runtime environments like Java Virtual Machine (JVM) or Microsoft .NET's Common Language Runtime (CLR) introduce additional challenges to real-time software development. Since applications for such environments are usually deployed in platform independent intermediate code, one issue is the timing of code transformation from intermediate code into native code. We have developed a solution for this problem, so that code transformation is suitable for real-time systems. It combines pre-compilation of intermediate code with the elimination of indirect references in native code. The gain of determinism comes with an increased application startup time. In this paper we present an optimization that utilizes an Ahead-of-Time compiler to reduce the startup time while keeping the real-time suitable timing behaviour. In an experiment we compare our approach with existing ones and demonstrate its benefits for certain application cases.

### [**Detecting Clones Across Microsoft .NET Programming Languages** (Al-Omari,  Keivanloo, Roy & Rilling, 2012)](https://www.semanticscholar.org/paper/Detecting-Clones-Across-Microsoft-.NET-Programming-Al-Omari-Keivanloo/22241ada86ef977315cc6c5978ce0a0636e1850c#paper-header)

**Abstract**

The Microsoft .NET framework and its language family focus on multi-language development to support interoperability across several programming languages. The framework allows for the development of similar applications in different languages through the reuse of core libraries. As a result of such a multi-language development, the identification and trace ability of similar code fragments (clones) becomes a key challenge. In this paper, we present a clone detection approach for the .NET language family. The approach is based on the Common Intermediate Language, which is generated by the .NET compiler for the different languages within the .NET framework. In order to achieve an acceptable recall while maintaining the precision of our detection approach, we define a set of filtering processes to reduce noise in the raw data. We show that these filters are essential for Intermediate Language-based clone detection, without significantly affecting the precision of the detection approach. Finally, we study the quantitative and qualitative performance aspects of our clone detection approach. We evaluate the number of reported candidate clone-pairs, as well as the precision and recall (using manual validation) for several open source cross-language systems, to show the effectiveness of our proposed approach.

### [**Language-independent sandboxing of just-in-time compilation and self-modifying code** (Ansel & Marchenko, 2012)](https://www.researchgate.net/publication/314841984_Language-independent_sandboxing_of_just-in-time_compilation_and_self-modifying_code)

**Abstract**

When dealing with dynamic, untrusted content, such as on the Web, software behavior must be sandboxed, typically through use of a language like JavaScript. However, even for such specially-designed languages, it is difficult to ensure the safety of highly-optimized, dynamic language runtimes which, for efficiency, rely on advanced techniques such as Just-In-Time (JIT) compilation, large libraries of native-code support routines, and intricate mechanisms for multi-threading and garbage collection. Each new runtime provides a new potential attack surface and this security risk raises a barrier to the adoption of new languages for creating untrusted content. Removing this limitation, this paper introduces general mechanisms for safely and efficiently sandboxing software, such as dynamic language runtimes, that make use of advanced, low-level techniques like runtime code modification. Our language-independent sandboxing builds on Software-based Fault Isolation (SFI), a traditionally static technique. We provide a more flexible form of SFI by adding new constraints and mechanisms that allow safety to be guaranteed despite runtime code modifications. We have added our extensions to both the x86-32 and x86-64 variants of a production-quality, SFI-based sandboxing platform; on those two architectures SFI mechanisms face different challenges. We have also ported two representative language platforms to our extended sandbox: the Mono common language runtime and the V8 JavaScript engine. In detailed evaluations, we find that sandboxing slowdown varies between different benchmarks, languages, and hardware platforms. Overheads are generally moderate and they are close to zero for some important benchmark/platform combinations.

### [**VMKit: a Substrate for Managed Runtime Environments** (Geoffray, Thomas, Lawall, Muller & Folliot, 2010)](https://www.researchgate.net/publication/221137881_VMKit_a_Substrate_for_Managed_Runtime_Environments)

**Abstract**

Managed Runtime Environments (MREs), such as the JVM and the CLI, form an attractive environment for program execution, by providing portability and safety, via the use of a bytecode language and automatic memory management, as well as good performance, via just-in-time (JIT) compilation. Nevertheless, developing a fully featured MRE, including e.g. a garbage collector and JIT compiler, is a herculean task. As a result, new languages cannot easily take advantage of the benefits of MREs, and it is difficult to experiment with extensions of existing MRE based languages. This paper describes and evaluates VMKit, a first attempt to build a common substrate that eases the development of high-level MREs. We have successfully used VMKit to build two MREs: a Java Virtual Machine and a Common Language Runtime. We provide an extensive study of the lessons learned in developing this infrastructure, and assess the ease of implementing new MREs or MRE extensions and the resulting performance. In particular, it took one of the authors only one month to develop a Common Language Runtime using VMKit. VMKit furthermore has performance comparableto the well established open source MREs Cacao, Apache Harmony and Mono, and is 1.2 to 3 times slower than JikesRVM on most of the Dacapo benchmarks.

### [**MMC: the Mono Model Checker** (Ruys & Aan de Brugh, 2007)](https://www.sciencedirect.com/science/article/pii/S1571066107005348)

**Abstract**

The Mono Model Checker (mmc) is a software model checker for cil bytecode programs. mmc has been developed on the Mono platform. mmc is able to detect deadlocks and assertion violations in cil programs. The design of mmc is inspired by the Java PathFinder (jpf), a model checker for Java programs. The performance of mmc is comparable to jpf. This paper introduces mmc and presents its main architectural characteristics.

### [**Numeric performance in C, C# and Java** (Sestoft, 2007)](https://www.researchgate.net/publication/228380860_Numeric_performance_in_C_C_and_Java)

**Abstract**

We compare the numeric performance of C, C# and Java on three small cases.

### [**Mono versus .Net: A Comparative Study of Performance for Distributed Processing.** (Blajian, Eggen, Eggen & Pitts, 2006)](https://www.researchgate.net/publication/221134118_Mono_versus_net_A_Comparative_Study_of_Performance_for_Distributed_Processing)

**Abstract**

Microsoft has released .NET, a platform dependent standard for the C#,programming language. Sponsored by Ximian/Novell, Mono, the open source development platform based on the .NET framework, has been developed to be a platform independent version of the C#,programming environment. While .NET is platform dependent, Mono allows developers to build Linux and crossplatform applications. Mono’s .NET implementation is based on the ECMA standards for C#. This paper examines both of these programming environments with the goal of evaluating the performance characteristics of each. Testing is done with various algorithms. We also assess the trade-offs associated with using a cross-platform versus a platform.

### [**Automated detection of performance regressions: the mono experience** (Kalibera, Bulej & Tuma, 2005)](https://www.semanticscholar.org/paper/Automated-detection-of-performance-regressions%3A-the-Kalibera-Bulej/3b4c7756340df10a7c73a5646931763a9e81ee05)

**Abstract**

Engineering a large software project involves tracking the impact of development and maintenance changes on the software performance. An approach for tracking the impact is regression benchmarking, which involves automated benchmarking and evaluation of performance at regular intervals. Regression benchmarking must tackle the nondeterminism inherent to contemporary computer systems and execution environments and the impact of the nondeterminism on the results. On the example of a fully automated regression benchmarking environment for the mono open-source project, we show how the problems associated with nondeterminism can be tackled using statistical methods.

----

## **Shared Source Common Language Infrastructure** (SSCLI) - a.k.a '**Rotor**'

### [**Efficient virtual machine support of runtime structural reflection** (Ortina, Redondoa & Perez-Schofield, 2009)](https://www.sciencedirect.com/science/article/pii/S0167642309000689)

**Abstract**

Increasing trends towards adaptive, distributed, generative and pervasive software have made object-oriented dynamically typed languages become increasingly popular. These languages offer dynamic software evolution by means of reflection, facilitating the development of dynamic systems. Unfortunately, this dynamism commonly imposes a runtime performance penalty. In this paper, we describe how to extend a production JIT-compiler virtual machine to support runtime object-oriented structural reflection offered by many dynamic languages. Our approach improves runtime performance of dynamic languages running on statically typed virtual machines. At the same time, existing statically typed languages are still supported by the virtual machine.

We have extended the .Net platform with runtime structural reflection adding prototype-based object-oriented semantics to the statically typed class-based model of .Net, supporting both kinds of programming languages. The assessment of runtime performance and memory consumption has revealed that a direct support of structural reflection in a production JIT-based virtual machine designed for statically typed languages provides a significant performance improvement for dynamically typed languages.

### [**Extending the SSCLI to Support Dynamic Inheritance** (Redondo, Ortin & Perez-Schofield, 2008)](https://link.springer.com/chapter/10.1007/978-3-642-05201-9_2)

**Abstract**

This paper presents a step forward on a research trend focused on increasing runtime adaptability of commercial JIT-based virtual machines, describing how to include dynamic inheritance into this kind of platforms. A considerable amount of research aimed at improving runtime performance of virtual machines has converted them into the ideal support for developing different types of software products. Current virtual machines do not only provide benefits such as application interoperability, distribution and code portability, but they also offer a competitive runtime performance.

Since JIT compilation has played a very important role in improving runtime performance of virtual machines, we first extended a production JIT-based virtual machine to support efficient language-neutral structural reflective primitives of dynamically typed programming languages. This article presents the next step in our research work: supporting language-neutral dynamic inheritance for both statically and dynamically typed programming languages. Executing both kinds of programming languages over the same platform provides a direct interoperation between them.

### [**Sampling profiler for Rotor as part of optimizing compilation system** (Chilingarova & Safonov, 2006)](https://www.semanticscholar.org/paper/Sampling-profiler-for-Rotor-as-part-of-optimizing-Chilingarova/99e874d7fd5ab5f890d599759a875ef2212e6a3b)

**Abstract**

This paper describes a low-overhead self-tuning sampling-based runtime profiler integrated into SSCLI virtual machine. Our profiler estimates how “hot” a method is and builds a call context graph based on managed stack samples analysis. The frequency of sampling is tuned dynamically at runtime, based on the information of how often the same activation record appears on top of the stack. The call graph is presented as a novel Call Context Map (CC-Map) structure that combines compact representation and accurate information about the context. It enables fast extraction of data helpful in making compilation decisions, as well as fast placing data into the map. Sampling mechanism is integrated with intrinsic Rotor mechanisms of thread preemption and stack walk. A separate system thread is responsible for organizing data in the CC-Map. This thread gathers and stores samples quickly queued by managed threads, thus decreasing the time they must hold up their user-scheduled job

### [**To JIT or not to JIT: The effect of code-pitching on the performance of .NET framework** (Anthony, Leung & Srisa-an, 2005)](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.127.9138)

**Abstract**

The.NET Compact Framework is designed to be a highperformance virtual machine for mobile and embedded devices that operate on Windows CE (version 4.1 and later). It achieves fast execution time by compiling methods dynamically instead of using interpretation. Once compiled, these methods are stored in a portion of the heap called code-cache and can be reused quickly to satisfy future method calls. While code-cache provides a high-level of reusability, it can also use a large amount of memory. As a result, the Compact Framework provides a “code pitching ” mechanism that can be used to discard the previously compiled methods as needed. In this paper, we study the effect of code pitching on the overall performance and memory utilization of.NET applications. We conduct our experiments using Microsoft’s Shared-Source Common Language Infrastructure (SSCLI). We profile the access behavior of the compiled methods. We also experiment with various code-cache configurations to perform pitching. We find that programs can operate efficiently with a small code-cache without incurring substantial recompilation and execution overheads.

### [**Adding structural reflection to the SSCLI** (Ortin, Redondo, Vinuesa & Lovelle, 2005)](https://www.researchgate.net/publication/249898327_Adding_structural_reflection_to_the_SSCLI)

**Abstract**

Although dynamic languages are becoming widely used due to the flexibility needs of specific software prod- ucts, their major drawback is their runtime performance. Compiling the source program to an abstract machine's intermediate language is the current technique used to obtain the best performance results. This intermediate code is then executed by a virtual machine developed as an interpreter. Although JIT adaptive optimizing com- pilation is currently used to speed up Java and .net intermediate code execution, this practice has not been em- ployed successfully in the implementation of dynamically adaptive platforms yet. We present an approach to improve the runtime performance of a specific set of structural reflective primitives, extensively used in adaptive software development. Looking for a better performance, as well as interaction with other languages, we have employed the Microsoft Shared Source CLI platform, making use of its JIT compiler. The SSCLI computational model has been enhanced with semantics of the prototype-based object-oriented com- putational model. This model is much more suitable for reflective environments. The initial assessment of per- formance results reveals that augmenting the semantics of the SSCLI model, together with JIT generation of native code, produces better runtime performance than the existing implementations.

### [**Static Analysis for Identifying and Allocating Clusters of Immortal Objects** (Ravindar & Srikant, 2005)](https://www.researchgate.net/publication/252238722_Static_Analysis_for_Identifying_and_Allocating_Clusters_of_Immortal_Objects)

**Abstract**

Long living objects lengthen the trace time which is a critical phase of the garbage collection process. However, it is possible to recognize object clusters i.e. groups of long living objects having approximately the same lifetime and treat them separately to reduce the load on the garbage collector and hence improve overall performance. Segregating objects this way leaves the heap for objects with shorter lifetimes and now a typical collection can nd more garbage than before. In this paper, we describe a compile time analysis strategy to identify object clusters in programs. The result of the compile time analysis is the set of allocation sites that contribute towards allocating objects belonging to such clusters. All such allocation sites are replaced by a new allocation method that allocates objects into the cluster area rather than the heap. This study was carried out for a concurrent collector which we developed for Rotor, Microsoft's Shared Source Implementation of .NET. We analyze the performance of the program with combina- tions of the cluster and stack allocation optimizations. Our results show that the clustering optimization reduces the number of collections by 66.5% on average, even eliminating the need for collection in some programs. As a result, the total pause time reduces by 62.8% on average. Using both stack allocation and the cluster optimizations brings down the number of collections by 91.5% thereby improving the total pause time by 79.33%.

### [**An Optimizing Just-InTime Compiler for Rotor** (Trindade & Silva, 2005)](https://www.semanticscholar.org/paper/An-Optimizing-Just-InTime-Compiler-for-Rotor-Trindade-Silva/6ef2de17e42fa2ad74799211d87ceaa6edc6e8bb)

**Abstract**

The Shared Source CLI (SSCLI), also known as Rotor, is an implementation of the CLI released by Microsoft in source code. Rotor includes a single pass just-in-time compiler that generates non-optimized code for Intel IA-32 and IBM PowerPC processors. We extend Rotor with an optimizing justin-time compiler for IA-32. This compiler has three passes: control flow graph generation, data dependence graph generation and final code generation. Dominance relations in the control flow graph are used to detect natural loops. A number of optimizations are performed during the generation of the data dependence graph. During native code generation, the rich address modes of IA32 are used for instruction folding, reducing code size and usage of register names. Despite the overhead of three passes and optimizations, this compiler is only 1.4 to 1.9 times slower than the original SSCLI compiler and generates code that runs 6.4 to 10 times faster.

### [**Software Interactions into the SSCLI platform** (Charfi & Emsellem, 2004)](https://www.semanticscholar.org/paper/SOFTWARE-INTERACTIONS-INTO-THE-SSCLI-PLATFORM-Charfi-Emsellem/b51d387d9ed8fb73d6f2449469a8276d40293fb2)

**Abstract**

By using an Interaction Specification Language (ISL), interactions between components can be expressed in a language independent way. At class level, interaction pattern specified in ISLrepresent model s of future interactions when applied on some component instances. The Interaction Server is in charge of managing the life cycle of interactions (interaction pattern registration and instantiation, destruction of interactions, merging). It acts as a central repository that keeps the global coherency of the adaptations realized on the component instances.The Interaction service allows creati ng interactions between heterogeneous components. Noah is an implementation of this Interaction Service. It can be thought as a dynamic aspect repository with a weaver that uses an aspect composition mechanism that insures commutable and associative adaptations. In this paper, we propose the implementation of the Interaction Service in the SSCLI. In contrast to other implementations such as Java where interaction management represents an additional layer, SSCLI enables us to integrate Interaction Management as in intrinsic part of the CLI runtime.

### [**Experience Integrating a New Compiler and a New Garbage Collector Into Rotor** (Anderson, Eng, Glew, Lewis, Menon & Stichnoth, 2004)](https://www.semanticscholar.org/paper/Experience-Integrating-a-New-Compiler-and-a-New-Anderson-Eng/55f0fd31010e8b7a3d92cbb4ab012db75deff1aa)

**Abstract**

Microsoft’s Rotor is a shared-source CLI implementation intended for use as a research platform. It is particularly attractive for research because of its complete implementation and extensive libraries, and because its modular design allows dierent implementations of certain components such as just-in-time compilers (JITs). Our group has independently developed our own high-performance JIT and garbage collector (GC) and wanted to take advantage of Rotor to experiment with these components in a CLI environment. In this paper, we describe our experience integrating these components into Rotor and evaluate the flexibility of Rotor’s design toward this goal. We found it easier to integrate our JIT than our GC because Rotor has a well-defined interface for the former but not the latter. However, our JIT integration still required significant changes to both Rotor and our JIT. For example, we modified Rotor to support multiple JITs. We also added support for a second JIT manager in Rotor, and implemented a new code manager compatible with our JIT. We had to change our JIT compiler to support Rotor’s calling conventions, helper functions, and exception model. Our GC integration was complicated by the many places in Rotor where components make assumptions about how its garbage collector is implemented, as well as Rotor’s lack of a well-defined GC interface. We also had to reconcile the dierent assumptions made by Rotor and our garbage collector about the layout of objects, virtual-method tables, and thread structures.
