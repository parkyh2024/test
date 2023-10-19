# **<center>제어공학 2주차 과제**</center>  
2019732017 이상훈

---
### p2.7
그림 P2.7의 op-amp 회로는 적분기이다.

KCL을 통해 식을 세워보면

$\frac{0-V_1(s)}{R}+\frac{0-V_2(s)}{1/sC}=0$ 을 만족한다.  


따라서 위 식을 통해 1차 저역통과 필터로 구분한 적분 증폭기 회로의 전달함수$G(s)$는 $\frac{V_2(s)}{V_1(s)}=-\frac{1}{RCs}$이다.

---

### p2.12
그림 P2.12를 보아 오픈 루프 전달함수는

$\frac{Y(s)}{R(s)}=\frac{K}{s+50}$ 이다.  

$r(t)=1$ 이면 $R(s) = 1/s$의 경우  

$Y(s)=\frac{K}{s(s+50)}$ 가 된다.

위 식을 변형시켜보면  

$Y(s)=\frac{K}{50}(\frac{1}{s}-\frac{1}{s+50})$  

이 되고 인버스 라플라스 변환을 이용하면  

$y(t)=\frac{K}{50}(1-e^{-50t})$ 가 된다.  

$t\rightarrow \infty$ 일 때 $y(t)=\frac{K}{50}$ 이 되므로  

$y(t)\rightarrow1$ 를 만족하는 $K$값은 $50$이다.

---
### p2.15
그림 P2.15는 매달려 있는 스프링-질량-감쇠기 시스템을 볼 수 있다.  

이 시스템에 대한 미분방정식을 세워보면  
$m\frac{d^{2}x}{dt^{2}}+kx+b\frac{dx}{dt}=0$  

$\frac{d^{2}x(t)}{dt^{2}}+\frac{b}{m}\frac{dx(t)}{dt}+\frac{k}{m}x(t)=0$  
된다.  

입력 $\delta (t)$ 이면  

$\frac{d^{2}x(t)}{dt^{2}}+\frac{b}{m}\frac{dx(t)}{dt}+\frac{k}{m}x(t)=\delta (t)/m$ 이다.  

 이를 라플라스변환을 시켜보면  

$s^{2}x(s)+\frac{b}{m}sx(s)+\frac{k}{m}x(s)=1/m$,

$x(s)=\frac{1/m}{s^{2}+\frac{b}{m}s+\frac{k}{m}}$,  

$x(t)=L^{-1}(\frac{1/m}{s^{2}+\frac{b}{m}s+\frac{k}{m}})$,  

$x(t)=\frac{2\sin\left ( \frac{t\sqrt{4km-b^{2}}}{2m} \right )e^{-\frac{bt}{2m}}}{\sqrt{4km-b^{2}}}$
를 구할 수 있다.  



---
### p2.26
그림 P2.26을 보고   


$M\ddot{x}+b(\dot{x}-\dot{y})+k(x-y)=F(t)$ -(1)  
$m\ddot{x}+b(\dot{y}-\dot{x})+k(y-x)=0$ -(2)  

위 식과 같은 로봇의 질량모델의 운동방정식을 구할 수 있다.  
(1),(2) 식에 라플라스 변환을 하게 되면  
(1)
$Ms^{2}X(s)+b(sX(s)-sY(s))+k(X(s)-Y(s))=F(s)$  

$ Ms^{2}X(s)+bsX(s)kX(s)=F(s)+bsY(s)+kY(s)$  

$X(s)[Ms^{2}+bs+k]=F(s)+Y(s)[bs+k]$  이고

(2)  
$ms^{2}Y(s)+b(sY(s)-sX(s))+k(Y(s)-X(s))=0$  

$ms^{2}Y(s)+bsY(s)+kY(s)=bsX(s)+kX(s)$  

$Y(s)[ms^{2}+bs+k]=X(s)[bs+k]$  

$X(s)=\frac{Y(s)[ms^{2}+bs+k]}{bs+k}$

의 결과를 얻을 수 있다.  

$X(s)$를 이용하여 정리해보면  
$\frac{Y(s)[ms^{2}+bs+k]}{[bs+k]}[Ms^{2}+bs+k]=F(s)+Y(s)[bs+k]$,  

$\frac{Y(s)[ms^{2}+bs+k]}{[bs+k]}[Ms^{2}+bs+k]-Y(s)[bs+k]=F(s)$,  

$Y(s)\frac{[ms^{2}+bs+k][Ms^{2}+bs+k]-[bs+k]^{2}}{[bs+k]}=F(s)$이고,  

$\frac{Y(s)}{F(s)}=\frac{[bs+k]}{[ms^{2}+bs+k][Ms^{2}+bs+k]-[bs+k]^{2}}
$를 구할 수 있다.

---
### p2.37
(a)  
그림 P.37를 보면  

$m_1\frac{d^{2}x}{dt^{2}}=-(k_1+k_2)x+k_2y$ 과  

$m_2\frac{d^{2}y}{dt^{2}}=k_2(x-y)x+u$ 을 세울 수 있다.  

문제에서 $m_1=m_2=1$ 이고 $K_1=K_2=1$이라고 했으므로 미분방정식은  

$\frac{d^{2}x}{dt^{2}}=-2x+y$ 와  

$\frac{d^{2}y}{dt^{2}}=x-y+u$ 이 된다.  

(b)  
$U(s)$에서 $Y(s)$까지의 전달함수를 계산하면  

라플라스 변환을 통해

$s^{2}X(s)=2X(s)=Y(s)$  

$s^{2}Y(s)+Y(s)=X(s)+U(s)$  

위 식이 구해지고 $Y(s)$에 대하여 풀면  

$Y(s)=\left [ \frac{s^{2}+2}{s^{4}+3s^{2}+1} \right ]U(s)$  가 구해진다.



