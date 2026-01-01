FACULTY OF TECHNOLOGY & ENGINEERING
Department of Computer Science & Engineering

CSE1405CS: Design and Analysis of Algorithms Practical / Experiment List

(Practical Hours: 2 hours × 1 day per week, per batch)

Updated General Instructions (for all experiments)

· Implement all programs in C on Linux (recommended: GCC).
· For every algorithm implementation, analyze the time complexity theoretically (best/average/worst where applicable).
· For performance measurement, you MUST use gettimeofday() from the Linux C library (sys/time.h).
· Measure only the core computation (e.g., sort function, DP transition loops, heap operations) and avoid including input/output time.
· Report time in microseconds (µs). Run the core operation multiple times (e.g., 30–100 iterations) and report minimum/average to reduce noise.
· For experiments involving randomized input, fix a seed (srand(seed)) and document the input sizes used for analysis.

Exp. No Name of Experiment CO
1 Generate large number of elements randomly and sort all the elements in ascending order using Quick sort & Insertion Sort. Analyze the time complexity for best, average and worst case. C01, C03
2 Generate large number of elements randomly and sort all the elements in ascending order using Merge sort. Analyze the time complexity for best, average and worst case. C01, C03
3 Write a recursive program to (a) find factorial of given number (b) generate Fibonacci series (c) Tower of Hanoi problem . Compare it with iterative methods also if exists. C03
4 Write a program to implement Max-heap sort. C03
5 Write a program to implement Binomial-heap. C03
6 Write a program to implement Making change problem and Knapsack problem using Greedy method. C03
7 Write a program to implement Making change problem using Dynamic programming. C04, C05
8 Write a program to implement Knapsack problem using Dynamic programming. C04, C05
9 Write a program to implement Chained matrix multiplication. C05
10 Write a program to implement n-queen problem using backtracking. C05
11 Write a program to implement assignment problem using branch-and-bound. C06

Sample Example: Measuring core function time using gettimeofday() (microseconds)

Below is a minimal example showing how to measure only the core operation. In this example, we time the sort_core() function and report elapsed time in microseconds.

// Compile: gcc -O2 timing_example.c -o timing_example
#include <stdio.h>
#include <stdlib.h>
#include <sys/time.h>

static inline long long now_us(void) {
struct timeval tv;
gettimeofday(&tv, NULL); // Linux C library call
return (long long)tv.tv_sec * 1000000LL + (long long)tv.tv_usec;
}

// Example "core" operation (replace with your algorithm core)
void sort_core(int *a, int n) {
// Simple insertion sort (demo only). Replace with quick/merge/heap etc.
for (int i = 1; i < n; i++) {
int key = a[i], j = i - 1;
while (j >= 0 && a[j] > key) {
a[j + 1] = a[j];
j--;
}
a[j + 1] = key;
}
}

int main() {
int n = 5000;
int a = (int)malloc(sizeof(int) * n);
if (!a) return 1;

}

Dr. Viral Kapadia