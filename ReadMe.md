# OVERTAKE_data

## Overview

Our dataset contains about fifteen hours of driving data, including **easy mode**, **medium mode** and **hard mode**. We record data and motion commands at 10 frames per second. The labeling contains steering angle, accelerator and brake.

## About the data

The dataset is divided into 3 folders according to task difficulty, i.e., easy, mdium and hard. Each difficulty of data is further divided into 5 csv files according to **episode**, and an episode means a process from the starting point to the end point. One single csv file contains a maximum of 300 episodes, and one difficulty of data contains nearly 1300 episodes, so there are 5 csv files in each diffculty data folder. Note that the name of csv file also incates the index range of episodes.

In each csv file, there are **29 columns** and many number of **rows**, and a row of data are sampled within one single **frame**. The first 2 columns is the episode and frame indices. That is, frames sampled in the same episode have a same episode index, and every epiode in the same difficulty of dataset has a unique episode index. Note that episodes may contain different number of frames.

The other 27 columns are the vehicles' kinematic and command data, and can be further divided into four part. The first and second part denotes the X- and Y-Axis **coordinates and speed values** of ego-vehicle and other sorrounding vehicles. The third part three columns of data stands for the **accelerator**, **braking** values and the **steering** angle of the ego-vehicle. Finally, the last part contains **distances** from the center of ego-vehicle to the left and right lane lines of the current lane and the road boundaries, respectively.

All data columns and their detailed meanings are listed below.

| Column  | Meaning |
| ------- | ------- |
| episode | index of episodes in one certain difficulty of dataset |
| frame | index of frames in one episode |
| x_ego | x position of ego-vehicle |
| x_other_1 | x position of other vehicle #1 |
| x_other_2 | x position of other vehicle #2 |
| x_other_3 | x position of other vehicle #3 |
| x_other_4 | x position of other vehicle #4 |
| y_ego | y position of ego-vehicle |
| y_other_1 | y position of other vehicle #1 |
| y_other_2 | y position of other vehicle #2 |
| y_other_3 | y position of other vehicle #3 |
| y_other_4 | y position of other vehicle #4 |
| vx_ego | velocity of ego-vehicle in the x-axis |
| vx_other_1 | velocity of other vehicle #1 in the x-axis |
| vx_other_2 | velocity of other vehicle #2 in the x-axis |
| vx_other_3 | velocity of other vehicle #3 in the x-axis |
| vx_other_4 | velocity of other vehicle #4 in the x-axis |
| vy_ego | velocity of ego-vehicle in the y-ayis |
| vy_other_1 | velocity of other vehicle #1 in the y-axis |
| vy_other_2 | velocity of other vehicle #2 in the y-axis |
| vy_other_3 | velocity of other vehicle #3 in the y-axis |
| vy_other_4 | velocity of other vehicle #4 in the y-axis |
| throttle | accelerator value of ego-vehicle |
| braking  | braking value of ego-vehicle |
| steering | steering angle of ego-vehicle |
| d_left_1 | distance to the current lane's left lane line |
| d_right_1 | distance to the current lane's right lane line |
| d_left_2 | distance to the left road boundary |
| d_right_2 | distance to the right road boundary |

## Examples

### Dataset example

This is an example of the top 10 rows in one cvs file. Note that the first column is the row indices and has no column name. The other 29 columns all have column names which indicate the meanning of each column data as metioned before.

|      | episode | frame | x_ego     | x_other_1 | x_other_2 | x_other_3  | x_other_4  | y_ego      | y_other_1  | y_other_2  | y_other_3  | y_other_4  | vx_ego        | vx_other_1 | vx_other_2 | vx_other_3    | vx_other_4 | vy_ego    | vy_other_1 | vy_other_2 | vy_other_3 | vy_other_4 | throttle | braking | steering  | d_left_1 | d_right_1 | d_left_2 | d_right_2 |
| ---- | ------- | ----- | --------- | --------- | --------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ------------- | ---------- | ---------- | ------------- | ---------- | --------- | ---------- | ---------- | ---------- | ---------- | -------- | ------- | --------- | -------- | --------- | -------- | --------- |
| 0    | 0       | 0     | -1.378816 | 43.075848 | 37.514030 | -21.242659 | -33.793720 | 207.399994 | 207.399994 | 204.199997 | 204.099991 | 203.800003 | 0.000000e+00  | 0.000000   | 0.000000   | 0.000000e+00  | 0.000000   | 0.000000  | 0.000000   | 0.000000   | 0.000000   | 0.000000   | 0.0      | 0.0     | 0.000000  | 1.599994 | 1.900006  | 5.099994 | 1.900006  |
| 1    | 0       | 1     | -1.378816 | 43.075848 | 37.514030 | -21.242659 | -33.793720 | 207.399994 | 207.399994 | 204.199997 | 204.099991 | 203.800003 | 0.000000e+00  | 0.000000   | 0.000000   | 0.000000e+00  | 0.000000   | 0.000000  | 0.000000   | 0.000000   | 0.000000   | 0.000000   | 0.0      | 1.0     | -0.800000 | 1.599994 | 1.900006  | 5.099994 | 1.900006  |
| 2    | 0       | 2     | -1.378816 | 43.075848 | 37.516048 | -21.242188 | -33.793720 | 207.399994 | 207.399994 | 204.199982 | 204.100021 | 203.800003 | 0.000000e+00  | 0.000000   | 0.039877   | -7.456872e-12 | 0.000000   | 0.000000  | 0.000000   | -0.000003  | 0.001109   | 0.000000   | 0.0      | NaN     | 0.800000  | 1.599994 | 1.900006  | 5.099994 | 1.900006  |
| 3    | 0       | 3     | -1.377847 | 43.081387 | 37.518650 | -21.240322 | -33.793350 | 207.399445 | 207.399796 | 204.200546 | 204.099854 | 203.800003 | 3.657267e-04  | -0.002114  | -0.001971  | 9.642183e-04  | 0.000000   | -0.037941 | -0.001820  | 0.001286   | -0.004583  | 0.000000   | 0.7      | 0.0     | -0.031490 | 1.599445 | 1.900555  | 5.099445 | 1.900555  |
| 4    | 0       | 4     | -1.377867 | 43.081009 | 37.518475 | -21.240503 | -33.791050 | 207.399368 | 207.399689 | 204.200424 | 204.099777 | 203.801300 | -5.397946e-08 | -0.001512  | -0.001016  | -5.815665e-04 | 0.000019   | 0.004897  | 0.001210   | -0.001752  | 0.001263   | -0.000171  | 0.7      | 0.0     | -0.215264 | 1.599368 | 1.900632  | 5.099368 | 1.900632  |
| 5    | 0       | 5     | -1.377816 | 43.080799 | 37.518440 | -21.240761 | -33.791470 | 207.398987 | 207.399628 | 204.200394 | 204.099777 | 203.800613 | -8.069370e-05 | -0.000661  | -0.000463  | -2.371819e-04 | -0.000642  | 0.009371  | 0.001019   | -0.001033  | 0.001417   | -0.000556  | 0.7      | 0.0     | -0.006196 | 1.598987 | 1.901013  | 5.098987 | 1.901013  |
| 6    | 0       | 6     | -1.377796 | 43.080723 | 37.518429 | -21.240871 | -33.791767 | 207.398987 | 207.399643 | 204.200302 | 204.099899 | 203.800308 | -4.515704e-05 | -0.000242  | -0.000166  | -9.692906e-05 | -0.000291  | 0.005386  | 0.000418   | -0.000467  | 0.000626   | -0.000237  | 0.7      | 0.0     | 0.000687  | 1.598987 | 1.901013  | 5.098987 | 1.901013  |
| 7    | 0       | 7     | -1.377786 | 43.080692 | 37.518425 | -21.240913 | -33.791897 | 207.398987 | 207.399582 | 204.200348 | 204.099854 | 203.800171 | -1.858471e-05 | -0.000087  | -0.000056  | -4.138955e-05 | -0.000123  | 0.002229  | 0.000157   | 0.000058   | -0.000028  | -0.000093  | 0.7      | 0.0     | 0.002111  | 1.598987 | 1.901013  | 5.098987 | 1.901013  |
| 8    | 0       | 8     | -1.377783 | 43.080692 | 37.518433 | -21.240925 | -33.791950 | 207.398804 | 207.399567 | 204.200363 | 204.099838 | 203.800125 | -6.908410e-06 | -0.000036  | -0.000022  | -1.640508e-05 | -0.000049  | 0.000196  | -0.000004  | 0.000030   | -0.000041  | -0.000040  | 0.7      | 0.0     | 0.002621  | 1.598804 | 1.901196  | 5.098804 | 1.901196  |
| 9    | 0       | 9     | -1.377782 | 43.080692 | 37.518433 | -21.240932 | -33.791965 | 207.398743 | 207.399567 | 204.200363 | 204.099823 | 203.800095 | -2.370085e-06 | -0.000020  | -0.000013  | -6.677407e-06 | -0.000017  | 0.000040  | -0.000002  | 0.000012   | -0.000017  | -0.000039  | 0.7      | 0.0     | 0.002692  | 1.598743 | 1.901257  | 5.098743 | 1.901257  |


### Overtaking example
This is an example of ego-vehicle(blue) overtaking other vehicle(orange) in our dataset, captured in the CARLA simulator.
<img src="overtake.gif"/>
