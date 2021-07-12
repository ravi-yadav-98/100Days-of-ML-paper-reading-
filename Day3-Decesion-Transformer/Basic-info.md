## Basic info related to Decision Transformer Paper:-
### Key RL Terms: 
 - In model-free RL you don't learn the state-transition function (the model) and you can rely only on samples
 - V-Function: -> state value function F(s)-->r
 - Q-function :-> state, action functionf(s,a)-->r
 - Temporal difference is an agent learning from an environment through episodes with no prior knowledge of the environment
 - 
### Other paper: RL as one big sequence modelling problem
- Decision Transformer Abstracts RL as Sequence Modelling
- Online RL: agent interacts with environment in real time (agent performs action a and evnironment returns new state s' and reward r)
- Offline Rl: agent is given a experience  dataset of some other agent(in environment) and agent does BC(behaviour cloing of that agent) i.e it learn a poliy using 
that experience dataset to maximize rewards
- Offline algorithms: - Q-learning 
- conservative Q-Learning:--> improves limitations of q-learning (overestimation)
- temporal differnce learning: TD Learning:- 
