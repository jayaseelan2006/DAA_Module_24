# EX 6A CHERRY PICK UP PROBLEM
## DATE:
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1. Two people move together from the top-left (0, 0) to the bottom-right (n-1, n-1), collecting cherries.
2. They can only move right or down, and cannot step on blocked cells (marked as -1).
3. The function keeps track of both positions and collects cherries (once if both are on the same cell).
4. Tries all possible moves for both people and uses memoization to avoid repeating work.
5. Returns the maximum number of cherries they can collect together.  
## Program:
```
/*
To implement the program for Cherry pickup problem.


Developed by: jayaseelan U
Register Number:  212223220039
*/
```
```
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        dp = [[-1] * (n + 1) for _ in range(n + 1)]
        memo = {}
        def f(r1, c1, r2, dp):
            c2 = r1 + c1 - r2 
            if (r1 < 0 or c1 < 0 or r2 < 0 or c2 < 0 or 
                r1 >= n or c1 >= n or r2 >= n or c2 >= n or 
                grid[r1][c1] == -1 or grid[r2][c2] == -1):
                return float('-inf')
            if r1 == n-1 and c1 == n-1:
                return grid[r1][c1]
            key = (r1, c1, r2)
            if key in memo:
                return memo[key]
            current = grid[r1][c1]
            if r1 != r2 or c1 != c2:
                current += grid[r2][c2]
            best = float('-inf')
            moves = [
                (r1+1, c1, r2+1),
                (r1+1, c1, r2), 
                (r1, c1+1, r2+1),
                (r1, c1+1, r2) 
            ]
            for move in moves:
                best = max(best, f(move[0], move[1], move[2], dp))
            if best != float('-inf'):
                current += best
            else:
                current = float('-inf')
            memo[key] = current
            return current
        return f(0,0,0,dp)
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output:
![image](https://github.com/user-attachments/assets/eb322841-5b22-4200-8d7d-c00babcd2798)
## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
