---
layout: default
---

# Welcome to Xubo's Projects!

Here I listed basic instructions of my research projects deposited at GitHub.

## (1) Robotics-Navigation-Deep-Reinforcement-Learning

[See it at GitHub](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning)

### why do I start this project?

Even though it's easy for human to make successive decisions for vehicle in complicated driving conditions, it's even harder than our imagination for self-driving cars to decide how to pass these areas automatically. However, reinforcement learning methods have been designed to deal with continuous decision problem. Therefore, I'm considering and trying to apply deep reinforcement learning algorithms to the self-driving simulated model, to see if there are any improvement on automatic navigation at complicated traffic scenes.

### what is in this project?

Currently, I am trying to apply deep-Q-network and DDPG algorithms on different agent navigation scenarios(mainly crossroads) in simulation environment(SUMO) to see if the DRL methods could improve efficiency and safety in complicated navigation tasks. I also want to check whether there are some ways to transfer the trained model to real world tasks. 

![simulation](https://farm5.staticflickr.com/4635/39490314751_d95eedb46a_m.jpg) 

-   **basic** : Include the elementary parts of a 'SUMO' map 

    > **IMPORTANT**: SUMO is the short of "Simulation of Urban Mobility". It is a software which help you creat any kinds of traffic simulation scenes quickly. 
    > **IMPORTANT**: You'd better read the tutorials of SUMO first in order to understand the content below. Tutorials are here: [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials).Apart from that, the blog is great for your quick scan on SUMO's utility. 

    There are five parts below:

    - [car.rou.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/car.rou.xml) : Defined by user. You have to define the car flow on certain route or place in order to simulate the traffic scene.
    - [edges.edg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/edges.edg.xml) : Defined by user. To build a road net(see [road.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/road.net.xml)) , you have to define the every edge as you wish.
    - [nodes.nod.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/nodes.nod.xml) : Defined by user. To build a road net, you also have to define every node in order to connect edges together to be a map.
    - [road.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/road.net.xml) : Not defined by user, but generated by the file [edges.edg.xml] and [nodes.nod.xml]. As for the command. see and find it in [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials)
    - [cfg.sumocfg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/basic/cfg.sumocfg.xml) : Defined by user. This file contains simulation parameters mainly for the process of entire simulation.



-   **crossroad** : Include the source code of DRL models, algorithms and environment settings.

    > **IMPORTANT** : 'Traci' is the short for "Traffic Control Interface". It is a library used for the communication with SUMO based on TCP protocol in order to modify and recieve values in simulation on-line. We apply Traci here since we need to interfere with simulation procedure('Environment' in reinforcement learing) to choose actions or stop the episode('action' and 'episode' are terms in reinforcement learing). To get familiar with Traci first, you'd better check [Traci Tutorials](http://www.sumo.dlr.de/userdoc/TraCI/Protocol.html)  

    There are four parts now:  

    - Traffic map
      - [crossroad.net.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.net.xml) : a complete road net
      - [crossroad.rou.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.rou.xml) : a convenient way to define the motion trace of cars. See [SUMO TUTORIALS](http://sumo.dlr.de/wiki/Tutorials)
      - [crossroad.sumocfg.xml](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/crossroad.sumocfg) : As usual, the parameters file for simulation circle.
    - Deep reinforcement learning model
      - [Model.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/Model.py) : Implemented a basic DQN model based on the paper ["Human level control through deep reinforcement learning"](https://www.nature.com/articles/nature14236.pdf). This model serves as a complicated function to get policy output via image features input.
    - Environment setting
      - [Env.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/Env.py) : Implemented environment logic such as how to convert information from SUMO to the necessary states in Markov Decision Process.
    - reinforcement learning algorithm and main function for training
      - [Main.py](https://github.com/lvlvlvlvlv/Robotics-Navigation-Deep-Reinforcement-Learning/blob/master/crossroad/main.py) : Implemented Q-learning algorithm embedded in whole training procedure. You only need to execute this file to start the training.  

## (2) Reinforcement Learning Framework

[See it at GitHub](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning)

### why do I start this project?

Since it's hard for me to find a complete and feasible algorithms set on ‘Reinforcement Learning’ which is of vital help for freshers who want to get into this field.  

Nowthat I have made a detailed reading notes on the excellent book "A-introduction-to-reinforcement-learning" and implemented most of its algorithms, why not share them to public?   

I believe the quote > 'talk is cheap, show me the code'.  

### what are in this project?

This repository consists of the algorithms from first 9 chapters in this book: [Reinforcement Learning:An introduction --2012 version](https://files.cnblogs.com/files/lvlvlvlvlv/SuttonBook.pdf)  

![on-policy MC](https://farm5.staticflickr.com/4590/39490314591_0a9ec90de8_m.jpg)

The algorithms after 9th chapter will be added continuously by another version of this book.  

- **chapter4** : Dynamic Programming  

  Includes two exercises:

  - [The Gambler](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter4/The_Gambler.py) 
  - [Jack's Car Rental](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter4/Jack%E2%80%99s_Car_Rental.py)  


- **chapter5** : Monte Carlo Methods  

  Includes an exercise called "racetrack" and experiment performances on **racetrack**.  

  - [Racetrack.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter5/Racetrack.py)

    **Note**:the Monte Carlo algorithms from chapter 5 are all implemented in the single file [Racetrack.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter5/Racetrack.py). Specifically in func:```def update_policy(episode)```

- **chapter6** : Temporal-Difference Learning  

  Includes td-related algorithms and experiment performances on **racetrack**.  

  - [td.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter6/td.py)  

  **Note**: From this chapter, I quit implementing environment of every exercise. Since almost each exercise has a different environment. If I just used different algorithms on different environments, one can hardly has a comparison between those algorithms, Therefore, I decided to show the performances of different algorithms on single same environment: **racetrack**.  

  ![naive-Q-lambda](https://farm5.staticflickr.com/4590/39490314591_0a9ec90de8_m.jpg)  

- **chapter7** : Eligibility Traces

  Includes td-lambda related algorithms and experiment performances on **racetrack**  

  - [td_lambda.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter7/td_lambda.py)

- **chapter8** : Planning and Learning with Tabular Methods

  Includes Dyna_Q algorithm.  

  - [Dyna_Q](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/chapter8/Dyna_Q.py)  

- **RLF** ： An reinforcement learning algorithms library which pulls together all algorithms mentioned above and *some new deep reinforment learning algorithms like DQN or DDPG* for purpose of convenient external call.  
  **Note**: One remarkable point of this library is the seperation of *'environment'* and *'agent algorithm'* via the attribute of 'python Class'. In this way, you could add or modify your own environment without interfering agent part. Also, you can just connect agent algorithms(td,monte-carlo,dp,...) to your environment.  

  - environment code:
    - [env.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/env.py)
  - agent algorithms:  
    - [monte_carlo.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/monte_carlo.py)
    - [dp.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/dp.py)
    - [td.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/td.py)
    - [td_lambda.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/td_lambda.py)
    - [Dyna_Q.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/Dyna_Q.py)
    - [DQN.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/DQN.py)
  - main function:
    - [main.py](https://github.com/lvlvlvlvlv/A-introduction-to-reinforcement-learning/blob/master/RLF/main.py)

## (3) Traffic Lanes Detection and Classification

[See it at GitHub](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification)

### 	why do I start this project?

For self-driving vehicle, it's very important to recognize traffic lanes precisely. Therefore, I conducted this project for finding more compact and effective features of grayscale road map using C++, OpenCV and Random-Forest/SVM model to improve detection accuracy of traffic lanes. 

### 	what is in this project?

![performance](http://farm5.staticflickr.com/4686/38681320945_8c10dfd986_b.jpg)

+ features:
  + [trainFeaturesMat-sample.txt](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/features/trainFeaturesMat-sample.txt)
  + [trainLablesMat.txt](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/features/trainLablesMat.txt)
  + [testFeaturesMat-sample.txt](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/features/testFeaturesMat-sample.txt)
  + [testLabelsMat.txt](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/features/testLabelsMat.txt)
+ lib:
  + [SWT.lib](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/lib/SWT.lib)
  + [libadas.lib](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/lib/libadas.lib)
  + [opencv_calib3d300d.dll](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/lib/opencv_calib3d300d.dll) ~ [opencv_videoio300d.dll](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/lib/opencv_videoio300d.dll)
  + [vl.dll](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/lib/vl.dll)
+ model
  + [SVM_Model.xml](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/model/SVM_Model.xml)
  + [rtrees_1.xml](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/model/rtrees_1.xml)
  + [rtrees_2.xml](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/model/rtrees_2.xml)


+ source
  + [SWT.sln](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/SWT.sln)
  + [SimpleIni.h](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/SimpleIni.h)
  + [simpleiniext.h](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/simpleiniext.h)
  + [main.cpp](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/main.cpp)
  + [contours.h](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/contours.h)
  + [Camera.h](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/Camera.h)
  + [config.ini](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/config.ini)
  + [standard_setting.ini](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/source/standard_setting.ini)
+ yml 
  + [OV10635_20160518_1547_lane.yml](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/yml/OV10635_20160518_1547_lane.yml)
  + [config_OV10635_20160518_1547.yml](https://github.com/lvlvlvlvlv/Traffic-Lanes-Detection-and-Classification/blob/master/yml/config_OV10635_20160518_1547.yml)

## (4) A Basic Fingerprint Recognition System

[See it at GitHub](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System)

### 	why do I start this project?

This project derived from my undergraduate period. I started it since I had seen a few fingerprint scanners for security check and I was curious to know the entire technical principles of fingerprint recognition system. So, I implemented all necessary image-processing algorithms without resorting to any external functions to form a basic demo using Python.

### 	what is in this project?

+ [Comparison.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Comparison.py)

  The main function of this file is to compare two fingerprint pictures based on thinned image and valid feature points. Please refer to ```def Compare()```

+ [Freq.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Freq.py)

  The main function of this file is to compute the corresponding frquency field image based on original fingerprint image and direction field image.

  What is frequency? In the direction perpendicular to the ridge line, the image grayscale distribution is approximated to a sine wave. So we refer the frequency of this sine wave as the frequency of a series of ridge lines.

+ [GUI.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/GUI.py)

  This is the final GUI of the fingerprint system software.

+ [Gabor.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Gabor.py)

+ [GetMinutia.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/GetMinutia.py)

+ [Match.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Match.py)

+ [Preprocess.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Preprocess.py)

+ [Preprocess.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Preprocess.py)

+ [Thin.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/Thin.py)

+ [beginning.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/beginning.py)

+ [feature.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/feature.py)

+ [function.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/function.py)

+ [orientation.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/orientation.py)

+ [segment_first.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/segment_first.py)

+ [segment_second.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/segment_second.py)

+ [segment_final.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/segment_final.py)

+ [segment_test.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/segment_test.py)

+ [supercore.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/supercore.py)

+ [temp.py](https://github.com/lvlvlvlvlv/Fingerprint-Recognition-System/blob/master/temp.py)