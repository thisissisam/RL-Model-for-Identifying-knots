# RL-Model-for-Identifying-Knots
Reinforcement Learning Model for simplifying knots through braid operations and identifying them

## How It Works
Every knot can be uniquely represented as a braid (an element of the braid group). When the ends of a braid are connected (called the *closure* of the braid), it becomes a knot (or a link). Braid relations and Markov moves act on braids without changing the underlying knot. Using these operations, one can usually simplify a knot by decreasing the number of crossings. Once the braid has been simplified, the model checks whether it exists in the braid–knot database. If not, it attempts further simplification and repeats the process.

## How Reinforcement Learning Works
The main concepts of Reinforcement Learning are **state**, **agent**, **action**, **environment**, **policy**, and **reward function**.

**State**: what the *agent* observes.  
**Environment**: where the *state* lives, which *actions* are possible, and what their consequences are.  
**Action**: what the *agent* decides to do. When an *action* is taken, the *environment* computes the resulting *reward* and *new state*.  
**Policy**: which *action* to take given the *current state*.  
**Reward Function**: determines the *reward* based on the state and action.  
**Agent**: the entity being trained; it evaluates the current *state* and tries to choose the best *actions* to maximize the *reward*.

The main challenges of RL are as follows:

- Designing a *reward function* such that the *agent* achieves the intended goal, which is often referred to as **Reward Engineering**  
- Determining the best RL model for the specific problem, such as PPO, Q-Learning, DDPG, or multi-policy approaches (combinations of different models and policies)  
- Setting up the *environment*  
- Choosing and fine-tuning the hyperparameters of the RL model, such as:  
  - **Learning Rate**: how fast the *policy* updates  
  - **Clip Range**: prevents overly large *policy* changes  
  - **Batch Size**: how much data is used per update  
  - **Gamma**: how much future reward matters, etc.

## RL for Knot Solving
In our case, the *environment* is the braid, and the possible *actions* are the braid and Markov moves. The *state* is again the braid itself. For this implementation, the Proximal Policy Optimization (maskable) model is chosen because it is a stochastic policy suitable for discrete action spaces and exploration. PPO also prevents the *policy* from changing too quickly. A mask is used on top of the policy because not all actions are legal in every state; illegal actions are masked out, and the agent receives a large penalty for attempting an invalid move.

**This RL Modal was a project for a modul `Weiterführung Topologie: Knoten Theorie und Machine Learning` in Bergische University of Wuppertal. The Modal still doesn't work as of now and I am trying to figure out the problem.**
The possible problems could be: 
- inappropriate use of the maskable PPO modal
- unoptimized reward system for the goal
- possible bloatware from the sage library, since the braid and its operations are realised thorugh the sage library, which increased the training time
- small training sample

