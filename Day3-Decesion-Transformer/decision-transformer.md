### Day:03 Date: 06/07/2021
### Decision Trasformer --> [paper link:](https://arxiv.org/pdf/2106.01345v1.pdf)

### Decision Transformer: Reinforcement Learning via Sequence Modeling

#### Abstract:
- We introduce a framework that abstracts Reinforcement Learning (RL) as a sequence modeling problem
- It casts the problem of RL as conditional sequence modeling.
- Similar to language models (i.e BERT and GPT-x)
- Decision Transformer simply outputs the optimal actions by leveraging a causally masked Transformer.
- By conditioning an autoregressive model on the desired return (reward), past states, and actions, our Decision Transformer model can 
generate future actions that achieve the desired return

#### Introduction:
- For Zero Shot Learning(ZSL): Dataless/zero data classification  (learner predicts classes which were not used during training)
- Recent work has shown transformers [1] can model high-dimensional distributions of semantic
concepts at scale, including effective zero-shot generalization in language
- **Can transformers use for sequential decision making problems: --> RL**
- **Like Generative trajectory modelling: -> modeling the joint distribution of the sequence of states, actions, and rewards – can serve as a
replacement for conventional RL algorithms.**
- In conventional RL, we train a policy (i.e Temporal diff), but here we will train a transformer collected experience using sequential modelling objective
- This will allow us to bypass the need for bootstrapping for long term credit assignment – thereby avoiding one of the “deadly triad” [6] known
to destabilize RL
- It also avoids discounting future rewards.
-  we can make use of existing transformer frameworks widely used in language and vision that are easy to scale, utilizing a
large body of work studying stable training of transformer models.

### Advantage of Transformers over RL:
   - Transformers can perform credit assignment directly via self-attention, in contrast to
Bellman backups which slowly propagate rewards and are prone to “distractor” signals
 - This can enable transformers to still work effectively in the presence of sparse or distracting rewards.
 - Finally, empirical evidence suggest that a transformer modeling approach can model a wide distribution of
behaviors, enabling better generalization and transfer.
 - No need of discounting future rewards
 - no need of bootstrapping for credit assignment.  --> avoid destablize RL
 
### Hypothesis: Offline RL:
 - This procedure of learning a policy or Q-function from static data with no further interaction with the environment 
 is called Offline RL (sometimes called Batch RL)
 -  It is producing maximally effective behavior from fixed, limited experience.
 -  Issues with offline RL: --> Overestimation and error propagation
 -  By taining an autoregressive model on sequences of states, actions, and returns, we reduce policy sampling to autoregressive generative

### Key Poinst:
  - we propose Decision Transformer, where we use the GPT architecture to autoregressively model trajectories
  - Use for RL Benchmarks: Atari, openAI Gym, Key to door 
  -  Decision Transformer matches or exceeds the performance of state-of-the-art model-free offline RL algorithms
  -  Furthermore, in tasks where long-term credit assignment is required, Decision Transformer capably outperforms the RL baselines
 
## Preliminaries:
1. **OffLine RL**
   - Markov decision process: tuple( S,A,P,R):
   - State(S), action(A), Transition probabilities(P), rewards(R)
   - P = p(s'/s, a)
   - r = R(s,a)
   - A trajectory is made up of a sequence of states, actions, and rewards: τ = (s0, a0, r0, s1, a1, r1, . . . , sT , aT , rT ).
   - The goal in reinforcement learning is to learn a policy which maximizes the expected return (sum of discounted rewards)
   -  In offline reinforcement learning, instead of obtaining data via environment interactions, we only have access to some fixed limited
dataset consisting of trajectory rollouts of arbitrary policies.
  - This setting is harder as it removes the ability for agents to explore the environment and collect additional feedback.

2. **Transformers**
   - as an architecture to efficiently model sequential data.
   - these models consist of stacked self-attention layers with residual connections
   - each self-attention layesr recieves n-embeddings and outputs n-embeddings
 
 
 ## Method:
  - we present Decision Transformer, which models trajectories autoregressively with
minimal modification to the transformer architecture,
  -  


  

