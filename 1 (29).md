# 신규 과제
## **P2.7**
s-domain에서 커패시터의 임피던스는  
$\frac{1}{Cs}$  

KCL에 의해  

$i_1+i_2=0$  

$\frac{V_1(s)}{R}+Cs(0-V_2(s))=0$  

$V_2(s)=-\frac{1}{RCs}V_1(s)$

transfer function은 다음과 같다.

$\frac{V_2(s)}{V_1(s)}=-\frac{1}{sRC}$

## **P2.12**
transfer function은  

$\frac{Y(s)}{R(s)}=\frac{K}{s+50}$  

r(t)는 unit step input이므로 라플라스 변환에 의해

$R(s)=\frac{1}{s}$  

$Y(s)=\frac{K}{s(s+50)}$  
$Y(s)=\frac{K}{50}\left(\frac{1}{s}-\frac{1}{s+50}\right)$  

위 식을 라플라스 역변환 해주면

$y(t)=\frac{K}{50}(1-e^{-50t})$  

$t\rightarrow\infty$일 때 $y(t)\rightarrow1$이므로  

$K=50$이다.

## **P2.15**
$m\ddot{x}+kx=\delta(t-a)$  

라플라스 변환  
초기조건이 0이므로  
$x(0)=0$이고 $\dot{x}(0)=0$이다.  
$ms^2X(s)+kX(s)=e^{as}$  
$X(s)=\frac{e^{as}}{ms^2+k}$  

라플라스 역변환  

$x(t)=\sqrt{\frac{1}{mk}}sin(\sqrt{\frac{k}{m}}(t+a))u(t+a)$


## **P2.26**
$M\ddot{x}+b(\dot{x}-\dot{y})+k(x-y)=F(t)$  
$m\ddot{y}+b(\dot{y}-\dot{x})+k(y-x)=0$  

라플라스 변환

$Ms^2X(s)+b(sX(s)-sY(s))+k(X(s)-Y(s))=F(s)$
$ms^2Y(s)+b(sY(s)-sX(s))+k(Y(s)-X(s))=0$  

이를 행렬으로 정리하면

$$\begin{bmatrix}
  Ms^2+bs+k & -(bs+k)  \\
  -(bs+k) & ms^2+bs+k  \\
  \end{bmatrix}
  \begin{bmatrix}
  X(s)  \\
  Y(s)  \\
  \end{bmatrix}
  =\begin{bmatrix}
  F(s)  \\
  0  \\
  \end{bmatrix}$$  

$(bs+k)X(s)=(ms^2+bs+k)Y(s)$이므로  
$X(s)=\frac{ms^2+bs+k}{bs+k}Y(s)$이다.  

이를  
$(Ms^2+bs+k)X(s)-(bs+k)Y(s)=F(s)$에 대입하면 다음과 같이 구할 수 있다.

$\frac{Y(s)}{F(s)}
=\frac{\frac{1}{mM}(bs+k)}{s^2[s^2+(1+\frac{m}{M})(\frac{b}{m}s+\frac{k}{m})]}$

## **P2.37**
(a) differential equation  
* $m_1$에 의한 미분방정식  
$m_1\frac{d^2x(t)}{dt^2}=-(k_1+k_2)x(t)+k_2y(t)$  

* $m_2$에 의한 미분방정식  
$m_2\frac{d^2y(t)}{dt^2}=k_2(x(t)-y(t))+u(t)$

$m_1=m_2=1$이고 $k_1=k_2=1$이므로  

$\frac{d^2x(t)}{dt^2}=-2x(t)+y(t)$  
$\frac{d^2y(t)}{dt^2}=x(t)-y(t)+u(t)$

(b) transfer function  
라플라스 변환에 의해  

$(s^2+2)X(s)-Y(s)=0$  
$-X(s)+(s^2+1)Y(s)=U(s)$  

위 식을 행렬로 바꾸면 다음과 같다.  

$$\begin{bmatrix}
  s^2+2 & -1  \\
  -1 & s^2+1  \\
  \end{bmatrix}
  \begin{bmatrix}
  X(s)  \\
  Y(s)  \\
  \end{bmatrix}
  =\begin{bmatrix}
  0  \\
  U(s)  \\
  \end{bmatrix}$$  

$X(s)=\frac{1}{s^2+2}Y(s)$이므로  
이를  
$-X(s)+(s^2+1)Y(s)=U(s)$에 대입하면 다음과 같이 구할 수 있다.

$\frac{Y(s)}{U(s)}=\frac{s^2+2}{s^4+3s^2+1}$

