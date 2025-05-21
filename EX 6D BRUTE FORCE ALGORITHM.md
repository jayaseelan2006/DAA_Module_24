# EX 6D BRUTE FORCE ALGORITHM
## DATE:
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.




## Algorithm
1. Take two strings: string (main text) and sub (pattern to find).
2. Loop through string to check every possible starting position.
3. For each position, compare characters with sub one by one.
4. If all characters match, print the starting index.
5. If no match, move to the next position until done.

## Program:
```
/*
To implement the program using brute force method of searching for the given substring in the main string.


Developed by: JAYASEELAN U
Register Number:  212223220039
*/
```
```
def match(string,sub):
    l = len(string)
    ls = len(sub)
    for i in range(l-ls+1):
        f=True
        for j in range(ls):
            if string[i+j]!=sub[j]:
                f=False
                break
        if f:
           print("Found at index",i) 
str1=input()
str2=input()
```
## Output:
![image](https://github.com/user-attachments/assets/e02c8a03-f908-41a8-a3bb-e5c76f1c9ad8)
## Result:
Thus the above program was executed successfully for searching the substring at respective index.
