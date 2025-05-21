# EX 6B KNAPSACK PROBLEM
## DATE:
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. You have items with weights and values and a knapsack with capacity W.
2. Use a table to store max value for each item and capacity.
3. For each item, either include it if it fits or skip it.
4. If no items or zero capacity, max value is zero.
5. The answer is the max value for all items and full capacity.
## Program:
```
/*
To implement the program for 0/1 knapsack problem.


Developed by: JAYASEELAN U
Register Number:  212223220039
*/
```
```
def knapSack(W, wt, val, n):
    dp=[[0 for j in range(W+1)]for i in range(n+1)]
    for i in range(n+1):
        for j in range(W+1):
            if i==0 or j==0:
                dp[i][j]=0
            if wt[i-1]>j:
                dp[i][j]=dp[i-1][j]
            else:
                dp[i][j]=max(val[i-1]+dp[i-1][j-wt[i-1]],dp[i-1][j])
    return dp[n][W]
x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```
## Output:
![image](https://github.com/user-attachments/assets/203e8304-306b-4a92-aba1-12c5a565a4d3)
## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
