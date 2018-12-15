# Minimum-Falling-Path-Sum

The minimum sum of any particular path will be the number you are looking at + the minimum of
the three(or two) possible paths on the row below that.  
Using this idea we can start at the bottom row of the square array and work our way up while using the original array to store the answers. 

The minimum path to every element in **only** the bottom row is itself.
We can then move up the 2d array and replace each element with the current element + the minimum of 
the available paths in the array below. We keep doing this until we're at the top row then the minimum number at the top row 
is the solution.

For example, if we have the array `A = [[1,2,3], [4,5,6], [7,8,9]]`, the bottom row `[7,8,9]` stays the same.
Then we move up one row to `[4,5,6]` and replace that with `[4 + min(7,8), 5 + min(7,8,9), 6 + min(8,9)]` which is `[11,12,14]`.
Now `A = [[1,2,3], [11,12,14], [7,8,9]]`. We do the same with the next row up to get `A = [[12,13,15], [11,12,14], [7,8,9]]` which leads to our answer `min(A[0]) = 12`.
