---
title: Swap in C and python
layout: minimal
parent: Daily Code
---

## How parameters and arguments differ  

<p>For simply understanding how C distinguishes between <em>parameters</em> and <em>arguments</em>,
I wrote a small python script for implementing the same one using in C,
since so many big words from C programming universe are really confusing to me.</p>

An original example shown by [Effective C](https://github.com/rcseacord/effective-c):
```c  
#include <stdio.h>
#include <stdlib.h>
void swap(int a, int b) { // swap function: swapping two integers values
	int t = a; // t is a temporary variable 
	a = b;
	b = t;
	printf("swap: a = %d, b = %d\n", a, b); 
}
int main() {
	int a = 21;
	int b = 17;
	swap(a, b); // swap called, a = 17, b = 21
	printf("main: a = %d, b = %d\n", a, b); // inside main, a = 21, b = 17
	return EXIT_SUCCESS;
}
```  

<p>I found myself really struggling to understand the changes, and the things that didn't change in this snippet example. As a novice learning C, I even felt like I was wasting my life reading so many explanations. So, I decided to think this one in a Pythonic way.</p>

```py
# same swap function
def swap(x, y):
    tmp = x # also, tmp is a temporary variable for safely keeping `x` value
    x = y
    y = tmp
    print(f"Inside swap: x = {x}, y = {y}\n") 

if __name__ == '__main__':
  x = 21
  y = 17
  swap(x,y) # swap called, x = 17, y = 21
  print(f"Inside main: x = {x}, y = {y}\n") # inside main part, x = 21, y = 17
```  

<p>Now, things are going better. The key poing is to first figure out that a program and a function are not the same thing.</p>


