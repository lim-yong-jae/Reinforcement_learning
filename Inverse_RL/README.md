# What is Inverse Reinforcement Learning(IRL): 
 Reinforcement learning uses rewards which are gotten from environment's predefined function. But what if that function is not existed, how we can do reinforcement learning? Many problems from real world, there are not reward functions. So we should devise the method for this situation.   
 Inversere Reinforcement learning can be one of the solution of that situation. It infers reward function from environments by using expert trajectories data. So it does not need reward functions, because it infers it. In this repository i summarize papers which are related with Inverse Reinforcement Learning(IRL), and add proofs, explanation, my insights.  
## Train Flow of IRL: 
 In Expert trajectories data expert actions are the global optimum. Therefore actor is trained to output that actions and reward function which is inferred from expert traj data give high reward that actions. 
 
## what is dIfference between Actor critic and IRL:   
 Actor critic uses two functions, but IRL use only actor funtion. IRL does not need Critic, because it uses expert traj. Expert traj data is Critic by itself. To be more detail, IRL assumes expert traj datas' state action pairs' actions always have the highest value on that states. Therefore we just do tune actor function output expert's trajectory datas' action on that state. In that process, we can get many reward functions which make expert trajs optimal.

## Can we use Maximum likelihood method for training actor?  
 By using MLE for traning actor, we can train actor for having high probability on specific state. Therefore we can surely get actions from states in expert traj. But there is a problem. Actor does not train states' feature or properties. Actor just remember (state-action) pair. So when it encounters strange states which does not appear in expert traj, It has high proabiltiy for choosing wrong action.  
 
## How to train actor for implementing IRL paper's model? 
 I use my PG repository's trained actor for getting expert traj. And use it for training IRL's actor model. Pendulum-v1 is the target game.  

# Paper
1. Algorithms for Inverse Reinforcement Learning: http://ai.stanford.edu/~ang/papers/icml00-irl.pdf  
 It tries to make IRL problem to computational tasks by using MDPs with optimal policy. Optimal policy is given by state-action pair sequential data. From that optimal policy, this paper suggests how to get reward function on 3 cases( 1) finite state space, 2) constraint condition with finite state space, 3) infinite state space.). But there are many reward function even constant or zero could be reward function. So it uses constraint condition for getting approximated reward function which is the closest to true. And it uses linear combiation form for approximating reward function where it is infinite state space case. For solving that case, it uses linear programming with constraint condition such as penalty and sampling.    
 
3. Apprenticeship Learning via Inverse Reinforcement Learning:  
4. Maximum Margin Planning:  
5. Maximum Entropy Inverse Reinforcement Learning:  
6. Generative Adversarial Imitation Learning:   
7. Variational Discriminator Bottleneck: Improving Imitation Learning, Inverse RL, and GANs by Constraining Information Flow:  

