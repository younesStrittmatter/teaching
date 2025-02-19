# 2 Temporal Difference Learning

## Table

Open the following link to see a *temporal difference learning* table in action. It is a small table with 3 states and 5
trials. Fill out the values for each state and trial manually to get a better understanding of how temporal difference
learning works.

Tip: Fill out the full table and examine how the values and the prediction error change over time. Think about how the
dopamine signal of the brain is related to the values you see. How would you describe what the brain "rewards" with the
dopamine signal?

<a href="https://younesstrittmatter.github.io/teaching/_static/machine-learning/td/td-table.html" target="_blank">START
EXERCISE</a>

## Model-Free vs Model-Based

In the context of reinforcement learning, there are two main approaches to learning: model-free and model-based.
What is the difference between these two approaches?

<details><summary>Solution</summary>
Both include Q-Values, but they differ in how they are updated.

### Model-Free

- Only the Q-value of the previous state-action pair is updated based on the next state and received reward.
- It does not update Q-values for states that were not directly experienced.
- Updates happen only when actual experience occurs.

### Model-Based

- The Q-value of states leading to the current state can be updated because the model allows simulating future
  transitions.
- The agent can update not just the previous state, but also earlier states that could have led to this state.
- Updates can happen even without actual experience (by using the model to simulate).

</details>

## Exercise 1

What you think about the following statement?

Mice don't like cheese and monkeys don't like bananas. But everybody likes errors!

<details><summary>Solution</summary>
The statement refers to the prediction error in the context of reinforcement learning. Agents like "positive surprises" and dislike "negative surprises". This helps them to steer their behavior to learn the best actions to take in a given environment. The agent is not rewarded by the "cheese" or the "banana" itself, but by the signal that indicates learning progress.
</details>

## Exercise 2
> How $\gamma$-radiation (gamma-radiation) helps the Hulk to take the shortest path.

![hulk](https://younesstrittmatter.github.io/teaching/_static/machine-learning/td/hulk.jpg)


### Exercise 2a

![reward-discounting](https://younesstrittmatter.github.io/teaching/_static/machine-learning/td/reward-discounting.png)

- Should you prefer the red path or the blue path?
- How can an agent learn to prefer the blue path?

<details><summary>Solution</summary>
Discounting future rewards (in equations typically written as $\gamma$-factor) is crucial to preferring shorter rewards. With "pure" Q-Values that don't discount future rewards, an agent would not prefer a shorter path since the overall reward is the same. By discounting future rewards, the agent learns to prefer shorter paths because the overall discounted reward of a shorter path is higher than that of a a longer path.
</details>

### Exercise 2b

- Could you imagine another mechanism (other then the one described in the solution) where an agent could learn to prefer the
  blue path?

<details><summary>Solution</summary>
Instead of discounting rewards, we could also give negative reward (instead of 0 reward) for states that don't have food (Yeh dining hall). This would make the agent learn to "avoid" as much as possible states between the starting point and the dining hall, effectively leading the agent to learn the shortest path. This also leads to an agent that not just randomly explores its environment, but actively tries to avoid states it has already visited and that are not rewarding (steered exploration).
</details>





