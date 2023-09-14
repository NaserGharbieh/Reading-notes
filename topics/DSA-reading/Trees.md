# Trees and Tree Traversals

### I have seen this sourse that talks about [Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html) and I want to write about it

## Terminology in Trees

**Analogy:** Think of a tree as a family tree. In a family tree, you have various members, with relationships connecting them. Now, let's break down some essential tree terminology using this analogy.

1. **Node**: In our family tree, each person is like a node. They have their unique identity, like a name or ID.

2. **Root**: The root of the family tree is like the oldest generation, usually the grandparents. They are at the top, representing the starting point.

3. **K**: Imagine K as a rule that grandparents set: each couple can have K children. In binary trees, K is 2, meaning two children per couple.

4. **Left and Right**: Just like in a family tree, where you might have siblings, a node's "left" and "right" are like your siblings. They are your immediate family members.

5. **Edge**: The lines or branches connecting each generation in a family tree are edges. They show who is related to whom.

6. **Leaf**: Think of leaves as the youngest generation in the family tree. They have no children of their own.

7. **Height**: The height of the family tree is like the number of generations from the grandparents to the youngest generation.

## Tree Traversals

**Analogy:** Imagine you are exploring a maze. The goal is to find a hidden treasure. Traversing the maze is similar to navigating a tree. Let's dive into tree traversals using this analogy.

**1. Depth First Traversal (DFS)**

- **Why:** You start walking down one path of the maze as far as you can before turning.

- **What:** DFS explores as deeply as possible along each branch before backtracking. It's like searching one path in the maze until you reach a dead-end.

- **How:** In a tree, you visit the root, then go as deep as possible to the left before returning and going to the right. This is like exploring one side of the maze before trying another.

**2. Breadth First Traversal (BFS)**

- **Why:** In the maze, you might prefer to explore one step at a time across all paths.

- **What:** BFS explores all the neighbors of a node before moving on to their children. It's like taking one step in every direction in the maze.

- **How:** In a tree, you visit the root, then its immediate neighbors before their children. It's similar to exploring each level of the maze before going deeper.

## Quiz

1. **What does a "node" represent in a tree?**

   - a) A generation in a family tree
   - b) A unique element in the tree
   - c) A root node

2. **In a binary tree, what does "K" stand for?**

   - a) The number of generations
   - b) The maximum number of children per node
   - c) The height of the tree

3. **What is the primary difference between Depth First and Breadth First tree traversals?**

   - a) Depth First goes deeper into a branch before exploring others; Breadth First explores neighbors before children.
   - b) Depth First explores neighbors before children; Breadth First goes deeper into a branch before exploring others.
   - c) They are essentially the same; the terms are interchangeable.

4. **In a tree traversal, what does "leaf" refer to?**

   - a) The starting point
   - b) A node with no children
   - c) The deepest node in the tree

5. **What is the Big O time complexity of a Binary Search Tree's search operation in the worst case?**

   - a) O(1)
   - b) O(log n)
   - c) O(n)

**Answers:** 1. b, 2. b, 3. a, 4. b, 5. c
