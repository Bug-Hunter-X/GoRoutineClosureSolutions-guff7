# Go Goroutine Closure Issue
This example demonstrates a common issue when using goroutines in Go loops.  The closure captures the loop variable, not its value at the time of goroutine creation.  This results in all goroutines printing the final value of 'i'.

## Bug
The `bug.go` file contains a simple program that launches 10 goroutines. Each goroutine should print a unique number from 0 to 9. However, due to the closure issue, they all print 10.

## Solution
The `bugSolution.go` file corrects the issue by passing a copy of the loop variable 'i' to each goroutine using a function literal. This ensures that each goroutine has its own copy of the variable, resulting in the expected output.

## How to run
1.  Save the code in `bug.go` and `bugSolution.go`
2.  Run the bug: `go run bug.go`
3.  Run the solution: `go run bugSolution.go`