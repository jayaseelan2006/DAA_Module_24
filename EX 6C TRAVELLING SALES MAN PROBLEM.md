# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE:
## AIM:
To Solve Travelling Sales man Problem for the following graph.



## Algorithm
1. Find all ways to visit every city once.
2. Start from a given city.
3. Calculate total distance for each route.
4. Remember the shortest route found.
5. Return the shortest distance.
## Program:
```
/*
To implement the program for TSP.


Developed by: JAYASEELAN U
Register Number:  212223220039
*/
```
```
from sys import maxsize
from itertools import permutations
V = 4
 

def travellingSalesmanProblem(graph, s):
    ver=[]
    for i in range(V):
        if i!=s:
            ver.append(i)
    minpath=maxsize
    nextper=permutations(ver)
    for i in nextper:
        cost=0
        r=s
        for c in i:
            cost+=graph[r][c]
            r=c
        cost+=graph[r][s]
        minpath=min(minpath,cost)
    return minpath
if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```
## Output:
![image](https://github.com/user-attachments/assets/684968cf-eac7-4081-8135-2346116e4e7a)
## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
