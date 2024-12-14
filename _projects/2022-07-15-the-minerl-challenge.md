---
layout: project
title:  The MineRL Challenge
date:   2020-12-31
image:  images/project1_MineRL/minerl.png
tags:   fixedwing swarming robotics ros ros2 collision avoidance uav 
---
*On the cover: A minerl gym environment (From gameplay of an RL Agent, by openAI)*

This was a project initiated by Analytics Club, IIT Madras. The goal of the project was to tackle the challenges provided in the [MineRL Competition](https://www.aicrowd.com/challenges/neurips-2022-minerl-basalt-competition). At an initial level, exposure toward Reinforcement learning algorithms was obtained by training AI Agents to play the cartpole challenge. And later basic atari games like Montezuma's revenge.


## Cartpole challenge:
![team](/images/project_MineRL/cartpole.png)
*Kernel 1.0 running the heats*
This challenge is a very basic gym environment, from OpenAI. It's a basic visualization of a control problem. A cart needs to be moved in a fashion to support the pole attached at the centre of the cart. The RL Agent needs to learn from the state-space to not overshoot and balance the pole upright with minimal movement across the environment. We trained an agent using basic algorithms including Deep Q-Learning and varying hyper parameters to compare the results. Moreover, this provided us with a better understanding of video frame based state-space estimation and CNN architectures.

## Montezuma's revenge :
![team](/images/project_MineRL/montezuma.jpg)

Montezuma's Revenge is a video game that was released for many different consoles and computers, including the Atari 2600, ColecoVision, Atari 5200, Apple II, Commodore 64, IBM PC, and Atari 8-bit computers. It had a little complicated action space, but still it was a 2D game. In this we tried different training methods and tried to experiment more with imitation learning, a fancy name for supervised learning, where the agent learns from the actions of the training data, where it tries to imitate the moves performed by him. We also employed Soft Actor crtitic (SAC) and Proximal Policy Optimization (PPO) algorithms to compare the results.

## Later :
2D game environments were straightforward and easy for an agent to learn. But Minecraft environment is in 3D and the agent needs to develop a spatial awareness. This means a continuous state-space and due to limited knowledge and time constraints, we did not get a chance to explore the latter part. 

![alt](/images/project10/comm_architecture.png)
*Communication architecture for fixedwing swarming*
