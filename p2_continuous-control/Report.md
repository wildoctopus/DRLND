Udacity DRLND Continous Control project Report

Task Description:

For this project, we have to work with the Reacher environment, where a double-jointed arm is trained to reach to a target location. Now a reward of +0.1 is given to the agent if its hand is in the goal position.
Thus, the goal of our agent is to maintain its position at the target location for as many time steps as possible. Now as the task is episodic, so in order to solve the environment, our agent must get an average score of +30 over 100 consecutive episodes.

Examine the State and Action Spaces: 
Below code cell and output gives information about the Environment and shows how random initialization of state looks like for first agent. 

                # reset the environment
                env_info = env.reset(train_mode=True)[brain_name]

                # number of agents
                num_agents = len(env_info.agents)
                print('Number of agents:', num_agents)

                # size of each action
                action_size = brain.vector_action_space_size
                print('Size of each action:', action_size)

                # examine the state space 
                states = env_info.vector_observations
                state_size = states.shape[1]
                print('There are {} agents. Each observes a state with length: {}'.format(states.shape[0], state_size))
                print('The state for the first agent looks like:', states[0])

                Number of agents: 1
                Size of each action: 4
                There are 1 agents. Each observes a state with length: 33
                The state for the first agent looks like: [  0.00000000e+00  -4.00000000e+00   0.00000000e+00   1.00000000e+00
                  -0.00000000e+00  -0.00000000e+00  -4.37113883e-08   0.00000000e+00
                   0.00000000e+00   0.00000000e+00   0.00000000e+00   0.00000000e+00
                   0.00000000e+00   0.00000000e+00  -1.00000000e+01   0.00000000e+00
                   1.00000000e+00  -0.00000000e+00  -0.00000000e+00  -4.37113883e-08
                   0.00000000e+00   0.00000000e+00   0.00000000e+00   0.00000000e+00
                   0.00000000e+00   0.00000000e+00   5.75471878e+00  -1.00000000e+00
                   5.55726671e+00   0.00000000e+00   1.00000000e+00   0.00000000e+00
                  -1.68164849e-01]




Learning Algorithm :
To solve this problem i have used  Deep Deterministic Policy Gradient (DDPG) code explained in the course lecture. For more info, please see the paper [inser link for DDPG]. 
The model used in this have three fully connected layers for Actor and Critic, with alternative batch normalization layer. Ornstein-Uhlenbeck noise has also been used with the default value provided in the paper. 
For complete model structure please see model.py[link] in this repo. 
Below is the hyperparameters configuration, which helped me in acheving the required score in just 110 episode. 


Hyper-parameters and Agents initializations:

                  BUFFER_SIZE = int(1e5)  # replay buffer size
                  BATCH_SIZE = 128        # minibatch size
                  GAMMA = 0.99            # discount factor
                  TAU = 1e-3              # for soft update of target parameters
                  LR_ACTOR = 2e-4         # learning rate of the actor 
                  LR_CRITIC = 2e-4        # learning rate of the critic
                  WEIGHT_DECAY = 0        # L2 weight decay

                  agent = Agent(state_size=state_size, action_size=action_size, random_seed=11)
With the above hyperparameter tuning , i got a good result that can be seen in below section. 

Reward Plot :
[insert image continuos_reward_plot.png]
It can be seen from the figure that Environment got solved in 110 episode with an avarage score of 31.97, which is a good result, just by tweaking the hyperparameters.

Future Improvements :

While looking for different sources found that one can go with Proximal Policy Optimization (PPO)(https://www.researchgate.net/publication/330105099_Learning_Continuous_Control_through_Proximal_Policy_Optimization_for_Mobile_Robot_Navigation)  for this project. 
Second, I would like to check D4PG and Prioritized experience replay to see how it improves the learning process.
