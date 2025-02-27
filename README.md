Download link :https://programming.engineering/product/optimal-control-20-points/

# Optimal-Control-20-Points-
Optimal Control [20 Points]
Name, Surname, ID Number

Problem 2.1 Optimal Control [20 Points]

In this exercise, we consider a finite-horizon discrete time-varying Stochastic Linear Quadratic Regulator with Gaussian noise and time-varying quadratic reward function. Such system is defined as

s t+1 = At s t + Bt at + w t ,

(1)

where s

is the state, a

is the control signal, w

b ,

is Gaussian additive noise with mean b

and covariance

t and tt

= 0, 1, . . . , T ist

the time horizon. The controltN

signaltt at is computed as

t

at = K t s t + kt

(2)

and the reward function is

r ewar dt = ¤

(s t

r t )T Rt (s t

r t )

t

when

t = T

(3)

(s t

r t )T Rt (s t

r t )

aTH t at

when

t = 0, 1, . . . , T

1

Implementation [8 Points]

Implement the LQR with the following properties

1

T =

s0 N 0, I

50

At = 0

1

Bt =

0.1

bt = 0

0.1

0

0.01

t =

0

5

0.01

0

K t = 5 0.3

kt =

0.3

0

0.1

if t = 14 or 40

8

0

if

t = 0, 1, . . . , 14

8

H t = 1

Rt =

>

100000

0

r t =

>

10

>

>

>

0

0.1

>

0

>

0.01

0

otherwise

>

20

if

t = 15, 16, . . . , T

<

<

>

>

>

>

:

:

Execute the system 20 times. Plot the mean and 95% confidence (see “68–95–99.7 rule” and mat-plotlib.pyplot.fill_between function) over the diﬀerent experiments of the state s t and of the control signal

t over time. How does the system behave? Compute and write down the mean and the standard deviation of the cumulative reward over the experiments. Attach a snippet of your code.

Name, Surname, ID Number

LQR as a P controller [4 Points]

The LQR can also be seen as a simple P controller of the form

at = K t sdest s t + kt , (4)

which corresponds to the controller used in the canonical LQR system with the introduction of the target sdest. Assume as target

8

10

if

t = 0, 1, . . . , 14

>

>

>

0

s t = r

t = <

if

t = 15, 16, . . . , T

(5)

20

des

>

>

>

0

Use the same LQR system as in the previous exercise and run 20 experiments. Plot in one figure the mean

and 95% confidence (see “68–95–99.7 rule” and matplotlib.pyplot.fill_between function) of the first dimension of the state, for both sdest = r t and sdest = 0.

Name, Surname, ID Number

Optimal LQR [8 Points]

To compute the optimal gains K t and k t , which maximize the cumulative reward, we can use an analytic optimal solution. This controller recursively computes the optimal action by

at = H t + BTt V t+1 Bt 1 BTt (V t+1 (At s t + bt ) v t+1) ,

(6)

which can be decomposed into

