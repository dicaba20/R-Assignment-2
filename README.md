# R-Assignment-2
Matrix &lt;- function(x = matrix()) {   inv &lt;- NULL   set &lt;- function(y) {     x &lt;&lt;- y     inv &lt;&lt;- NULL   }   get &lt;- function() x   setinverse &lt;- function(inverse) inv &lt;&lt;- inverse   getinverse &lt;- function() inv   list(set=set, get=get, setinverse=setinverse, getinverse=getinverse) } cacheSolve &lt;- function(x, ...) {   inv &lt;- x$getinverse()   if(!is.null(inv)) {     message("getting cached data.")     return(inv)   }   data &lt;- x$get()   inv &lt;- solve(data)   x$setinverse(inv)   inv } x = rbind(c(4, -8), c(-8, 4)) m = makeCacheMatrix(x) m$get() cacheSolve(m)
