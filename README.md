# rl-algorithms

## Value Iteration
1. Initalize all $$Q_{s,a}$$ to zero
2. For every state _s_ and every action _a_ in this state, perform update: 
$$ Q_{s,a} \leftarrow \sum\nolimits_{s'} p_{a,s\rightarrow s^\prime}(r_{s,a} + \gamma \max\nolimits_{a^\prime}Q_{s^\prime,a^\prime)}
$$ 
3. Repeat step 2

Code from Deep Reinforcement Learning by Maxim Lapan. 

We initialize an Agent that has:<br>
Environment (env): Based on the OpenAI environment chosen<br>
State (state): State in the environment<br>
Rewards (rewards): float of collections.defaultdict (based on state-action-new_state tuple)<br>
Transits (transits): collections.Counter of collections.defaultdict (based on state-action pair and a counter for each new_state from each pair)<br>
Values (values): float of collections.defaultdict (based on state-action pair)<br>

Start by playing 100 random steps. For each step, sample a random action and determine the new_state, reward, and is_done from the selected action. Update the state to the new state (or reset if the episode ended), update the transit counter for this state-action-new_state +=1, and update the rewards for this state-action-new_state to the reward obtained. 

Do value iteration. Go through every state-action pair in a for loop. The goal of this loop is to get a value for each state-action pair. We start by setting this value to 0 and then iterating through the target states (i.e. new_state from above) given this state-action pair -- we already have a list of the new_states given this state-action pair and the counts for each one. For each target state, we take the reward, the best action from that target state, and the normalized value for this state-action-reward-new_state-best_action tuple. 

Finally, we run test episodes and compute the average reward from the test episodes. Each test episode runs until the end of the episode and finds the best action from each current state, then moves to the next state based on that action. State rewards and transits are updated here just as in the 100 random step function. 

## Tabular Q-Learning

## Deep Q-Learning (DQN)
