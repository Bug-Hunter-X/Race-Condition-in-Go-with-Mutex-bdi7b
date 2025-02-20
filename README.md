# Race Condition in Go with Mutex

This repository demonstrates a race condition in a Go program that uses goroutines and mutexes to calculate the sum of numbers. The program appears to work correctly but produces incorrect results because of the race condition.  The solution demonstrates how to correctly fix this race condition.

## Bug Description

A race condition occurs when multiple goroutines access and modify the same shared variable concurrently without proper synchronization. In this case, the `x` variable is shared by multiple goroutines, and the `sync.Mutex` is not used correctly to protect it, leading to inconsistent results.

## Solution

The solution corrects the race condition by ensuring that the `m.Lock()` and `m.Unlock()` calls are properly paired and that the mutex is held for the entire duration of the critical section.

## How to run

1. Clone the repo
2. Navigate to the repo directory
3. Run the bug program using `go run bug.go`
4. Run the solution program using `go run bugSolution.go`
5. Compare the results

The bug program will likely produce a wrong sum while the solution program will produce the correct sum (499500).