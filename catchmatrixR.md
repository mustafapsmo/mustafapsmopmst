## This module creates two function.
## 1. makeCacheMatrix
## 2. cacheSolve

## This function creates a special matrix called cached matrix, which is
## really a list containing a function to

## 1.  set the the matrix
## 2.  get the the matrix
## 3.  set the inverse of the matrix
## 4.  get the inverse of the matrix

makeCacheMatrix <- function(x = matrix()) {
    
    inv <<- NULL
    
    set <- function(m) {
        x <<- m
        inv <<- NULL
    }
    
    get <- function() {
        x
    }
    
    setinv <- function(invmatrix) {
        inv <<- invmatrix
    }
    
    getinv <- function() {
        inv
    }
    
    list(set = set, get = get, setinv = setinv, getinv = getinv)
}


## This function creates the inverse of cached matrix
## If the inverse matrix is existing, get the cached inverse
## otherwise calculate the invere of cached matrix

##Example
mat1 <- matrix(c(4,3,3,2),2,2)
mat2 <- makeCacheMatrix(mat1)
mat3 <- cacheSolve(mat2)
print(mat3)
mat3 <- cacheSolve(mat2)
print(mat3)
