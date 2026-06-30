## Introduction 

"Gradient descent is a method for [[unconstrained]] mathematical [[optimization]]. It is a [[first-order]] [[iterative]] [[algorithm]] for minimizing a [[differentiable]] [[multivariate]] [[function]].

The idea is to take repeated steps in the opposite direction of the [[gradient]] (or approximate [[gradient]]) of the [[function]] at the current point, because this is the direction of steepest descent. Conversely, stepping in the direction of the gradient will lead to a trajectory that [[maximizes]] that function; the procedure is then known as gradient ascent. Gradient descent should not be confused with local [[search]] [[algorithm|algorithms]], although both are iterative methods for optimization.

Gradient descent is particularly useful in [[machine learning]] and [[artificial intelligence]] for minimizing the [[cost function|cost]] or [[loss function]].

Gradient descent is generally attributed to Augustin-Louis Cauchy, who first suggested it in 1847. Jacques Hadamard independently proposed a similar method in 1907. Its [[convergence]] properties for [[non-linear optimization]] problems were first studied by Haskell Curry in 1944, with the method becoming increasingly well-studied and used in the following decades.

A simple extension of gradient descent, [[stochastic gradient descent]], serves as the most basic algorithm used for training most [[deep networks]] today."^[https://en.wikipedia.org/wiki/Gradient_descent]

## Mathematics

### Definition

- The update rule is:^[https://introml.mit.edu/_static/fall24/LectureNotes/chapter_Gradient_Descent.pdf]
  $$
  \theta_{t+1} = \theta_t - \eta_t \nabla_{\theta} \mathcal{J}(\theta_t)
  $$

- $\theta$ is the generic [[parameter]] [[vector]], mathematically belonging to a parameter [[space]] such as $\Theta \subseteq \mathbb{R}^d$ ([[real numbers]]).

- $t$ is the iteration index, mathematically belonging to the [[nonnegative]] [[integers]] $\mathbb{N}_0 = \{0,1,2,\dots\}$.

- $t+1$ is the next iteration index, mathematically also belonging to $\mathbb{N}_0$.

- $\theta_t$ is the current parameter vector at iteration $t$, mathematically belonging to $\mathbb{R}^d$.

- $\theta_{t+1}$ is the updated parameter vector after one optimization step, mathematically belonging to $\mathbb{R}^d$.

- $\eta_t$ is the learning rate or step size at iteration $t$, mathematically a [[positive]] [[scalar]] belonging to $\mathbb{R}_{>0}$.

- $\mathcal{J}$ is the [[objective function|objective]], [[cost function|cost]], or [[loss function]] being [[minimized]], mathematically a [[function]] $\mathcal{J}:\mathbb{R}^d \to \mathbb{R}$.

- $\mathcal{J}(\theta_t)$ is the scalar loss value obtained by evaluating the objective function at the current parameter vector, mathematically belonging to $\mathbb{R}$.

- $\nabla_{\theta}$ is the [[gradient]] operator with respect to the parameter vector $\theta$, mathematically producing a vector of [[partial derivative|partial derivatives]] with respect to the components of $\theta$.

- $\nabla_{\theta}\mathcal{J}(\theta_t)$ is the gradient of the objective at $\theta_t$, mathematically belonging to $\mathbb{R}^d$ and pointing in the direction of steepest local increase of $\mathcal{J}$.

- $-\nabla_{\theta}\mathcal{J}(\theta_t)$ is the negative-gradient direction, mathematically belonging to $\mathbb{R}^d$ and pointing in the direction used to locally decrease $\mathcal{J}$.

- $\eta_t\nabla_{\theta}\mathcal{J}(\theta_t)$ is the [[scaling|scaled]] gradient step, mathematically belonging to $\mathbb{R}^d$ because a scalar $\eta_t$ multiplies a vector $\nabla_{\theta}\mathcal{J}(\theta_t)$.

- $\theta_t - \eta_t\nabla_{\theta}\mathcal{J}(\theta_t)$ is the full update expression, mathematically belonging to $\mathbb{R}^d$ because it subtracts one vector in $\mathbb{R}^d$ from another vector in $\mathbb{R}^d$.

- The whole equation says that the next parameter vector $\theta_{t+1}$ is obtained by moving the current parameter vector $\theta_t$ a distance controlled by $\eta_t$ in the negative-gradient direction of the objective $\mathcal{J}$.

### Worked example