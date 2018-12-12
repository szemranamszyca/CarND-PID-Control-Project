# Controls PID
Self-Driving Car Engineer Nanodegree Program
Extended Kalman Filter

This project contains an implementation of PID Controller and a short description of its parts.
---

## PID Control

PID is a simple, widely used controller. Difference between measured and desired value is fed into PID controller as an error.  A car simulator, in this project, generates error signal as the distance between actual car position and reference trajectory called cross-track error (CTE). The goal of PID controller is to minimiaze that distance. In this project, steering angle is under PID control.

### P - proportional gain

Output of proportional gain is... propotional to the cross-track error. Pure P is unstable and at best oscillates around target.
### D - differential gain

Oscillation observed at pure P controller could be reduced by differential gain to help covergance to set value.

### I - integral gain

If there's a constant system error (e.g. our steering wheel is fixed at some non-zero position) it could be reduced by using integral gain in PID controller, which simply sums up the cross-track error over time.


## Hyperparameter Tuning

Parameters were chosen manually. There's no Integral Gain (=0). With pure P, the car bounces to the left and to the right on the track. I've chosen quite small P gain (=.15) and tried to reduced oscillation with D parameter, which finally is set to 3. That allowed me to pass one lap without any problems.
