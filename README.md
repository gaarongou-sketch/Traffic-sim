Traffic Wave Simulation

This simulation models how the speed of a single vehicle affects the motion of cars further down a traffic line. The scope of the simulation is a single lane road. One vehicle, the ‘pace setter,’ is not influenced by any car in front. They are free to go as fast as the speed limit and slightly above. 
The speeds of the cars behind the pace setter are necessarily influenced by the actions of the pace setter, as well as the actions of any cars between that car and the pace setter. This has the effect of amplifying the pace setter’s actions down the line. For example, if the pace setter brakes slightly, the last car in line might be slamming on their brakes. This phenomenon is known as a traffic wave or phantom traffic jam.
Many people experience this frustration where it feels like they are driving well under the speed limit and wonder why the car in front isn’t going faster. This simulation attempts to show that the pace setter is in fact going the speed limit, but due to the effects of amplification the quality of the ride is much rougher. 

Simulation:

To make the simulation realistic but not too complex the user can adjust the following parameters: 
  -	Number of cars 
  -	Speed limit

Pace setter: 
  -	Target speed
  -	Speed variability

All other cars: 
  -	Target following distance
  -	Reaction time
  -	Max acceleration
  -	Human noise 
  -	Max allowable speed above the speed limit

The goal of the pace setter is to maintain its target speed. The goal of the following cars is to maintain their following distance by braking if they are too close and speeding up if they fall behind. Each car adjusts acceleration based on the difference between its current distance and target following distance, with a delay defined by reaction time. The braking is prioritized more, as avoiding a collision is more important than catching up. 
Note: Human noise introduces random variation to the target catch-up speed, simulating a human driver’s inability to perfectly control velocity.
The simulation will begin immediately when the file is opened and will run on live infinite mode unless changed. Press the “pause” button to stop the simulation, and “reset” to restart it. 

The display features the settings on the left, a visual display of cars on the upper right, and a plot of the car’s velocities on the middle right. Some statistics and data for the course of the simulation are on the bottom right. 

Settings: 

The first two sliders in the settings change the simulation speed and duration. By default the simulation runs at live speed for infinite, but for data collection the speed can be increased up to 100x and the duration set to 30 mins. 
Next are the settings for the pace setter, which can either be on cruise control (a constant speed) or with human error (there will be variability in their speed). 

Display: 

The “follow pace/mid/last” buttons lock the viewpoint on each car respectively, allowing the user to observe the system from different positions. Click the “show all cars” button to display the graph of every car’s velocity. Since that can be overwhelming and hard to distinguish, they are not shown by default. 
The green slider below the graph changes the time scale that the graph shows. 
The orange slider scrubs the graph, so that after running a 30 min simulation at 100x speed, you can actually go back and see specific moments of interest. 

Data: 

The data on bottom is summarized for the pace, middle, and last cars for simplicity: 
  -	Now: Current cars’ speeds
  -	Loss: Difference between the pace setter’s and last cars’ speeds
  -	Avg: The “now” values averaged over the run
  -	Min: The lowest speed reached during the simulation
  -	∑: Standard deviation showing roughness of ride (acceleration/braking)
  -	%Sub-Limit: Percentage of time spent below the speed limit

Live usage: 

A fun way to use the simulation is in infinite/live mode, where the settings can be changed mid-run. A good way to use this is to suddenly reduce the pace setters target speed (simulating braking), then move it back up and watch how it affects the line of cars behind it. Particularly how long it takes the last car to reach the speed limit again. 

Assumptions/limitations: 

  -	All the settings for the following cars are identical, this is unrealistic as each person driving has different cars, habits, following distances, etc. 
  -	Additionally, the cars only react to the car directly in front of them. In reality, drivers take note of several cars in front of them to react quicker. 
  -	Depending on the settings, the cars can collide or even swap places. There is nothing in the code to note this, avoid it, or fix it. If position swapping          occurs, the cars eventually return to their original order.

