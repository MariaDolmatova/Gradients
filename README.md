This is a small project aimed to compare 2 numerical optimization algorythms. The code implements two algorithms to find the minimum of a quadratic function: Method of Steepest Descent (fast) and the Conjugate Gradient Method (conj_grad).

**The Target Function**  
The function F is a quadratic form. In matrix notation, it looks like this:  
$$f(x) = \frac{1}{2}x^T Ax + b^T x$$  
Where A is the Hessian matrix (the matrix of second derivatives) and b represents the linear coefficients. The goal is to find the vector $x$ that results in the lowest possible value for $F$.  

**Method of Steepest Descent (fast)**
This is a standard Gradient Descent algorithm.  
How it works: It calculates the gradient (the direction of steepest ascent) and takes a step in the opposite direction.  
The step size l (alpha) is fixed at 0.14.  
The Downside: Because the step size is constant and not optimized at each iteration, it often takes many steps to "zig-zag" to the bottom, especially if the function is shaped like a narrow valley.

**Conjugate Gradient Method (conj_grad)**

This is a much more sophisticated algorithm for solving quadratic problems.  
How it works: Instead of just moving in the direction of the gradient, it moves in "conjugate" directions. This ensures that the progress made in one step isn't "undone" by the next.  
Efficiency: For a system with 4 variables, the Conjugate Gradient method is supposed to find the exact minimum in at most 4 iterations (in perfect arithmetic), whereas Steepest Descent might take dozens or hundreds.
