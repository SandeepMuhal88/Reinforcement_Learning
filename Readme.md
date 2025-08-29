# 📚 End-to-End Reinforcement Learning — Professor-Style Course

## 📖 Table of Contents
- [Lecture 1: Introduction to RL](#lecture-1-introduction-to-rl)
- [Lecture 2: Markov Decision Processes (MDPs)](#lecture-2-markov-decision-processes-mdps)
- [Lecture 3: Dynamic Programming](#lecture-3-dynamic-programming)
- [Lecture 4: Monte Carlo Methods](#lecture-4-monte-carlo-methods)

## Lecture 1: Introduction to RL

- What is RL? (Agent–Environment interaction loop)
- Formalizing the problem: reward hypothesis
- Difference from supervised/unsupervised learning
- Exploration vs. exploitation

> **📌 Mathematics**: Define the RL framework as a sequential decision-making problem.

## Lecture 2: Markov Decision Processes (MDPs)

- **Markov property**: Future depends only on present, not past
- **State space**: S
- **Action space**: A
- **Transition probabilities**: P(s'|s,a)
- **Reward distribution**: R(s,a)
- **Policy**: π(a|s) — stochastic/deterministic

> **📌 Mathematics**:
> Define Value Function:
> ```
> V^π(s) = E_π[∑(γ^t * R_{t+1}) | S_0 = s]
> ```
> 
> Derive Bellman Expectation Equation:
> ```
> V^π(s) = ∑_a π(a|s) ∑_s' P(s'|s,a) [R(s,a,s') + γV^π(s')]
> ```

## Lecture 3: Dynamic Programming (Planning when model known)

- Policy evaluation, policy iteration, value iteration
- Proof of convergence of Value Iteration via contraction mapping theorem

> **📌 Mathematics**:
> Prove that Bellman operator T is a contraction:
>
> `||TV - TU||_∞ ≤ γ||V - U||_∞`
>
> → Guarantees convergence to optimal value function V^*
>
> `|∣TV−TU∣∣ ≤ γ|∣V−U∣∣`
>
> → Guarantees convergence to optimal value function V*
>

## Lecture 4: Monte Carlo Methods (Learning from experience)

- First-visit and Every-visit Monte Carlo
- Monte Carlo policy evaluation & control

> **📌 Mathematics**:
> Show unbiasedness of Monte Carlo estimates:
>
> `𝑉𝜋(𝑠) ≈ 1𝑁(𝑠) ∑ 𝑖=1𝑁(𝑠) 𝐺(𝑖) as 𝑁(𝑠)→∞`
>
> `Vπ(s)≈N(s) 1 i=1 ∑ N(s) 𝐺(G(i)) as N(s)→∞`
>

## Lecture 5: Temporal Difference (TD) Learning

- TD(0) prediction: update rule
- Proof intuition: Why target networks reduce oscillations

> **📌 Mathematics**:
> Derive Q-learning optimality:
>
> `𝑄(𝑠,𝑎) ← 𝑄(𝑠,𝑎) + 𝛼[𝑅𝑡+1+𝛾max𝑎′𝑄(𝑠′,𝑎′)−𝑄(𝑠,𝑎)]`
>
> `Q(s,a)←Q(s,a)+α[Rt+1+γa′maxQ(s′,a′)−Q(s,a)]`
>
> `∇𝐽(𝜃) = 𝐸𝜋[∇𝜃log𝜋𝜃(𝑎∣𝑠)𝑄𝜋(𝑠,𝑎)]`
>
> `∇J(θ)=Eπ[∇θlogπθ(a∣s)Qπ(s,a)]`
>
> `derivation: Likelihood ratio trick`
>

## Lecture 6: Function Approximation in RL

> **📌 Mathematics**:
> Bias-variance decomposition of function approximation error in RL.
>

## Lecture 7: Deep Q-Learning

- DQN: replay buffer, target networks
- Stability improvements: Double DQN, Dueling DQN, Prioritized Replay

> **📌 Mathematics**:
> Proof intuition: Why target networks reduce oscillations
>

## Lecture 8: Policy Gradient Theorem

> **📌 Mathematics**:
> Why value-based methods fail in continuous action spaces
>
> `∇𝐽(𝜃) = 𝐸𝜋[∇𝜃log𝜋𝜃(𝑎∣𝑠)𝑄𝜋(𝑠,𝑎)]`
>
> `∇J(θ)=Eπ[∇θlogπθ(a∣s)Qπ(s,a)]`
>
> `Derivation: Likelihood ratio trick`
>
> `REINFORCE Algorithm (with/without baseline) Variance reduction using advantage functions`
>

## Lecture 9: Actor-Critic Methods

- Actor = policy, Critic = value function
- A2C, A3C, Generalized Advantage Estimation (GAE)

> **📌 Mathematics**:
> Derive advantage function:
>
> `𝐴𝜋(𝑠,𝑎) = 𝑄𝜋(𝑠,𝑎) - 𝑉𝜋(𝑠)`
>
> `Aπ(s,a) = Qπ(s,a) - Vπ(s)`
>

## Lecture 10: Advanced Policy Optimization

- TRPO (Trust Region Policy Optimization) → prove monotonic improvement guarantee
- PPO (Proximal Policy Optimization) → clipping objective
- Continuous control: DDPG, TD3, SAC

## Lecture 11: Model-Based RL

- Planning + learning
- Dyna-Q
- Modern methods: MuZero (combines value, policy, and dynamics model)

## Lecture 12: Advanced Topics

- Exploration: UCB, Thompson Sampling, intrinsic motivation
- POMDPs (Partially Observable MDPs) → belief states
- Multi-Agent RL (MARL)
- Offline RL

## Lecture 13: Ethics, Safety, Applications

- Reward hacking, safe RL
- Applications in robotics, healthcare, finance, games