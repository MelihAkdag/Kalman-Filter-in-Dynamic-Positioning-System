# Kalman Filter Application in Dynamic Positioning System
My main goal of this study is to understand how to apply kalman filter by using Python. I wanted to choose an example from a real life scenerio. As I had experience working onboard a ship with Dynamic Positioning (DP) system, I knew that kalman filter is widely used in the system.

Before starting the study, I should explain what is the Dynamic Positioning System and how is the kalman filter used in DP systems.

Especially in the offshore industry, DP system is widely used to automatically maintain a marine platform's (either a ship or an offshore platform) position, heading (yaw angle), follow survey routes, conduct berthing or docking maneavours. These platforms have multiple thrusters (propellers) and multiple sensors (GPS, wind, current, IMU sensors, acoustic transponders, laser rangefinders etc).

For a position keeping scenario, imagine the platform is on the location where we want to keep her position. One can measure her position from multiple GPS sensors. And if acoustic transponders are used, one can also see the relative position of the platform from these transponders. In reality, sensor data can be noisy and unstable. At the same time external forces like wind or current speed and direction can change over time. External forces can cause a drift in the platform's position. Every time the position information changes, the DP system commands thrusters to get the platform back into her desired position. If the system uses these unstable and noisy data, it can command thrusters unnecessarily and this can cause more of a position drift. Kalman filter is used to in order to discard these noisy data and estimate a stable position information. For more information about the kalman filter and it's use in DP system, I would recommend you to check resources at the end of this study.

In reality, DP system configuration is much more complex than this definition of mine, but I wanted to explain the basics of the procedure. In order to simplfy the problem, I didn't use velocity, accelaration, wind, current data. I used only position data (x and y axes). And I followed these steps:

1. Defining number of steps (or time period).
2. Defining actual (physical) position of the ship. In order to simplfy the study x and y axes are used instead of geographic coordinates.
3. Creating imaginary, noisy position measuremants with the same number of steps.
4. Creating empty arrays to save calculated measurements after kalman filter is applied.
5. Defining related matrices for mathematical calculations.
6. Conducting calculations and saving measurements.
7. Visualising the actual, noisy measurements and estimated positions.
