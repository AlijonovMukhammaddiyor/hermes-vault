# Arrays & Hashing — Mental Model

## The Hash Map Superpower

Most array problems become trivial once you ask: **"What lookup do I need to make constant-time?"**

### Core insight (NeetCode)
A hash map (dict/set in Python) trades O(n) memory for O(1) lookups — and that trade wins almost every time you need to remember *what you've seen before*.

### Three patterns that cover 90% of arrays-hashing problems

1. **"Seen before" check** — iterate once, store each element in a set. If you encounter it again → duplicate found. O(n) time, O(n) space. (Contains Duplicate)

2. **Character frequency counter** — count characters in one string into a dict, decrement for the other. If all counts are zero → anagram. O(n) time, O(1) space (fixed alphabet). (Valid Anagram)

3. **Complement lookup** — for each element x, check if (target - x) exists in a hash set. If so, you've found your pair. O(n) time, O(n) space. (Two Sum)

### Why this works (MIT 6.006 insight)
Hash tables give us the *dictionary ADT* — insert, delete, lookup in expected O(1). This transforms "is this element already in the collection?" from an O(n²) nested-loop scan into a single pass.

### The default that bites beginners
**The naive approach** to "contains duplicate" is a double loop — O(n²). The hash set cuts it to O(n). Always ask: *Does this problem need a lookup structure?* If yes, you probably want a hash set or hash map.

### References
- NeetCode, *Arrays & Hashing* playlist: https://neetcode.io/courses/dsa-for-beginners/3
- MIT 6.006, *Hash Tables*: https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/
