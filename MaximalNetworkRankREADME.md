# leet-day35

# Maximal Network Rank

This is a solution to the "Maximal Network Rank" problem on LeetCode. Given an infrastructure of cities and roads connecting them, the goal is to find the maximal network rank of the entire infrastructure.

## Problem Statement

You are given an infrastructure of n cities with some number of roads connecting these cities. Each `roads[i] = [ai, bi]` indicates that there is a bidirectional road between cities `ai` and `bi`. The network rank of two different cities is defined as the total number of directly connected roads to either city. If a road is directly connected to both cities, it is only counted once. The maximal network rank of the infrastructure is the maximum network rank of all pairs of different cities.

## Example

### Input
```
n = 4
roads = [[0,1],[0,3],[1,2],[1,3]]
```

### Output
```
4
```

Explanation: The network rank of cities 0 and 1 is 4 as there are 4 roads that are connected to either 0 or 1. The road between 0 and 1 is only counted once.

## Approach

1. Create a `degrees` vector to keep track of the degree of each city. Initialize it with zeros.
2. Create a `connected` matrix to check if there's a road connecting two cities. Initialize it with `false`.
3. Loop through the given roads and update the `degrees` vector and `connected` matrix accordingly.
4. Iterate through all pairs of different cities and calculate the network rank based on the sum of their degrees. If there's a road connecting the two cities, subtract 1 from the network rank.
5. Keep track of the maximum network rank encountered and return it at the end.

## Complexity Analysis

- Time complexity: O(n^2) where n is the number of cities. This is because we iterate through all pairs of cities.
- Space complexity: O(n^2) where n is the number of cities. This is because of the `connected` matrix that tracks the roads between cities.

## Usage

1. Clone the repository or create a new C++ source code file.
2. Copy and paste the provided solution into your source code.
3. Modify the `n` and `roads` variables with the input values.
4. Compile and run the code.
5. The output will be the maximal network rank of the given infrastructure.

## Conclusion

This solution effectively calculates the maximal network rank of the given infrastructure by considering the degrees of each city and the roads connecting them. It uses dynamic programming techniques to efficiently solve the problem and provide the expected output.
