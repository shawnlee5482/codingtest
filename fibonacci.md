## Fibonacci
## test123456
log2 ^ n is the optimum  (by using matrix multiplication)

function fib(n)
{
  if(n < 3) return n-1;
  let [a, b] = [1, 2]; 
  while(n--) {
    [a, b] = [b, a+b];
  }
  return a;
}

https://leetcode.com/articles/climbing-stairs/

