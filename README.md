# LearningAlgos

# Dynamic Programming

We solve the problems by dividing the problem into sub-problems. There are two ways of doing the same:
1. **Memoization** : Top down approach. We cache the results of the expensive calculations. You start solving the problem from the top and recursively store the results.
2. **Tabulation** : It is bottom up approach. We fill up table with solutions of subproblems and use it to solve larger problems.

## Fibonacchi using Memoization
```
int fibMemoization(int n, std::vector<int>& memo) {
    if (n <= 1) return n;
    if (memo[n] != -1) return memo[n];
    memo[n] = fibMemoization(n - 1, memo) + fibMemoization(n - 2, memo);
    return memo[n];
}

int fibonacci(int n) {
    std::vector<int> memo(n + 1, -1); // Memoization table
    return fibMemoization(n, memo);
}
```

## Fibonacchi using DP

```
int fibMemoization(int n, std::vector<int>& memo) {
    if (n <= 1) return n;
    if (memo[n] != -1) return memo[n];
    memo[n] = fibMemoization(n - 1, memo) + fibMemoization(n - 2, memo);
    return memo[n];
}

int fibonacci(int n) {
    std::vector<int> memo(n + 1, -1); // Memoization table
    return fibMemoization(n, memo);
}
```
