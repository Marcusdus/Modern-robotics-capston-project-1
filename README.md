# Modern-robotics-capston-project-1


This project is to write software to control a mobile manipulator to pick up a block, carry it to a new configuration, and put it down.  To achieve this, our software will plan a multi-segment trajectory for the end-effector of the mobile manipulator; implement a feedback controller to drive the wheels and arm joints of the mobile manipulator; and simulate the mobile manipulator's motion given the wheel and joint velocities calculated by your controller.  This simulator will use odometry to simulate the motion of the chassis.


Description


To animate the bot, add config.csv to hbox in V-REP GUI. To generate the csv file, we need to run main.py. The parameters required for the python file are as listed above. Some of the notable details are as follows:

1. There is a speed limit check for velocity of both wheels and joints in simulate.py. The parameter to set the limit can be found in bot_params.yaml.

2. testJointLimits is also implemented in feedback_controller.py to ensure that the joints after timestep and the given joint speeds do not violate the joint limits. For this the violating joint limits are noted and their corresponding column in the Je matrix is set to zero so as to ensure that the constraint joint do not contribute further to achieve the desired configuration.

3. In order to avoid singularity, the pseudo jacobian inverse is given a tolerance of 1e-3

4. Also provision to change the time scaling and trajectory type is also added in parameters in config folder
