# Class 18 reading:
# Purely Functional Programming

In purely functional programming, data structures are typically treated as immutable, meaning once they are created, they cannot be changed. Instead of modifying an existing data structure, you create new data structures that incorporate the desired changes while leaving the original data structures unchanged. This immutability is a fundamental principle of purely functional programming and is key to ensuring referential transparency and avoiding side effects.

## What Is Purely Functional Programming?

**Purely functional programming** is a programming paradigm where all computation is treated as the evaluation of mathematical functions. In this paradigm, functions are pure, meaning they depend only on their arguments and have no side effects. Purely functional programs avoid mutable state and use immutable data structures. This approach aims to make programs more predictable, easier to reason about, and less prone to bugs related to mutable state.

## How It Differs From Imperative Programming

Purely functional programming differs significantly from imperative programming, which is likely the style of programming you've encountered in most of your courses. Imperative programs often involve changing the state of variables, using loops, and performing actions with side effects. In contrast, purely functional programs aim to minimize or eliminate side effects and mutable state. This change in mindset and approach may require a different way of thinking and structuring your programs.

Here are some key differences you might encounter when transitioning to purely functional programming:

1. **Immutability:** In purely functional programming, you'll work with immutable data structures, which means you create new data structures with each modification instead of changing existing ones.

2. **Pure Functions:** Functions are expected to be pure, meaning they don't have side effects and depend only on their input parameters. This can lead to a different approach to writing functions.

3. **Recursion:** Functional programming often relies on recursion rather than loops for iteration, which can be a significant shift in how you structure your code.

4. **State Management:** Rather than changing the state of variables, you'll create new versions of data structures with each update, making it easier to reason about program behavior.

5. **Concurrency:** Functional programming can simplify concurrent and parallel programming by avoiding shared mutable state.

6. **Higher-Order Functions:** Functional programming languages often have robust support for higher-order functions, allowing you to pass functions as arguments and return functions from other functions.

Overall, purely functional programming encourages a different style of coding that focuses on expressing computations as a series of transformations on data, without changing the data in place. While it can be a significant departure from imperative programming, it offers benefits in terms of code correctness, maintainability, and scalability.

