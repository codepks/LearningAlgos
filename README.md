# LearningAlgos

# Dynamic Programming

We solve the problems by dividing the problem into sub-problems. There are two ways of doing the same:
1. **Memoization** : Top down approach. We cache the results of the expensive calculations. You start solving the problem from the top and recursively store the results.
2. **Tabulation** : It is bottom up approach. We fill up table with solutions of subproblems and use it to solve larger problems.

## Fibonacchi Problem

### Fibonacchi using Memoization
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

### Fibonacchi using DP

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


## Knapsack 0/1

>Given N items where each item has some weight and profit associated with it and also given a bag with capacity W,
>(i.e., the bag can hold at most W weight in it).
>The task is to put the items into the bag such that the sum of profits associated with them is the maximum possible. 

```
max( val[n - 1] + knapSack(W - wt[n - 1], wt, val, n - 1), knapSack(W, wt, val, n - 1)); 
```

We need to understand the recursion method first.

**Explantion**

> For example : profit[] = {60, 100, 120}, weight[] = {10, 20, 30}, W = 50
> First you need to sort the weight array
> 1. Keep the value of the last element in the array = val[n-1]
> 2. Call the function with the remove element weight on the rest of the earlier array = knapSack(W - wt[n - 1], wt, val, n - 1)
> 3. Apply recursion on the array without the last element to see if you can still get better results without the last element
> 4. Check max of ( 1 + 2 ) and (3)

