# Project 3: Colloboration and Competition

## Introduction

For this project, we go with the Tennis environment.


The aim of this project was to implement and train agent/s to play table tennis. The two agents were provided control of rackets to bounce a ball over a net. A reward of +0.1 is given to an agent if it is able to hit the ball over the net. A penalty point of -0.01 is given when the ball hits the ground or his the ball out of the play area.

This is an episodic problem where the goal is for the agent to continuously keep the ball in the air.



+ After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.

+This yields a single score for each episode.

The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.


## Run Instructions


1. The system requires python 3.6 installed in a python virtual envirnonment
```
conda create --name drlnd python=3.6
source activate drlnd

pip install ./python
```

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Soccer/Soccer_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Soccer/Soccer.app.zip)

2. Place the file in the `p3_collab-compet/` folder, and unzip (or decompress) the file. 


3. Run project3_final.ipynb
