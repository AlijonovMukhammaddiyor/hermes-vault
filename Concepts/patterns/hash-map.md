# Hash Map / Set Pattern

**When to use:** Need to detect duplicates, count frequencies, or find complements/pairs in O(n).

**Why it applies:** Hash tables provide O(1) average-case lookups, turning nested-loop O(n²) checks into O(n) single-pass scans.

**The invariant/trick:** Map elements → their frequency or first-seen index. When the operation is symmetric (anagram check) use a single counter dict + inc/dec. When order doesn't matter (duplicate check) use a set.
