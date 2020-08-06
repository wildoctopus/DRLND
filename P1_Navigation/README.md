
# Project 1: Navigation

## Project Discription

For this project, our aim is to train an agent to navigate (and collect bananas!) in a Banana Collector environment (similar to unity Banana collector Environment) provided by Udacity.<br>
![alt text](https://github.com/wildoctopus/DRLND/blob/master/P1_Navigation/banana_collector_env.gif)

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the final goal of our agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

    0 - move forward.
    1 - move backward.
    2 - turn left.
    3 - turn right.

The task is episodic, and in order to solve the environment, our agent must get an average score of +13 over 100 consecutive episodes.

## Environment/Project setup

Follow the instructions below to explore the environment on your own machine! You will also learn how to use the Python API to control your agent.

Step 1: Clone this repo in your local machine.

Step 2: Download the Unity Environment

For this project, you will not need to install Unity - directly download the prebuilt unity environment from one of the links below. You need only select the environment that matches your operating system:

    Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)<br>
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)<br>
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)<br>
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)<br>

Then, place the file in the p1_navigation/ folder in your cloned repository, and unzip (or decompress) the file.


## Instructions

Follow the instructions provided in Navigation.ipynb to get started with training your own agent!
For information on how the algorithm works and future improvements that can be done,  check [Report.md](Report.md) file. 
