## Introduction

Peer-graded Assignment: Programming Assignment 2: Lexical Scoping

Assignment: Caching the Inverse of a Matrix

makeCacheMatrix: This function creates a special "matrix" object that can cache its inverse.

cacheSolve: This function computes the inverse of the special "matrix" returned by makeCacheMatrix above. If the inverse has already been calculated (and the matrix has not changed), then cacheSolve should retrieve the inverse from the cache.

## Test of the functions : makeCacheMatrix()and cacheSolve 
### Test sequence (copy past to the console)
  A<-matrix(data = 1:4, nrow = 2, ncol = 2)
  B<-matrix(c(1,1,2,2,3,4,5,7,8), nrow = 3, ncol = 3)
  solve(A)
  solve(B)
  my_matrix <- makeCacheMatrix(A)
  my_matrix$get()
  my_matrix$getinv()
  cacheSolve(my_matrix)
  my_matrix$getinv()
  my_matrix$set(B)
  cacheSolve(my_matrix)
  my_matrix$getinv()
### end of test sequence
  
### test sequence with expected results
  > A<-matrix(data = 1:4, nrow = 2, ncol = 2)
  > B<-matrix(c(1,1,2,2,3,4,5,7,8), nrow = 3, ncol = 3)
  > solve(A)
  [,1] [,2]
  [1,]   -2  1.5
  [2,]    1 -0.5
  > solve(B)
  [,1] [,2] [,3]
  [1,]    2   -2  0.5
  [2,]   -3    1  1.0
  [3,]    1    0 -0.5
  > my_matrix <- makeCacheMatrix(A)
  > my_matrix$get()
  [,1] [,2]
  [1,]    1    3
  [2,]    2    4
  > my_matrix$getinv()
  NULL
  > cacheSolve(my_matrix)
  [,1] [,2]
  [1,]   -2  1.5
  [2,]    1 -0.5
  > my_matrix$getinv()
  [,1] [,2]
  [1,]   -2  1.5
  [2,]    1 -0.5
  > my_matrix$set(B)
  > cacheSolve(my_matrix)
  [,1] [,2] [,3]
  [1,]    2   -2  0.5
  [2,]   -3    1  1.0
  [3,]    1    0 -0.5
  > my_matrix$getinv()
  [,1] [,2] [,3]
  [1,]    2   -2  0.5
  [2,]   -3    1  1.0
  [3,]    1    0 -0.5
  >
# end of test sequence
