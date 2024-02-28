**Tower of Hanoi Recursion Solver**

This Python script provides a solution to the classic Tower of Hanoi problem using recursion. The Tower of Hanoi is a mathematical puzzle that consists of three rods and a number of disks of different sizes which can be slid onto any rod. The puzzle starts with the disks in a neat stack in ascending order of size on one rod, the source rod, with the smallest disk at the top.

The objective of the puzzle is to move the entire stack to another rod, obeying the following rules:

1. Only one disk can be moved at a time.
2. Each move consists of taking the top disk from one stack and placing it on another stack.
3. No disk may be placed on top of a smaller disk.

The script takes the number of disks as input and solves the Tower of Hanoi puzzle, printing each move until all disks are moved to the target rod.

**Usage:**

Before running the script, you can adjust the `NUMBER_OF_DISKS` variable to specify the number of disks in the Tower of Hanoi puzzle. Additionally, you can modify the initial configuration of the rods (`A`, `B`, and `C`) according to your preference.

**Example:**

Suppose you want to solve the Tower of Hanoi puzzle with 5 disks, with all disks initially placed on rod `A`. You can run the script with the following setup:

```python
NUMBER_OF_DISKS = 5
A = list(range(NUMBER_OF_DISKS, 0, -1))
B = []
C = []

def move(n, source, auxiliary, target):
    if n <= 0:
        return
    move(n - 1, source, target, auxiliary)
    target.append(source.pop())
    print(A, B, C, '\n')
    move(n - 1, auxiliary, source, target)

# initiate call from source A to target C with auxiliary B
move(NUMBER_OF_DISKS, A, B, C)
```

This will print the steps required to move all disks from rod `A` to rod `C`, adhering to the rules of the Tower of Hanoi puzzle.

**Note:**

- Ensure that the Python environment where the script is executed supports recursion, as large numbers of disks may cause stack overflow errors in environments with limited recursion depth.
