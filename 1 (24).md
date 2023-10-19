#**제어공학1 신규 과제**  
2019732035 이의주
***
P2.7  
$$\frac{V_1(s)}{R} = -C\frac{dV_2(s)}{dt}$$   
$$dV_2(s)=-\frac{1}{RC}V_1(s)dt$$   
$$V_2(s) = -\frac{1}{RC}\int_0^s V_1(s)dt\$$   
$$\frac{V_2(s)}{V_1(s)}=-\frac{1}{sCR}$$   
***
P2.12
$$\frac{Y(s)}{R(s)}=\frac{k}{S+50}$$  
$$R(s) = \frac{1}{S}$$  
$$Y(s)=\frac{k}{S(S+50)}=\frac{k}{50}(\frac{1}{S}-\frac{1}{S+50})$$  
$$y(t)=\frac{k}{50}(1-e^{-50t})$$  
$$t->{\infty} 일 때$$  
$$y(t)=\frac{k}{50}$$  
$$y(t)=1, k=50$$
***
P2.15  
$$m\frac{d^2}{dt^2}x(t)+b\frac{d}{dt}x(t)+kx(t)=f(t)$$  
$$\frac{d^2}{dt^2}x(t)+\frac{k}{m}x(t)=0$$  
$$X(s)=\frac{x(0)s}{s^2+k/m}$$  
$$x(t)=x(0)cos\sqrt{\frac{k}{m}}t$$  
***
P2.26  
$$M\frac{d^2}{dt^2}x(t)+b(\frac{d}{dt}x(t)-\frac{d}{dt}y(t)=F(t)$$  
$$m\frac{d^2}{dt^2}y(t)+b(\frac{d}{dt}y(t)-\frac{d}{dt}x(t)=0$$  
$$\begin{bmatrix}(Ms^2+bs+k)&-(bs+k)\\-(bs+k)&(ms^2+bs+k)\\ \end{bmatrix}
\begin{bmatrix}X(s)\\Y(s)\\ \end{bmatrix}=\begin{bmatrix}F(s)\\0\\ \end{bmatrix}$$
$$\frac{Y(s)}{F(s)}=\frac{\frac{1}{mM}(bs+k)}{s^2[s^2+(1+\frac{m}{M})(\frac{b}{M}s+\frac{k}{m})]}$$  
***
P2.37  
$$m_1\frac{d^2x}{dt^2}=-(k_1+k_2)x+k_2y$$  
$$m_2\frac{d^2y}{dt^2}=k_2(x-y)+u$$   
$$m_1=m_2=1, k_1=k_2=1$$  
$$\frac{d^2x}{dt^2}=-2x+y$$  
$$\frac{d^2y}{dt^2}=x-y-u$$
