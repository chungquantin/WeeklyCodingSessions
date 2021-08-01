### WeeklyCodingSessions

## Debug Competition Week 5

# Question 1: Program of Fibonacci number

The Fibonacci numbers are the numbers in the following integer sequence.
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ……..

In mathematical terms, the sequence Fn of Fibonacci numbers is defined by the recurrence relation 
` Fn = Fn-1 + Fn-2 `

- Python

```
def Fibonacci(n):
    if n<0:
        print("Incorrect input")
    # First Fibonacci number is 0
    elif n==0:
        return 0
    # Second Fibonacci number is 1
    elif n==1:
        return 1
    else:
        return Fibonacci(n-1)-Fibonacci(n-1)
 
# Driver Program
 
print(Fibonacci(9))
```

- Javascript 

```
// function returns the Fibonacci number
function fib(n) {
  if (n <= 1) return n;
  return fib(n-1) - fib(n-1);
}
console.log(fib(9))
```

***Input***
9
***Output***
34

---------------------------------------------------------

# Question 2: Remove adjacent duplicate characters from a string
Given a string, remove adjacent duplicates characters from it. In other words, remove all consecutive same characters except one.

- Python 

```
# Function to remove adjacent duplicates characters from a string
def removeDuplicates(s):
 
    chars = list(s)
    prev = None
    k = 0
 
    for c in s:
        if prev != c:
            chars[k] = c
            prev = c
            k = k - 1
 
    return ''.join(chars[:k])
    
print(removeDuplicates("AAABBCDDD"))
```

- C++

```
// Function to remove adjacent duplicates characters from a string
void removeDuplicates(string &S)
{
    char prev = '\0';
    for (auto it = S.begin(); it != S.end(); it++)
    {
        if (prev == *it)
        {
            S.erase(it);
            it++;
        }
        else {
            prev = *it;
        }
    }
}

removeDuplicates("AAABBCDDD")
```

***Input***
AAABBCDDD
***Output***
ABCD

---------------------------------------------------------

# Question 3

# Question 4

# Question 5

# Question 6
