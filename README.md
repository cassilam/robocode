# robocode

A Robocode project for California State Polytechnic University, Pomona's CS 141 course
Team Members: Cassi Lam, Joanna Cao

Essentially, what we wanted our robot Virr to do was be a dodging bot that only moved minimally so as to avoid bullets, while preventing certain types of targeting such as predictive targeting and circular targeting from hitting our bot as well. Virr would then fire a bullet back at the bot that it scanned after it dodges. Virr also avoid walls by checking its distance from walls. This is necessarily because running into walls causes loss in power and the possibility of it getting stuck.

Going deeper into the code, we started off by having our bot inherit from the AdvancedRobot class, which allows non-blocking calls and custom events, rather than the typical Robot class so that we’d have more options for our movement. In the main method (the run method), we set Virr’s gun to turn right by 99,999 degrees and then left for 99,999 degrees to scan for robots. When another robot is scanned and detected, Virr will turn to stay at right angles to the enemy robot to make it easier to move out of the way of incoming bullets. If it detects a change in energy, it assumes the opponent has fired and moves forward to dodge the bullet and fires a bullet at the enemy after scanning. Then it updates the value of the enemy’s energy level.

If Virr detects a wall 45 pixels ahead of it, it will turn left by 45 degrees to avoid hitting the wall since it would cause a loss of energy and grants the possibility of getting stuck. Robocode uses the Cartesian coordinate system, so the bottom left corner of the battlefield locates the coordinate (0,0). When Virr gets hit by a bullet, it turns its gun to the direction of where the bullet came from and fires a shot before turning right and moves forward in that direction. If Virr collides with a robot, it uses the isMyFault method to check if it was moving towards the robot that was hit, and if it returns true, Virr moves backwards by 200 pixels. Otherwise, it would fire a bullet towards the enemy robot.

How to Implement Virr robot:
Download and install Robocode from this link: https://sourceforge.net/projects/robocode/ Download and extract Virr robot from our GitHub repository: https://github.com/cassilam/robocode
Navigate a Finder/Explorer window to C:\robocode\robots
Drag the “jhcao_cassilam” folder from the folder you downloaded from GitHub to the robots folder
You should now be able to use Virr in a battle

