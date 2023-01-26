# Line-Follower

Line follower robot developed within the "Introduction to Robotics" course, 3rd year, 1st semester.   

Our team "Vecchia Roma" composed of Călin Cruceanu ([his repo](https://github.com/TheGladja/Robotics-Line-Follower)) and me had to build a functional line follower from scratch.  

:camera: Picture of the setup (without the battery):     
   
<img src="./Setup.jpeg" width=70% height=70%>

:hammer_and_wrench: Components:   
1. Arduino Uno  
2. Zip-ties  
3. Power source (can be of different shape). In my case, a LiPo battery 
4. Wheels (2)  
5. Wires for the line sensor (female - male)  
6. QTR-8A reflectance sensor (out of which we used only 6), along with screws
7. Ball caster  
8. Extra wires from the kit or lab  
9. Chassis10.Breadboard - medium (400pts)  
11. L293D motor driver  
12. DC motors (2)


🔶 Context:   
&emsp; We received the kit for the line follower and had to assemble it in a laboratory.
The more interesting part is that we had to write the actual code for it in less than 12 hours (an experience similar to a hackaton) and test it as well using some hand-made routes (with white paper and black tape).


💠 Technical Task:   
&emsp; Build a line follower robot that has to finish a given route as quick as possible, using a **PID controller**.
Before the robot starts to follow the black line, it has to **auto calibrate**, meaning moving to the left and right to distinguish between different colors by using the sensors attached.    
&emsp; Also it is important to follow the black line no matter what (for example even if there are 2 close curves). It is already known there will be no intersections.   

&emsp; **What we did**: We had an empirical approach, in order to find the best kp, kd, ki values for our robot. We started with fine tuning the kp parameter and after being comfortable with the result, we moved to the kd one. There, we adjusted the smoothness in movements. Finally, we added just a little improvement by setting the ki value to a really small one, to act as a *learning rate*.  Undoubtedly this process took many tries, but we chose the *trial and error* strategy.   


:thinking: Challenges encountered:
- Calibration: We had to use millis() while calibrating the robot. Also, the motors didn't move the same, meaning they didn't have the same power when given a specific speed, so we had to try different cases to find a good balance. In the end we chose to read values from the sensors and move to left and right accordingly, so that the robot's sensors would detect plain white and plain black too.  
- PID controller: We had to fine tune the kp, kd, ki values from the PID controller (as well as other ones) in order to find a good combination for our robot.
- Hardware: Powering the robot required a lot of attention, because we used LiPo batteries.


🔶 Other details:  
Coding style is important.  
Magic numbers are not accepted and consistentency in style is desired.

**In the end, we managed to get an approximate finish time of 21 seconds.**

:film_projector: [Video showcasing the functionality](https://www.youtube.com/shorts/8KyZO9jaVYE)   
