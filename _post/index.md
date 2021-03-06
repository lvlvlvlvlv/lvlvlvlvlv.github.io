---
layout：post
---

# Instructions

**Below are simple instructions of my projects on GitHub**

## (1) Robotics-Naigation-Deep-Reinforcement-Learning
### why do I start this project?
I am focusing on the robotics navigation problem with reinforcement learning methods. All the time people consider SLAM methods as the kernel solution for navigation purpose of robot. However, SLAM method has a few difficulty parts that are not well solved for a long time. I'm considering and trying to find a distinctive way, with the help of deep reinforcement learning method, to see if there are any improvement in robotics navigation.

### what is in this project?
Currently, I am trying to apply deep-Q-network and DDPG algorithms on different agent navigation scenarios(mainly crossroads) in simulation environment(SUMO) to see if the DRL methods could improve efficiency and safety in complicated navigation tasks. I also want to check whether there are some ways to transfer the trained model to real world tasks. 

![screen shot](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/programImage.png)  

-  **basic** : Include the elementary parts of a 'SUMO' map 

      **IMPORTANT**: SUMO is the short of "Simulation of Urban Mobility". It is a software which help you creat any kinds of traffic simulation scenes quickly. 

      **IMPORTANT**: You'd better read the tutorials of SUMO first in order to understand the content below. Tutorials are here: [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials).Apart from that, the blog is great for your quick scan on SUMO's utility.

      There are five parts below:
   * [car.rou.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/car.rou.xml) : Defined by user. You have to define the car flow on certain route or place in order to simulate the traffic scene.
   * [edges.edg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/edges.edg.xml) : Defined by user. To build a road net(see [road.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/road.net.xml)) , you have to define the every edge as you wish.
   * [nodes.nod.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/nodes.nod.xml) : Defined by user. To build a road net, you also have to define every node in order to connect edges together to be a map.
   * [road.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/road.net.xml) : Not defined by user, but generated by the file [edges.edg.xml] and [nodes.nod.xml]. As for the command. see and find it in [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials)
   * [cfg.sumocfg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/cfg.sumocfg.xml) : Defined by user. This file contains simulation parameters mainly for the process of entire simulation.

-  **crossroad** : Include the source code of DRL models, algorithms and environment settings.
      **IMPORTANT** : 'Traci' is the short for "Traffic Control Interface". It is a library used for the communication with SUMO based on TCP protocol in order to modify and recieve values in simulation on-line. We apply Traci here since we need to interfere with simulation procedure('Environment' in reinforcement learing) to choose actions or stop the episode('action' and 'episode' are terms in reinforcement learing). To get familiar with Traci first, you'd better check [Traci Tutorials](http://www.sumo.dlr.de/userdoc/TraCI/Protocol.html)  

      There are four parts now:  
   + Traffic map
     - [crossroad.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.net.xml) : a complete road net
     - [crossroad.rou.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.rou.xml) : a convenient way to define the motion trace of cars. See [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials)
     - [crossroad.sumocfg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.sumocfg) : As usual, the parameters file for simulation circle.
   + Deep reinforcement learning model
     - [Model.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/Model.py) : Implemented a basic DQN model based on the paper ["Human level control through deep reinforcement learning"](https://www.nature.com/articles/nature14236.pdf). This model serves as a complicated function to get policy output via image features input.
   + Environment setting
     - [Env.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/Env.py) : Implemented environment logic such as how to convert information from SUMO to the necessary states in Markov Decision Process.
   + reinforcement learning algorithm and main function for training
     - [Main.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/main.py) : Implemented Q-learning algorithm embedded in whole training procedure. You only need to execute this file to start the training.  


## (2) Reinforcement Learning Framework

### - why do I start this project?
Since it's hard for me to find a complete and feasible algorithms set on ‘Reinforcement Learning’ which is of vital help for freshers who want to get into this field.  

Nowthat I have made a detailed reading notes on the excellent book "A-introduction-to-reinforcement-learning" and implemented most of its algorithms, why not share them to public?   

I believe the quote > 'talk is cheap, show me the code'.  

### - what are in this project?  
This repository consists of the algorithms from first 9 chapters in this book: [Reinforcement Learning:An introduction --2012 version](https://files.cnblogs.com/files/lvlvlvlvlv/SuttonBook.pdf)  

![on-policy MC](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/MC_ON-POLICY_RACETRACK.png)

The algorithms after 9th chapter will be added continuously by another version of this book.  

- **chapter4** : Dynamic Programming  

  Includes two exercises:  
  1. [The Gambler](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter4/The_Gambler.py) 
  2. [Jack's Car Rental](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter4/Jack%E2%80%99s_Car_Rental.py)  

- **chapter5** : Monte Carlo Methods  

  Includes an exercise called "racetrack" and experiment performances on **racetrack**.  
  1. [Racetrack.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter5/Racetrack.py)

  **Note**:the Monte Carlo algorithms from chapter 5 are all implemented in the single file [Racetrack.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter5/Racetrack.py). Specifically in func: `def update_policy(episode):`  

- **chapter6** : Temporal-Difference Learning  

  Includes td-related algorithms and experiment performances on **racetrack**.  
  1. [td.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter6/td.py)  

  **Note**: From this chapter, I quit implementing environment of every exercise. Since almost each exercise has a different environment. If I just used different algorithms on different environments, one can hardly has a comparison between those algorithms, Therefore, I decided to show the performances of different algorithms on single same environment: **racetrack**.  

  ![naive-Q-lambda](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/naive_Q_lambda_RACETRACK.png)  

- **chapter7** : Eligibility Traces

  Includes td-lambda related algorithms and experiment performances on **racetrack**  
  1. [td_lambda.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter7/td_lambda.py)

- **chapter8** : Planning and Learning with Tabular Methods

  Includes Dyna_Q algorithm.  
  1. [Dyna_Q](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter8/Dyna_Q.py)  

- **RLF** ： An reinforcement learning algorithms library which pulls together all algorithms mentioned above and *some new deep reinforment learning algorithms like DQN or DDPG* for purpose of convenient external call.  
  **Note**: One remarkable point of this library is the seperation of *'environment'* and *'agent algorithm'* via the attribute of 'python Class'. In this way, you could add or modify your own environment without interfering agent part. Also, you can just connect agent algorithms(td,monte-carlo,dp,...) to your environment.  
  + environment code:
    - [env.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/env.py)
  + agent algorithms:  
    - [monte_carlo.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/monte_carlo.py)
    - [dp.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/dp.py)
    - [td.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/td.py)
    - [td_lambda.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/td_lambda.py)
    - [Dyna_Q.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/Dyna_Q.py)
    - [DQN.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/DQN.py)
  + main function:
    - [main.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/main.py)

## (3) Traffic Lanes Detection and Classification
### - why do I start this project?
### - what is in this project?
## (4) A Basic Fingerprint Recognition System 
### - why do I start this project?
### - what is in this project?



