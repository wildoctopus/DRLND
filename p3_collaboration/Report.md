Udacity DRLND Collaboration and Competition project Report

Task Description:

Examine the State and Action Spaces:
The environment have two agents playing tenis, where a agent is rewarded with a reward of +0.1 if it hits the ball over the net in oponent side otherwise a receives a reward of -0.1. 
So the goal of the agent is to score as much as possible keeping the ball in play. 
The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. 
So, the task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).
Below sections shows the environment info and how a Random state for first agent looks like: 


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

        Number of agents: 2
        Size of each action: 2
        There are 2 agents. Each observes a state with length: 24
        The state for the first agent looks like: [ 0.          0.          0.          0.          0.          0.          0.
          0.          0.          0.          0.          0.          0.          0.
          0.          0.         -6.65278625 -1.5        -0.          0.
          6.83172083  6.         -0.          0.        ]
          


Learning Algorithm :

For this project, DDPG algorithm has been used to initialized the two agents (see in below section), where a parameter "memory" has been passed to other agent for shared replay buffer.
Model and Networks has been kept similar to second project(Continuous Control) with some tweaking in Hyper-parameters to acheive the results in decent number of episodes.

The important part is the "memory" parameter passed as a input to second Agent , so that theri experience can be combined, which make them learn effectively. 
For Model, as just stated above, it has been kept close to previous project, that is 3 fully connected layers has been used with alternate batch normalization layer to improve the learning speed.
Below section shows the hyperparameters values kept for this project.(one can tweak this to see the improvements)

Hyper-parameters and Agents initializations:

                          BUFFER_SIZE = int(1e6)  # replay buffer size
                          BATCH_SIZE = 512        # minibatch size
                          GAMMA = 0.99            # discount factor
                          TAU = 1e-3              # for soft update of target parameters
                          LR_ACTOR = 1e-4         # learning rate of the actor 
                          LR_CRITIC = 1e-4        # learning rate of the critic
                          WEIGHT_DECAY = 0        # L2 weight decay

                          agent1 = Agent(state_size=state_size, action_size=action_size, random_seed=13)
                          agent2 = Agent(state_size=state_size, action_size=action_size, random_seed=13, memory=agent1.memory)

Reward Plot :
                          scores = ddpg()

                          Unity Academy name: Academy
                                  Number of Brains: 1
                                  Number of External Brains : 1
                                  Lesson number : 0
                                  Reset Parameters :

                          Unity brain name: TennisBrain
                                  Number of Visual Observations (per agent): 0
                                  Vector Observation space type: continuous
                                  Vector Observation space size (per agent): 8
                                  Number of stacked Vector Observation: 3
                                  Vector Action space type: continuous
                                  Vector Action space size (per agent): 2
                                  Vector Action descriptions: , 
                          Episode 50	Average Score: 0.00
                          Episode 100	Average Score: 0.01
                          Episode 150	Average Score: 0.03
                          Episode 200	Average Score: 0.00
                          Episode 250	Average Score: 0.01
                          Episode 300	Average Score: 0.01
                          Episode 350	Average Score: 0.01
                          Episode 400	Average Score: 0.01
                          Episode 450	Average Score: 0.02
                          Episode 500	Average Score: 0.02
                          Episode 550	Average Score: 0.02
                          Episode 600	Average Score: 0.04
                          Episode 650	Average Score: 0.04
                          Episode 700	Average Score: 0.02
                          Episode 750	Average Score: 0.04
                          Episode 800	Average Score: 0.04
                          Episode 850	Average Score: 0.03
                          Episode 900	Average Score: 0.03
                          Episode 950	Average Score: 0.05
                          Episode 1000	Average Score: 0.06
                          Episode 1050	Average Score: 0.11
                          Episode 1100	Average Score: 0.12
                          Episode 1150	Average Score: 0.16
                          Episode 1200	Average Score: 0.14
                          Episode 1250	Average Score: 0.17

                          Environment solved in 1298 episodes!	Average Score: 0.55

[insert image]


Future Improvements :
Wile looking for different sources and reffering to few papers found that one can go with Proximal Policy Optimization (PPO) [link] for this project. 
Second, one can try to prioritized experience replay to improve the learning process.
