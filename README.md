# rl-algorithms

## Value Iteration
1. Initalize all $$Q_{s,a}$$ to zero
2. For every state _s_ and every action _a_ in this state, perform update: $$Q_{s,a} \leftarrow \sum_{s'} p_{a,s\rightarrows')(r_{s,a} + \gamma \max_{a'}(Q_{s',a'}))

## Tabular Q-Learning

## Deep Q-Learning (DQN)
