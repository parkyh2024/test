#**제어공학1 6주차 과제 (Chapter 3)**  
2019732035 이의주
***
P3.1  
(a)  
$$x_1(t)=y(t)$$  
$$x_2(t)=\frac{dy(t)}{dt}$$  
(b)  
$$M\frac{d^2y(t)}{dt^2}+b\frac{dy(t)}{dt}+ky(t)=F(t)$$  
$$M\frac{dx_2(t)}{dt}+bx_2(t)+kx_1(t)=F(t)$$  
(c)  
$$\frac{dx_1(t)}{dt}=x_2(t)$$  
$$\frac{dx_2(t)}{dt}=-\frac{b}{M}x_2(t)-\frac{k}{M}x_1(t)+\frac{1}{M}F(t)$$
$$y(t)=x_1(t)$$  
***  
P3.3  
$$L\frac{d{i_L}}{dt}-V_C+V_2-V_1=0$$  
$$C\frac{dV_C}{dt}=-i_L+i_R$$  
$$i_R R-V_2+V_C=0$$  
$$i_R=-\frac{V_C}{R}+\frac{V_2}{R}$$  
$$\frac{dV_C}{dt}=-\frac{V_C}{RC}-\frac{i_L}{C}+\frac{V_2}{RC}$$  
$$\frac{di_L}{dt}=\frac{V_C}{L}+\frac{V_1}{L}-\frac{V_2}{L}$$  

$$
 \begin{pmatrix}
  \dot{x_1} \\
  \dot{x_2}
 \end{pmatrix}=
 \begin{bmatrix}
  0 & 1/L \\
  -1/C & -1/RC
 \end{bmatrix}
  \begin{pmatrix}
  x_1 \\
  x_2
 \end{pmatrix}+
  \begin{bmatrix}
  1/L & -1/L \\
  0 & 1/RC
 \end{bmatrix}
  \begin{bmatrix}
  V_1 \\
  V_2
 \end{bmatrix}$$  
 ***  
 P3.5  
 (a)  
 $$T(S) = \frac{S+2}{S^3+5S^2-23S+2}$$  
 (b)  
 $$(S^3+5S^2-23S+2)Y(S)=R(S)$$  
 
$$
 \begin{bmatrix}
  \dot{x_1} \\
  \dot{x_2} \\
  \dot{x_3}
 \end{bmatrix}=
 \begin{bmatrix}
  0 & 1 & 0 \\
  0 & 0 & 1 \\
  -2 & 23 & -5
 \end{bmatrix}
  \begin{bmatrix}
  x_1 \\
  x_2 \\
  x_3
 \end{bmatrix}+
  \begin{bmatrix}
  0 \\
  0 \\
  1
 \end{bmatrix}r
 $$  
 
 $$y=
 \begin{bmatrix}
2 & 1 & 0  
\end{bmatrix}
 \begin{bmatrix}
x_1 \\  
x_2 \\
x_3
\end{bmatrix}$$  
***  
P3.12  
(a)  

$$\dot{x}=
 \begin{bmatrix}
  0 & 1 & 0 \\
  0 & 0 & 1 \\
  -48 & -44 & -12
 \end{bmatrix}x+
  \begin{bmatrix}
  0 \\
  0 \\
  1
 \end{bmatrix}r
 $$  
 
 $$y=
  \begin{bmatrix}
  40 & 8 & 0
 \end{bmatrix}x
 $$  
 
(b)  

 $$\Phi(t)=
  \begin{bmatrix}
  \Phi_1(t) : & \Phi_2(t) : & \Phi_3(t)
 \end{bmatrix}
 $$  

$$\Phi_1(t) =
 \begin{pmatrix}
  e^{-6t}-3e^{-4t}+3e^{-2t} \\
  -6e^{-6t}+12e^{-4t}-6e^{-2t} \\
  36e^{-6t}-48e^{-4t}+12e^{-2t}
 \end{pmatrix}$$  

$$\Phi_2(t) =
 \begin{pmatrix}
  \frac{3}{4}e^{-6t}-2e^{-4t}+\frac{5}{4}e^{-2t} \\
  -\frac{3}{2}e^{-6t}+8e^{-4t}-\frac{5}{2}e^{-2t} \\
  27e^{-6t}-32e^{-4t}+5e^{-2t}
 \end{pmatrix}$$  

$$\Phi_3(t) =
 \begin{pmatrix}
  \frac{1}{8}e^{-6t}-\frac{1}{4}e^{-4t}-\frac{1}{8}e^{-2t} \\
  -\frac{3}{4}e^{-6t}+e^{-4t}-\frac{1}{4}e^{-2t} \\
  \frac{9}{2}e^{-6t}-4e^{-4t}+\frac{1}{2}e^{-2t}
 \end{pmatrix}$$  
***  
p3.17  
$$G(S)=C(sI-A)^{-1}B=\frac{-4S+12}{S^3-14S^2+37S+20}$$  
