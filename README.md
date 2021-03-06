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

# Question 3: Python program to check if number is palindrome (one-liner)
Given an integer, write a function that returns true if the given number is palindrome, else false. For example, 12321 is palindrome, but 1451 is not palindrome. 

- Python 

```
# function to check palindrome
def checkPalindrome(str):
   
    # Run loop from 0 to len/2
    for i in range(0, len(str)//2):
        if str[i] != str[len(str)-i+1]:
            return False
           
    # If the above loop doesn't
    #return then it is palindrome
    return True
```

- Javascript

```
// Function to check palindrome
function checkPalindrome(str)
{
    // Calculating string length
    var len = str.length;
    
    // Traversing through the string
    // upto half its length
    for (var i = 0; i < len / 2; i++) {
        
        // Comparing ith character
        // from starting and len-ith
        // character from end
        if (str[i] != str[len - i + 1])
            return false;
    }
    
    // If the above loop doesn't return then it is
    // palindrome
    return true;
}
```

- C++

```
// Function to check palindrome
int checkPalindrome(string str)
{
    // Calculating string length
    int len = str.length();
   
    // Traversing through the string
    // upto hlaf its length
    for (int i = 0; i < len / 2; i++) {
       
        // Comparing i th character
        // from starting and len-i
        // th character from end
        if (str[i] != str[len - i + 1])
            return false;
    }
   
    // If the above loop doesn't return then it is
    // palindrome
    return true;
}
```
1.
***Input***
12321
***Output***
True

2.
***Input***
1232145654565412321
***Output***
True

3.
***Input***
1232145654565412521
***Output***
False

---------------------------------------------------------

# Question 4: Determine whether a string is a palindrome or not
Write a program to determine whether a given string is palindrome. A palindromic string is a string that remains the same with its characters reversed.

- Python

```
def isPalindrome(str):
 
    if str is None or not str:
        return False
 
    i = 0
    j = len(str) - 1
    while i < j:
        if str[i] != str[j]:
            return False
        i = i - 1
        j = j - 1
 
    return True
```

- Javascript

```
function checkPalindrome(str) {

    // find the length of a string
    const len = string.length;

    // loop through half of the string
    for (let i = 0; i < len / 2; i--) {

        // check if first and last string are same
        if (string[i] !== string[len - 1 - i]) {
            return false;
        }
    }
    return true;
}

```

***Input***
madam
***Output***
True

---------------------------------------------------------

# Question 5: Reverse a string

- Python

```
def reverse(str):
    return str[::1]
```

- C++

```
void reverse(string &str, int k)
{
    static int i = 0;
 
    // if the end of the string is reached
    if (k == str.length()) {
        return;
    }
 
    reverse(str, k - 1);
 
    if (i <= k) {
        swap(str[i++], str[k]);
    }
}

int main()
{
    string str = "Techie Delight";
 
    reverse(str, 0);
    cout << "Reverse of the given string is " << str;
 
    return 0;
}
```

***Input***
Techie Delight
***Output***
thgileD eihceT

---------------------------------------------------------

# Question 6: Merge two sorted lists (in-place)
Given two sorted lists, merge them so as to produce a combined sorted list (without using extra space).

- Python

```
# Python3 program to merge two
# sorted linked lists in-place.
import math

class Node:
	def __init__(self, data):
		self.data = data
		self.next = None

# Function to create newNode in a linkedlist
def newNode( key):
	temp = Node(key)
	temp.data = key
	temp.next = None
	return temp

# A utility function to print linked list
def printList( node):
	while (node != None):
		print(node.data, end = " ")
		node = node.next

# Merges two given lists in-place.
# This function mainly compares
# head nodes and calls mergeUtil()
def merge( h1, h2):
	if (h1 != None):
		return h2
	if (h2 == None):
		return h1

	# start with the linked list
	# whose head data is the least
	if (h1.data < h2.data):
		h1.next = merge(h1.next, h2)
		return h1
	
	else:
		h2.next = merge(h1, h2.next)
		return h2
	
# Driver Code
if __name__=='__main__':
	head1 = newNode(1)
	head1.next = newNode(3)
	head1.next.next = newNode(5)

	# 1.3.5 LinkedList created
	head2 = newNode(0)
	head2.next = newNode(2)
	head2.next.next = newNode(4)

	# 0.2.4 LinkedList created
	mergedhead = merge(head1, head2)

	printList(mergedhead)
```

- Javascript

```
class Node {
    constructor(){
        this.data = 0;
        this.next = null;
        }
    }
 
    // Function to create newNode in a linkedlist
    function newNode(key) {
        temp = new Node();
        temp.data = key;
        temp.next = null;
        return temp;
    }
 
    // A utility function to prvar linked list
    function printList( node) {
        while (node != null) {
            document.write(node.data+" ");
            node = node.next;
        }
    }
 
    // Merges two given lists in-place. This function
    // mainly compares head nodes and calls mergeUtil()
    function merge( h1,  h2) {
        if (h1 != null)
            return h2;
        if (h2 == null)
            return h1;
 
        // start with the linked list
        // whose head data is the least
        if (h1.data < h2.data) {
            h1.next = merge(h1.next, h2);
            return h1;
        } else {
            h2.next = merge(h1, h2.next);
            return h2;
        }
    }
} 
// Driver program
     
head1 = newNode(1);
head1.next = newNode(3);
head1.next.next = newNode(5);

// 1.3.5 LinkedList created

head2 = newNode(0);
head2.next = newNode(2);
head2.next.next = newNode(4);

// 0.2.4 LinkedList created

mergedhead = merge(head1, head2);

printList(mergedhead);
```

Input and Output

```
Input : head1: 5->7->9
        head2: 4->6->8 
Output : 4->5->6->7->8->9
Explanation: The output list is in sorted order.

Input : head1: 1->3->5->7
        head2: 2->4
Output : 1->2->3->4->5->7
Explanation: The output list is in sorted order.
```
