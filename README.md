# C-211
Programs written for my C++ Object-Oriented Program class

These are the assignments for the class:

____________________________________________________________________
Assignment 1 - Perfect Square:

Write a program to find and print the first perfect square (i*i) whose last two digits
are both odd.

__________________________________________________________________
Assignment 2 - Equivalent Arrays:

Consider the two arrays a and b.
a: 1 2 3 4 5
b: 3 4 5 1 2

It is possible to transform array a into array b by right shifting each element of a to the “right”
three places. If an element “falls off” the back of the array have it come around the front and
keep counting positions. That is how 3 in array ended up in the first position of array b. One
way to look at this is to imagine that we are moving the element around in a circular manner.
In the example above, we have right shifted the array 3 positions to the right.
Definition: Let a and b be two integer arrays of the same length. We say that they are “shift
equivalent” if array a can be right shifted to create array b.

Problem:
Write a function: bool equivalent(int a[], int b[], int n)
which takes two arrays a and b of length n and returns true is they are shift equivalent and false
otherwise

__________________________________________________________________
Assignment 3 - Queens 1D with Goto:

Solve the 8 queens problem using goto

__________________________________________________________________
Assignment 4 - Queens 1D without Goto:

Solve the 8 queens problem without using goto

__________________________________________________________________
Assignment 5 - 8 Queens Problem solved through brute force:

Solve the 8 queens problem using brute force 
__________________________________________________________________
Assignment 6 - 8 Cross:

In the solution to this problem, use the backtracking scheme that we covered in class.
Write a program which allocates the integers 1-8 to the squares in the figure above, subject to
the restrictions that no two adjacent squares contain consecutive integers.
By adjacent we mean vertically, horizontally, or diagonally.

__________________________________________________________________
Assignment 7 - Stable Marriage

The Problem:
You have n men and n woman, and their preference rankings of each other, and you need
to match them up so that the total matching is “stable.”

The preference rankings:
You are given 2 n X n arrays, mp (men’s preference) which gives the men’s ranking of the
women, and wp (women’s preference) which gives the women’s ranking of the men.
So mp[i][j] gives man i's ranking of woman j and likewise for the women’s ranking of the men in
wp.
For example in the following tables we have n=3 and the women and men are “named” 0, 1 or 2
and the raking are in the range 0 = highest, 1 second highest and 2 lowest.

int mp[3][3]={0,2,1,
0,2,1,
1,2,0};
int wp[3][3]={2,1,0,
0,1,2,
2,0,1};

So man 1 assigns woman 2 the rank of 1 (i.e. second highest) and prefers woman 0 the best.
What is a stable matching?
A matching is stable if there are no “instabilities.” Say the match assigns m1 to w1 and m2 to
w2. An instability is the situation where there is a mutual greater preference for the other person’s
partner than for one’s own. For example m1 would prefer w2 to w1 and likewise w2 prefers m1
to m2.

Input Data:
For this program use the arrays mp and wp above. The data will thus be “given” and not obtained
by reading it in.
Output:
Print out all stable matchings, one per line. This is the same output that we did with the one
dimensional eight queens program.

__________________________________________________________________
Assignment 8 - n queens

By the “n queens problem” we mean the problem of placing n queens on an nXn “chessboard”
in such a way that no queen can capture any other on the next move. In class we solved the “8
queens” problem.
Write a function that inputs an integer n and returns the number of solutions to the “n
queens” problem. Your function should use the one dimensional representation for the board,
the algorithm we discussed in class, and no gotos.

Now, since each time through the loop you will need an array q of a different length, you will
need to allocate the array off of the heap (which we mentioned in class) and not the run-time
stack. To do this you use the “new operator” to request the heap to dynamically allocate the
memory for you.

For example, to get a one dimensional array of integers of size n and called q, we use the
following syntax:
int* q = new int[n];
This allocates the array for us dynamically, at run-time. After this we can use the array q just
as if it had been declared “normally” and it has n elements denoted q[0] through q[n-1].
When we no longer need the memory that was allocated to the array, we write:
delete [ ] q;
For this problem, you pass the required length for the array q to your function, which then
allocates q dynamically (using “new”) and uses it to hold the solutions for the given size. Each
time the function exits, you must deallocate q by calling delete [ ] q. 
__________________________________________________________________
Assignment 9 - Fancy Chessboard

Modify the Eight Queens program (1 dimensional array – no goto version) so that it prints out a
chessboard with some “fancy” representation of a queen in the appropriate positions.
__________________________________________________________________
Assignment 10 - Integrate 

The problem is to write a function “integrate” with prototype:
//FUNC represents functions of one variable that take a double as input and returns a double
typedef double (*FUNC)(double);
double integrate(FUNC f, double a, double b);
so that when it is passed a function f and bounds a and b, the call:
integrate(f, a,b) will return the value of the definite integral of f evaluated between a and b.
test integrate on the following three functions:
1. double line(double x){
return x;
 {
2. double square(double x){
return x*x;
 {
3. double cube(double x){
return x*x*x;
 {
And the following main function:
int main(){
cout<< “The integral of f(x)=x between 1 and 5 is: “<<integrate(line, 1, 5)<<endl;
cout<< “The integral of f(x)=x^2 between 1 and 5 is: “<<integrate(square, 1, 5)<<endl;
cout<< “The integral of f(x)=x^3 between 1 and 5 is: “<<integrate(cube, 1, 5)<<endl;
}
How does integrate work?
Inside a loop we sum up the area of rectangles with a small base (say .0001) and height f(x) for
each x between a and b in increments of .0001.
When the loop terminates, we return the value of the sum.
The purpose if this assignment is to see (and implement) a very simple application of function
pointers. 
__________________________________________________________________
Assignment 11 - Towers of Hanoi

Solve the Towers of Hanoi Problem using recursion
__________________________________________________________________
Assignment 12 - Recursive Stable Marriage

Solve the stable marriage problem from assignment 7 using recursion
__________________________________________________________________
Assignment 13 - Shortest Path

1. Using the outline in the “Handouts” section, write a recursive program that returns the shortest
path through the array. Do not use memoization.
2. Redo part 1 and memoize the cost function. 
__________________________________________________________________
Assignment 14 - Shortest Path Bottom up

3. Modify the memoized version of your program so that it prints the actual shortest path as well
as its cost. The path should be output as the sequence of rows to choose, going from left to right
on the original cost array.
4. In the first 3 problems, you implemented a “top down” approach to solve the problem. Many
dynamic programming problems may be solved quite simply from the “bottom up.” Write a
program to solve the shortest path problem using a bottom up approach. The path should be
output as the sequence of rows to choose, going from left to right on the original cost array.
__________________________________________________________________
Assignment 15 - NK Bishop

We have previously solved the “N Queens Problem”, where, for a given n, we calculated the
number of ways to place n queens on an nXn board. This problem concerns “bishops” on the
chessboard.
What is a bishop?
A bishop is a chess piece that controls all the squares on the two diagonals that it can reach.
Note that a bishop may be either on a white square or a black square.
The problem
Write a program that inputs two integers n and k, where n>=k. Your program should calculate
the number of different ways that k bishops could be placed on an nXn chessboard.
Structure your program using the backtracking scheme that we have used for the eight queens
problem. What needs to be modified is the “OK” function.
Input
Your main program should loop asking the user for values of n and k.
Output
Each time through the loop, output n, k and the number of configurations.
Program Termination
The program will terminate if the user enters a value of -1 for n
__________________________________________________________________
Assignment 16 - RAT Class

Starting with the Rat class (see Handouts) do the following:
1. Add the following operators to the class:
operator-()
operator*()
operator/()
2. Make sure Rats are reduced to lowest terms. So if a Rat is 2/4 it should be
reduced to ½.
3. If a Rat represents an “improper fraction” (i.e. numerator >denominator) print
the Rat as a “mixed number.” So 6/4 will be printed as 1 ½.
__________________________________________________________________
Assignment 17 - Continued Fractions

This assignment involves computing continued fractions, and contains three parts.
The general form of a continued fraction is:
where a0 is an integer, all other ai are positive integers, and n is a non-negative integer. We can
specify a continued fraction by an array of integers containing the values a0 … an.
1. Write a function that takes an array of integers as specified above (and ending with a -1) and
returns the value of the fraction as a double.
2. Write a function that takes an array of integers as specified above (and ending with a -1). Your
function will represent the value of the continued fraction as a “regular” fraction, p/q, in lowest
terms. We are looking for the result of doing the fractional arithmetic and keeping everything in
integers as we work our way through. The function returns a 2-element integer array, v, with
v[0]=p and v[1]=q.
3. Write recursive functions that, given the above representation of a continued fraction, returns
p and q such that p/q represent the value of the continued fraction as a “regular” fraction in
lowest terms, as in question 2 above. 
