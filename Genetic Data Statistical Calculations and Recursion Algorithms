#calculating d_hat

m =1614 # number of SNPs tested in this particular case

data = readLines("test1.txt")
data = strsplit(data, split=" ")
data = matrix(as.numeric(unlist(data)), nrow=m, byrow=T)
d_hat = sum((data[,1] - data[,2])*(data[,3])) / m


#revised forward propagation for Hidden Markov Chain
N = 10 #length of the Markov chain (number of t positions)
K = 3 # of possible values for Z at given t
#define random discrete uniform distribution func
rdu<-function(n,k) sample(1:k,n,replace=T)
#initialize the first value for z at position 1
z = vector()
z[1] = rdu(1,K)

for (t in 2:10){
#initialize random uniform distribution
p = runif(1,0,1)
#randomly generate from Bernoulli distribution
r = rbinom(1,1,p)

#conditional switch statements
if (r == 0){
  z[t] = z[t-1]}
else if (r == 1){
  z[t] = rdu(1,K)}}
