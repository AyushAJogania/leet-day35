# leet-day35

## Folder Name Generator

Given an array of strings representing folder names, this algorithm generates unique folder names by appending suffixes to ensure uniqueness.

### Problem Statement

You are given an array of strings `names` representing the names of folders that need to be created. Each folder name should be unique. If a folder name already exists, a numeric suffix `(k)` should be appended to the name, where `k` is the smallest positive integer that makes the folder name unique.

### Approach

The algorithm utilizes a hash map to keep track of the count of each folder name. It iterates through the `names` array and for each name, it follows these steps:

1. Check if the name already exists in the hash map.
2. If it does, append the smallest numeric suffix `(k)` to the name to ensure uniqueness.
3. Update the hash map with the new count of the modified name.
4. Add the modified name to the result vector.

### Pseudocode

```plaintext
function getFolderNames(names):
    nameCount = {}  # Hash map to store counts of each name
    result = []      # Vector to store the final unique folder names
    
    for name in names:
        newName = name
        while newName exists in nameCount:
            newName = name + "(" + nameCount[name] + ")"
            increment nameCount[name]
        nameCount[newName] = 1
        add newName to result
    
    return result
```

### Complexity Analysis

- Time Complexity: O(n * k), where n is the number of folder names and k is the average length of a name.
- Space Complexity: O(n), where n is the number of folder names, as the hash map `nameCount` is used to store the counts.

### Example

```cpp
names = ["gta", "gta(1)", "gta", "avalon"]
Output: ["gta", "gta(1)", "gta(2)", "avalon"]
```

In this example, the algorithm successfully generates unique folder names by appending numeric suffixes where needed.

### Conclusion

The algorithm provides an efficient solution to the problem of generating unique folder names from an array of strings, ensuring that the resulting folder names are both meaningful and follow the specified rules for uniqueness.
