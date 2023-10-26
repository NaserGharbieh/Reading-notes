# Hashtables

### I have seen this sourse that talks about [Hashtables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html) and I want to write about it

# What I Learned About Hashtables

## WHY
- Hashtables are used in data structures because they offer efficient data retrieval based on keys. They are vital for quick lookups, which is essential in many applications, from implementing dictionaries to optimizing library or database operations.

## WHAT
- Hashtables are a data structure that stores data as key-value pairs. Each key is hashed to determine the index in the array where the corresponding value is stored. This design allows for O(1) time complexity for lookups, making it an ideal choice when fast data retrieval is a priority.

## HOW
- Hashtables work by applying a hash function to a key, which produces a numeric representation. This numeric value is then used to calculate the index in the array where the key-value pair should be placed. In cases of collisions (where multiple keys produce the same hash), Hashtables employ linked lists within buckets to store multiple key-value pairs in the same index.

## Quiz
1. **Why are Hashtables commonly used in data structures?**
   - A. To make data storage more space-efficient.
   - B. To ensure all keys have the same index.
   - C. For efficient data retrieval based on keys.
   - D. To minimize the need for keys.

2. **What is the primary purpose of a hash code in Hashtables?**
   - A. To generate random numbers for key-value pairs.
   - B. To provide a numerical representation of a key.
   - C. To sort the keys alphabetically.
   - D. To determine the array size.

3. **How do Hashtables handle collisions when multiple keys hash to the same index?**
   - A. They discard the extra keys.
   - B. They overwrite the previous key-value pair.
   - C. They create linked lists within the same bucket.
   - D. They change the key to avoid collisions.

4. **What is the time complexity for lookups in a Hashtable with a properly implemented hash function?**
   - A. O(log n)
   - B. O(n)
   - C. O(1)
   - D. O(n log n)

**Answers:**
1. C
2. B
3. C
4. C
