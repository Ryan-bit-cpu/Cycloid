# Cycloid
The parametric plot of a wheel traveling at 2 meters/second in the xy-plane.

#Activate Qu-tip conda environment to run the code below
#Cycloid code

import numpy as np
from mpl_toolkits import mplot3d
import matplotlib.pyplot as plt
plt.style.use('seaborn-poster')

#Figure size, turn on grid, and dimensions
fig = plt.figure(figsize = (8,8))
ax = plt.axes(projection='3d')
ax.grid()

#Stating the function and domain parameters of the parametric function
v = 2			# velocity of the wheel is 2 m/s
R = 3			# the radius of the wheel is 3 m
w = v/R			# the anglar frequency in radians/second
t = np.arange(0, 10*np.pi, np.pi/50)
x = w*t - np.sin(w*t)			# The x-function of a cycloid
y = R*(1 - np.cos(w*t))			# The y-function of a cycloid

#Plotting the parametric functions
ax.plot3D(x, y, t)
ax.set_title('3D Parametric Plot of a Wheel Perfectly Rolling at constant 2 m/s')

# Set axes label
ax.set_xlabel('x (meters)', labelpad=20)
ax.set_ylabel('y (meters)', labelpad=20)
ax.set_zlabel('t (seconds)', labelpad=20)

plt.show()
