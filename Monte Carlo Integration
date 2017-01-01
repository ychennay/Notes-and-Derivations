a= 0
b= 1
f.min= -6
f.max= 1

hit_miss <- function(func, a,b,f.min, f.max,n){
  Z.sum <- 0 # sum of area under the curve, initialized at 0
  
  for (i in 1:n){
  X <- runif(1,a,b) #uniform between a and b
  Y <- runif(1,f.min, f.max) # uniform between f.min and f.max
  Z <- (func(X) >= Y) # if true, Y falls under the area of the curve
  Z.sum <- Z.sum + Z
  }
  I <- (b-a)*f.min + (Z.sum/n) * (b-a) * (f.max-f.min)
  return(I)
}

f <- function(x) x^3 - 7*x^2+1

hit_miss(f, 0,1,-6,1,10)
hit_miss(f, 0,1,-6,1,100)
hit_miss(f, 0,1,-6,1,1000)
hit_miss(f, 0,1,-6,1,1000000)
