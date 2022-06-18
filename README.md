# MountainCarContinuous-v0-by-fuzzy-controller
(You may have trouble running this issue in Colab and running the graphical environment. Run it on your local system and in the Jupyter Notebook for convenience.)

<img src='https://github.com/zahrasa/MountainCarContinuous-v0-by-fuzzy-controller/blob/main/img/MountainCarContinuousv0.png' alt='car' width=400px>

<img src='https://github.com/zahrasa/MountainCarContinuous-v0-by-fuzzy-controller/blob/main/img/force.png' alt='force' width=400px>
<img src='https://github.com/zahrasa/MountainCarContinuous-v0-by-fuzzy-controller/blob/main/img/position.png' alt='position' width=400px>
<img src='https://github.com/zahrasa/MountainCarContinuous-v0-by-fuzzy-controller/blob/main/img/speed.png' alt='speed' width=400px>

The aim of this project was to get acquainted with the implementation of a complex control system. We used the MountainCarContinuous-v0 environment here. For more information about this environment, refer to the following link:
https://gym.openai.com/envs/MountainCarContinuous-v0

This environment is a graphical environment in which a one-dimensional car is located between two hills. The goal is to reach the top of the hill on the right, but its engine is not strong enough to do it at once. Therefore, we have to move the car back and forth so that the car reaches the top of the hill on the right.

As mentioned, the goal is to control the car with a fuzzy system to reach the top of the hill on the right.
The car has two features in each state. The first feature is the location of the car, which varies from -1.2 to 0.6.
The second feature is the car speed, which varies from -0.07 to 0.07. These two state attributes represent the car at each step. The goal is to place the car more than 0.45.

In each step, an Action must be selected according to the state in which it is located. Action Here is a number between -1 to +1, which is the amount of force that will enter the car. The choice of this action should be based on a fuzzy control system. To design this system, the following steps must be followed:

- We will use the scikit-fuzzy library to design this fuzzy control system.
- The inputs here is the location and speed of the car. We need to define fuzzy intervals for these two inputs. Also, the output here is the force on the car, which is Action, for which we must define and implement intervals, too.
- In the next part, based on the inputs and outputs, rules should be designed that can take the car to the top of the hill on the right. These rules are implemented using the scikit- fuzzy library.
Finally, the implemented system must be used to select Action to control the car in a graphical environment.
- We have two conditions for termination. First, the car has reached the desired goal. Second, the number of steps has reached 500. This means that the designed system must reach its goal before 500 stages of the car and is not allowed to use more stages.

In general, to solve this question, you must go through the following steps:
1 - First run the desired graphical environment.
2 - Define and implement the said language variables.
3 - To achieve the goal and according to the language variables define the rules and implement them.
4 - In the implementation loop related to the car control, make a decision at each stage according to the state and using the implemented control system.
5 - Apply your decision on the environment and see the result.
6 - If the car does not reach the desired goal and the number of steps is less than 500, go to step 4.
7 - Finally, show a graph of the rewards received in different stages.
