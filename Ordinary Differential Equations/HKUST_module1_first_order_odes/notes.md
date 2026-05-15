## First order ordinary differential equations

**Course: HKUST Differential equations for engineers**

**Module: 1**

**Date completed: 15/05/26**

*Caution: These notes are meant to be for revision after learning the subject , not as a method for teaching oneself the subject*

## Introduction

#### Q: What are differential equations?

Differential equations are any equations that involve an infinitesimal rate of change in one of their sides, they're like ordinary algebraic equations but they contain a derivative which is what makes it tricky. A usual algebraic equation for say interest rate would be something like this   $ A = \left(1 + \frac{r}{100}\right)^t \times \text{initial amount} $  while a differential equation would basically involve taking the $t$ to the limit and assuming that compounding was continuous and get   $\frac{dA}{dt} = rA$  which could then be simplified to get the formula for $A(t)$.

#### Classification of differential equations

We classify the equations on three axes

+ Ordinary Vs Partial $\frac{dV}{dt} ; \text{vs} ; \frac{\partial V}{\partial t}$

+ Degree of the equation - basically the highest differential power present in the equation

+ Linear Vs nonlinear - If there exists higher powers of the dependent variable or the dependent variable is present in non linear functions such as $ e^v ,\sin v,\cos v $ etc

###### Examples:

$\frac{d^2y}{dt^2} + \sin (t+y) = \sin t$ : Ordinary, Second degree, nonlinear

$\frac{\partial^3 y}{\partial t^3} + \frac{\partial^2 y}{\partial t^2} + \frac{\partial y}{\partial t}=1$ : Partial, Third degree, linear

## Numerical Solutions of differential equations

#### Euler's method (first order)

Intuition: Simply continue the differential equation since we know the slope from the formula itself and all we need is an accurate point to start (IVP)

working:

1. Choose step value $\Delta x$

2. Now calculate slope $\frac{dy}{dx}=f(x_n,y_n)$ based on IVP $y(x_n)=y_n$

3. Now since slope = $\frac{\Delta y}{\Delta x}$ therefore multiplying it with $\Delta x$ will give $\Delta y$

4. So new values are $x_{n+1}=x_n +\Delta x$ & $y_{n+1}=y_n+\Delta x , f(x_n,y_n)$

#### Midpoint method

Intuition: the middle value of $x$ will yield the most accurate value for slope, since slope is continuously changing

working:

1. Choose $\Delta x$

2. Calculate $x_{n+1}, y_{n+1}$ as usual

3. Now calculate new $\Delta y_{\text{new}} = \Delta x , f\left(x_n +\frac{\Delta x}{2}, ; y_n+\frac{\Delta y}{2} \right) $

4. $x_{n+1} ; \text{remains the same only } ; y_{n+1}=y_n+\Delta y_{\text{new}}$

#### Runge-Kutta 2

Intuition: It basically calculates the average of the start slope and end slope, and uses that to update the value of $y$

###### Example Euler's method:

Use Euler’s method to estimate the value at $x = 1.5$ of the solution of  
$\frac {dy}{dx}= F(x, y) = y^2 - x^2 ; \text{for which} ; y(0) = -1$. Use step size $h = 0.5$ *(From MIT OCW 18.03sc Numerical methods module)*

Step Size ( $\Delta x$ ): $0.5$ , Differential Equation: $\frac{dy}{dx} = y^2 - x^2 $ , Initial Point: $y(0) = -1$ 

| **#** | **x** | **y**  | **Slope ($y^2-x^2$)**               | **$\Delta y=\Delta x\cdot \text{Slope}$** |
| ----- | ----- | ------ | ----------------------------------- | ----------------------------------------- |
| **1** | 0     | -1     | $(-1)^2 - 0^2 = \mathbf{1}$         | $0.5 \times 1 = \mathbf{0.5}$             |
| **2** | 0.5   | -0.5   | $(-0.5)^2 - (0.5)^2 = \mathbf{0}$   | $0.5 \times 0 = \mathbf{0}$               |
| **3** | 1     | -0.5   | $(-0.5)^2 - (1)^2 = \mathbf{-0.75}$ | $0.5 \times -0.75 = \mathbf{-0.375}$      |
| **4** | 1.5   | -0.875 | —                                   | —                                         |

## Solving ODEs by separation of variables:

if the differential equation can be decomposed from $ \frac{dy}{dx}=f(x,y)$ to a form of $ f(y) , dy = f(x) , dx$ then we can simply integrate both the sides for an answer as

$\int_{y_0}^y f(s), ds=\int_{x_0}^x f(t), dt$

###### Example

$y'=\frac{2-e^x}{3+2y}, \quad y(0)=0$

$\int_{0}^y (3+2s), ds=\int_{0}^x (2-e^t), dt$

$3y+y^2 |_{0}^y=2x-e^x |_0^x$

$3y+y^2=2x-e^x$

This is a quadratic in $y$ so we get

$y(x) = \frac{-3 + \sqrt {13+8x-4e^x}}{2}$

## Solving Linear ODEs using Integrating factor

We need to find an integrating factor $\mu(x)$ such that multiplying both sides of the equation by it makes the equation integrable.

###### Steps:

1. Arrange in the form $y'+p(x)y=q(x)$

2. multiply **both** sides of the equation with IF

3. Integrate and rearrange to obtain $y$

###### Example

$(1+x^2)y'+2xy=2x ; \text{with} ; y(0)=0$

$\text{rearranging we get } y'+\frac{2x}{1+x^2}y=\frac{2x}{1+x^2}$

$\mu(x) = e^{\int \frac{2x}{1+x^2} , dx}$

$\frac{d}{dx}\ln(1+x^2) = \frac{2x}{1+x^2}$

$\text{Therefore } \mu(x) = e^{\ln(1+x^2)}=1+x^2$

$\text{Multiplying both sides by } (1+x^2) \text{ we get } \frac{d}{dx}\big((1+x^2)y\big) =2x$

$\text{Integrating } (1+x^2)y= x^2$

$y=\frac{x^2}{1+x^2}$

## Applying ODEs

#### Q Continuously compounding interest

**a)** A man has some money in the bank account, he gains interest on the money compounded continuously at rate *r* per year and he deposits money continuously at a rate *k* per year, what is the function for the amount of money he has in the bank account at time $t$.

*Note: It doesn't have any effect on the equations final form whatever units you choose initially but they must be consistent*

**b)** If he has a starting deposit of 10,000, interest is 2% a year and adds money at a rate of 1000 a year, how much time will it take for him to have 100,000 in his account

$\text{Let } A(t) \text{ be the amount in the account. The model is } \frac{dA}{dt} = rA + k$

$\frac{dA}{dt} - rA = k$

$\text{Integrating factor: } e^{-rt}$

$e^{-rt}\frac{dA}{dt} - r e^{-rt}A = k e^{-rt}$

$\frac{d}{dt}(A e^{-rt}) = k e^{-rt}$

$A e^{-rt} = \int k e^{-rt} , dt$

$A e^{-rt} = -\frac{k}{r} e^{-rt} + C$

$A(t) = C e^{rt} - \frac{k}{r}$

$\text{Using } A(0) = A_0: \quad A_0 = C - \frac{k}{r}$

$C = A_0 + \frac{k}{r}$

$A(t) = \left(A_0 + \frac{k}{r}\right)e^{rt} - \frac{k}{r}$

$\text{Substitute } A_0 = 10000,\ r = 0.02,\ k = 1000$

$\frac{k}{r} = 50000$

$A(t) = 60000 e^{0.02t} - 50000$

$\text{Set } A(t) = 100000$

$60000 e^{0.02t} - 50000 = 100000$

$60000 e^{0.02t} = 150000$

$e^{0.02t} = 2.5$

$0.02t = \ln(2.5)$

$t = \frac{\ln(2.5)}{0.02}$

$t = 50 \ln(2.5)$

$t \approx 45.8 \text{ years}$
