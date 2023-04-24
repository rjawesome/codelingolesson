# Recursion


## What is Recursion?
The term recursion refers to the fact that the same computation recurs, or occurs repeatedly, as the problem is solved.

This method is a powerful technique for breaking up complex problems into simpler ones.

Many simple recursions can be computed as loops. However, loop equivalents for more complex recursions can be complex.

Recursive Computation:
- solves a problem by using the solution to the same problem with simpler inputs
- call pattern of a recursive method looks complicated, and the key to the successful design of a recursive method is not to think about it.

Just as loops can run into the problem of infinite looping, recursive functions can run into the problem of infinite recursion. Infinite recursion is when the function never stops calling itself. Every recursive function should have a halting condition, which is the condition where the function stops calling itself.

```
int sum = 0;
public void recursionex(int n) {
    sum += n;
    System.out.println(sum);
    if (n>15) {
        System.out.println("stop");
    }
    else {
        recursionex(n+1);
    }
  
}
recursionex(10);
```

```
10
21
33
46
60
75
91
stop
```


## What do I need to watch out for?
In infinite recursions, after a number of calls, all memory available for purpose is exhausted. Your computer shuts down and returns a “stack overflow”. 

This happens either when the arguments don’t get simpler or a special terminating case is missing.

```
//don't run lol
int sum = 0;
public void infiniteex(int n) {
    sum += n;
    System.out.println(sum);
    if (n>15) {
        System.out.println("stop");
    }
    infiniteex(n+1);
  
}
// infiniteex(10);
```


## Tracing through Recursive Methods
When you set a breakpoint in a recursive method, that project line is encountered in any call to the recursive method.

Watch the call stack to understand which nested call you are currently in.


## Recursion Hack:
Save this code from infinite recursion. The code should print something like this:

```
**********
*********
********
*******
******
*****
****
***
**
*
```

```
public void drawLine(int n) {
    for (int i = 1; i <= n; i++) {
        System.out.print("*");
        System.out.println();
        drawLine(n - 1);
    }
}
drawLine(10);
```