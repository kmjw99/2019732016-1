# 2019732016-김종완
제어공학 5주차 1차시 내용 정리

state variable models
-> 컴퓨터에게 쉽게 일을 맡기도록 바꾸어 나가는 과정
inputs -> system -> outputs
시스템 안에 의미있는 state를 정의하자 -> state variable model의 핵심

Example 1) spring-mass-damper system
M*d^2y(t)/dt^2 + b*dy(t)/dt + k*y(t) = r(t)
x1(t) = y(t), x2(t) = dy(t)/dt
dx1(t)/dt = x2(t), y(t) = x1(t)
dx2(t)/dt = -b/M*x2(t) - k/M*x1(t) + 1/M*r(t)
2차미분방정식을 1차미분방정식 2개로 바꿈

Example 2) R-L-C circuit system
x1 = Vc(t), x2(t) = iL(t)
By KCL -> u(t) = C*dx1(t)/dt + x2(t) -> dx1(t)/dt = 1/C[-x2(t)+u(t)]
By KVL -> Lx2(t)/dt + Rx2(t) - x1(t) = 0 -> x2(t)/dt = 1/L[x1(t)-R*x2(t)]
dx1(t)/dt = 1/C[-x2(t)+u(t)], y(t)=R*x2(t), dx2(t)/dt = 1/L[x1(t)-R*x2(t)]

state space equation(상태공간방정식)
<1차 상태미분방정식>
x'(t) = ax(t) + bu(t)
SX(s)-x(0) = aX(s) + bU(s)
(s-a)X(s) =  x(0) + bU(s)
x(t) = Φ(t) * x(0) + ∫Φ(t-λ)bu(λ)dt

<state vector and state space equation>
state vector 설정 -> state space equation, state differential equation

<Example 3.1>
M1*p''(t) = u(t) - b1[p'(t)-q'(t)]-k1[p(t)-q(t)]
M2*q''(t)=b1[p'(t)-q'(t)]+k1[p(t)-q(t)]-b2q'(t)-k2q(t)
y(t)=p(t), u(t)=0이라 가정하고 Matlab
