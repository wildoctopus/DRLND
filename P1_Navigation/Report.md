## Udacity DRLND Navigation project report

### Task Discription: 

The Goal of this excercise is to train an agent to collect as many yellow bananas as possible while avoiding the blue ones in Udacity Banana Collector environemnt. For collecting the correct banana a reward of +1 is given while for wrong one reward of -1 will be awarded to the agent. So agent has to lear this smartly and maximize this cummulative reward. 


### Learning Algorithm

For this project a Deep Q-Network was chosen as a learning algorithm as taught in class excercise, with a simple neural network model with just 2 hidden layers working on the 37 states known to the agent. For more on DQN please check this paper - [Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)


### Network Model :
For this project basic neural Architecture (that is taught in class) has been used. It can be found in the [model.py](model.py) file of the source code. The network consists of 3 fully connected layers with 64, 64, and 4 nodes respectively. 

        fc1_units=64 
        fc2_units=64

        self.fc1 = nn.Linear(state_size, fc1_units)
        self.fc2 = nn.Linear(fc1_units, fc2_units)
        self.fc3 = nn.Linear(fc2_units, action_size)

The parameter action_size = 4.

### Hyper-parameter:

    BUFFER_SIZE = int(1e5)  # replay buffer size
    BATCH_SIZE = 64         # minibatch size (Initially 64)
    GAMMA = 0.995           # discount factor (Initially 0.99)
    TAU = 1e-3              # for soft update of target parameters
    LR = 5e-4               # learning rate (Initially 5e-4)
    UPDATE_EVERY = 4        # how often to update the network

### Plot of Rewards
![alt text](https://github.com/wildoctopus/DRLND/blob/master/P1_Navigation/reward-plot.png)

With the chosen network model, dqn agent and the above hyper-parameters configurations, the agent was able to achieve an average score of 13.0 in 490 episodes.
It can be seen in the above image.

### Future Improvement
