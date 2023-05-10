# starter kit for line search

# Introduction 
In this assignment, you will implement the following algorithms and apply them to the test problems. 

- Backtracking line search
- Steepest descent method with line search

Your submission repository should be organized as follows.

```
-- root
   |-- steepest_descent.py
   |-- test_steepest_descent.py
   |-- backtracking.py
   |-- README.md
```

The test files are provided in this starter kit. You should implement the algorithms in the corresponding files. 

## Backtracking Line Search
In this part, you will write a program to solve some test problems using the heavy ball method with backtracking line search. 

- Guideline
  
  Here is a guideline for implementing the backtracking line search subroutine.
  - The implementation is designed to help you understand the algorithm.
  - You are welcome to discuss this with others but should implement it on your own. 
  - The repository should contain the following file:
    - `backtracking.py`: the implementation of the backtracking line search.
- Implementation
  - Task: Implement the backtracking line search, the algorithm follows the following steps:
    > 1. Initialize $\alpha$ and $\rho\in(0,1)$ and Wolfe constant $c_1\in (0, 1)$.
    > 2. Set $\alpha_k = \alpha$.
    > 3. While $f(x_k + \alpha_k d_k) > f(x_k) + c_1 \rho\alpha_k \nabla f(x_k)^T d_k$, update $\alpha_k = \alpha_k \rho$.
    > 4. Return $\alpha_k$.
- Coding (Python)
  - The function name should be `backtracking` and should be defined in the file `backtracking.py` with the following signature:
    - `backtracking(f, grad_f, x, d, alpha, rho, c1)`: the function for the backtracking line search.


## Steepest Descent Method
In this part, you will write a program to solve some test problems using the steepest descent method with the exact line search and without line search (step length is fixed). 

- Guideline
  
  Here is a guideline for implementing the steepest descent method with line search.
  - The implementation is designed to help you understand the algorithm.
  - You are welcome to discuss this with others but should implement it on your own. 
  - The repository should contain the following files:
    - `steepest_descent.py`: the implementation of the steepest descent method with line search.
    - `test_steepest_descent.py`: the test script for `steepest_descent.py`.
- Implementation
  - Task 1: Implement the steepest descent method with **exact** line search, the algorithm follows the following steps:
  >1. Initialize $x_0$ and set $k=0$.
  >2. Compute the search direction $d_k = -\nabla f(x_k)$.
  >3. Compute the step size $\alpha_k$ by exact line search.
  >4. Update $x_{k+1} = x_k + \alpha_k d_k$.
  >5. If the stopping criterion $\|d_k\|<\text{tol}$ is satisfied, stop; otherwise, set $k=k+1$ and go to step 2. 
  - Task 2: Implement the steepest descent method with **fixed** step length, the algorithm follows the following steps:
    > 1. Initialize $x_0$ and set $k=0$ and a fixed step size $\alpha$.
    > 2. Compute the search direction $d_k = -\nabla f(x_k)$.
    > 3. Update $x_{k+1} = x_k + \alpha d_k$.
    > 4. If the stopping criterion $\|d_k\|<\text{tol}$ is satisfied, stop; otherwise, set $k=k+1$ and go to step 2.
  - Task 3: Implement the steepest descent method with backtracking line search, the algorithm follows the following steps:
    > 1. Initialize $x_0$ and set $k=0$.
    > 2. Compute the search direction $d_k = -\nabla f(x_k)$.
    > 3. Compute the step size $\alpha_k$ by backtracking line search.
    > 4. Update $x_{k+1} = x_k + \alpha_k d_k$.
    > 5. If the stopping criterion $\|d_k\|<\text{tol}$ is satisfied, stop; otherwise, set $k=k+1$ and go to step 2.
- Coding (Python)
  - The function name should be `steepest_descent_exact` and `steepest_descent_fixed` and `steepest_descent_backtracking` for the exact line search, fixed step length and backtracking line search, respectively.
  - The functions should be defined in the file `steepest_descent.py` with the following signatures:
    - `steepest_descent_exact(f, grad_f, x0, tol, max_iter)`: the function for the steepest descent method with exact line search.
    - `steepest_descent_fixed_step(f, grad_f, alpha, x0, tol, max_iter)`: the function for the steepest descent method with backtracking line search. 
    - `steepest_descent_backtracking(f, grad_f, x0, tol, max_iter)`: the function for the steepest descent method with backtracking line search.

In the ``README.md`` file, you should include the following information:
- Your name and email address.
- The list of files in your submission repository.
- The description of the implementation and report comparison results for convergence behavior, number of iterations for the three methods based on the test cases.