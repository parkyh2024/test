.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 2장 문제풀이 :computer: 



## P2.7 
그림 2.7과 같이 1차 저역통과 필터로 구현한 적분 증폭기 회로의 전달함수를 구하라.
#### 풀이

이상적인 연상증폭기의 동작조건으로  $i_1 =0,v_1,v_2=0$이다.
키르히호프 법칙을 적용하여 

$$
\frac{(V_1(S) - v_1)}{R} + C\times \frac {d(v_1 - V_2(S))}{dt} = 0 \to \frac{V_1(S)}{R} =  C\times \frac {dV_2(S)}{dt}
$$

라플라스 변환을 통해 전달함수를 구하면

$$
\frac{V_1(S)}{R} =  CsV_2(S) \to V_2(S) = \frac{V_1(S)}{RCs} \to G(s) = \frac{V_2(S)}{V_1(S)} = \frac{1}{RCs}
$$


## P2.12

그림 p2.12에 주어진 블록선도로 표현된 개루프 제어 시스템에 대해 $t \to \infty$ 일 때 단위계단 입력 $r(t)$에 대한 응답  $y(t)\to\ 1$ 이되도록 $K$ 값을 정하라. 초기조건은 영이라고 가정한다.
#### 풀이
초기조건이 0 이므로, Laplace로 입,출력 비 표현이 가능하다. $\to\$ $\frac{Y(S)}{R(S)} = \frac{K}{(S+50)}$ 이다.

$$
Y(S) = \frac{K}{(S+50)} \cdot R(S) 
$$

$r(t)$는 단위계단 입력으로 그 라플라스 변환값은

$$
R(S) = \frac{1}{S}
$$

$$
Y(S) = \frac{K}{S(S+50)} \cdot \frac{1}{S}  \to Y(S) = \frac{K}{50} \cdot ( \frac{1}{S} - \frac{1}{(S+50)} ) 
$$

이고. 역 라플라스 변환을 하면

$$
y(t) = \frac{K}{50} \cdot ( 1 - e^(-50t) ) 
$$

이때 , $t \to \infty$ $y(t) \to \ 1$이기 위해서 $K =50$이다.

## P2.15
스프링-질량 시스템이 그림 p2.15에 주어졌다. 질량 m의 운동을 기술하는 미분방정식을 구하라. 초기조건이 영인 임펄스 입력에 대한 시스템의 응답 $x(t)$ 를 구하라.

#### 풀이
기계적인 운동을 하는 물체에 대하여 뉴턴의 운동법칙을 적용하여 문제를 풀이한다.
마찰력, 스프링의 장력, 물체의 중력을 통해 식을 구하면

$$
M \cdot \frac{d^2(x(t))}{dt^2} + b \cdot \frac{dx(t)}{dt} + kx(t) = 0
$$

이를 라플라스 변환을 통해 정리하면

$$
M\left ( S^{2}\cdot X(S))-S\cdot x(0^{-1})-\frac{\mathrm{d} x(t)}{\mathrm{d} x} \right ) + b(S\cdot X(S))- x(0^{-1}) + KX(S) = 0
$$

$$
r(t) = 0 ,x(0^{-1}) = x_0 , \frac{\mathrm{d} x(t)}{\mathrm{d} x} = 0$ \to MS^2\cdot X(S) -MSx_0 + bSX(S) - bx_0 + KX(S) = 0
$$  

정리하여

$$
X(S)(MS^2 + bS + K) = (MS + b)x_0 \to X(S)=\frac{MS + b}{MS^2 + bS + K}x_0
$$

Matlab을 통해 역라플라스를 진행하면 결과는 다음과 같다.
```
syms s M B K
Xs = (M*s + B) / (M*s^2 + B*s + K);
xt = ilaplace(Xs);
disp('역라플라스:')
disp(xt);
역라플라스:
exp(-(B*t)/(2*M))*(cosh((t*(B^2/4 - K*M)^(1/2))/M) + (B*sinh((t*(B^2/4 - K*M)^(1/2))/M))/(2*(B^2/4 - K*M)^(1/2)))
 
```
이에 시스템의 응답 $x(t)$는 다음과 같다.

$$
e^-{\frac{Bt}{2M}}(cosh(\frac{t\sqrt{\frac{B^2}{4}-KM}}{M})+B\frac{sinh(\frac{t\sqrt{\frac{B^2}{4}-KM}}{M})}{2\sqrt{\frac{B^2}{4}-KM}}) \cdot x(0)
$$





## P2.26
로봇은 그리퍼로 무거운 부하를 들 수 있으며 팔각 부위의 유연성이 높다[6.20]. 이 로봇의 두 질량모델이 그림 P2.26에 주어져 있다. 전달함수 Y(s)/F(S)를 구하라.

#### 풀이
뉴턴의 운동법칙을 적용하여 문제를 풀이한다. 두 물체의 질량은 각각 M,m이며 움직인 거리는 $x(t), y(t)$이다.

$$
M\frac{\mathrm{d^2x(t)}}{\mathrm{d} x^2} +b( \frac{\mathrm{dx(t)} }{\mathrm{d} x} -\frac{\mathrm{dy(t)} }{\mathrm{d} x}) + K(x(t)-y(t)) = F(t)
$$

$$
M\frac{\mathrm{d^2y(t)}}{\mathrm{d} x^2} +b( \frac{\mathrm{dy(t)} }{\mathrm{d} x} -\frac{\mathrm{dx(t)} }{\mathrm{d} x}) + K(y(t)-x(t)) = 0
$$

두 식을 라플라스 변환을 통해 정리하면,

$$
MS^2X(S) +bSX(S) + KX(S) - bSY(S) - KY(S) = F(S)
$$


$$
mS^2Y(S) +bSY(S) + KY(S) - bSX(S) - KX(S) = 0
$$

전달함수 $\frac{Y(S)}{F(S)}$를 구해야하므로 행렬식을 통해 표현하면

$$\begin{bmatrix}
MS^2+bS+k & -(bS + k)\\ 
 -(bS+K)& mS^2+bS+K 
\end{bmatrix}
\begin{bmatrix}
X(S) \\
Y(S)
\end{bmatrix}
&equals;
\begin{bmatrix}
F(S) \\
0
\end{bmatrix}
$$

전달함수를 구하기위해서 $Y(S)$를 구해야 하므로 역행렬을 구하여 진행한다.

$$
\begin{bmatrix}
X(S) \\
Y(S)
\end{bmatrix}
&equals;
A^{-1}
\begin{bmatrix}
F(S) \\
0
\end{bmatrix}
$$

MATLAB으로 실행하면 다음과같다.
```
>> syms s M m b k F

% 행렬 A 정의
A = [M*s^2 + b*s + k, -(b*s + k);
     -(b*s + k), m*s^2 + b*s + k];

% 행렬 A의 역행렬 구하기
A_inv = inv(A);

% 입력 벡터 정의
B = [F; 0];

Y = inv(A) * B;

% Y(s)/F(s) 계산
transfer_function = Y(2)/F;

% 결과 출력
disp('A의 역행렬:');
disp(A_inv);

disp('Y(s)/F(s) = ');
disp(transfer_function);
A의 역행렬:
[(m*s^2 + b*s + k)/(b*m*s^3 + k*m*s^2 + M*b*s^3 + M*k*s^2 + M*m*s^4),         (k + b*s)/(b*m*s^3 + k*m*s^2 + M*b*s^3 + M*k*s^2 + M*m*s^4)]
[        (k + b*s)/(b*m*s^3 + k*m*s^2 + M*b*s^3 + M*k*s^2 + M*m*s^4), (M*s^2 + b*s + k)/(b*m*s^3 + k*m*s^2 + M*b*s^3 + M*k*s^2 + M*m*s^4)]
 
Y(s)/F(s) = 
(k + b*s)/(b*m*s^3 + k*m*s^2 + M*b*s^3 + M*k*s^2 + M*m*s^4)
```
결과로 $\frac{Y(S)}{F(S)}$는 다음과 같다.

$$
\frac{Y(S)}{F(S)} = \frac{K+bS}{MmS^4+bmS^3+MbS^3+KmS^2+KMS^2}
$$


### P2.37
입력 힘 u(t)를 가지는 두 개의 질량 시스템을 그림 p2.37에 나타냈다. $$m_1=m_2=1$$이고 $$K_1=K_2=1$$일 때, (a)이 시스템으로 표현하는 미분방정식을 구하라. (b) U(S)에서 Y(S)까지의 전달함수를 계산하라.
#### 풀이

질량이 다른 두 물체와 각각 다른 스프링 상수 $m_1, m_2, k_1, k_2$를 통해 뉴턴의 운동법칙을 적용하면 그 식은 다음과 같다.

$$
m_{1}\frac{\mathrm{d^2}x(t)}{\mathrm{d} t} + k_1x(t) + k_2(x(t)-y(t)) = 0
$$

$$
m_{2}\frac{\mathrm{d^2}y(t)}{\mathrm{d} t} + k_2(y(t)-x(t)) = u(t)
$$

$m_1=m_2=k_1=k_21$를 적용하하여 미분방정식으로 정리하면 다음과 같다.

$$
\frac{\mathrm{d^2}x(t)}{\mathrm{d} x} = -2x(t) - y(t)
$$


$$
\frac{\mathrm{d^2}y(t)}{\mathrm{d} t} = u(t) + x(t) -y(t)
$$

이 미분방정식을 라플라스 변환을 적용 후, 행렬방정식으로 표현하면

$$
\begin{bmatrix}
S^2+2 & +1\\ 
 -1& S^2+1
\end{bmatrix}
\begin{bmatrix}
X(S) \\
Y(S)
\end{bmatrix}
&equals;
\begin{bmatrix}
0 \\
U(S)
\end{bmatrix}
$$

역행렬을 통해 $Y(S)$에 대해 전개하면  $U(S)에서 Y(S)$의 전달함수를 구할 수 있다.


$$
\begin{bmatrix}
X(S) \\
Y(S)
\end{bmatrix}
&equals;
\begin{bmatrix}
\frac{S^2+1}{S^4+3S^2+3} & \frac{1}{S^4+3S^2+3}\\ 
\frac{S^2+1}{S^4+3S^2+3}& \frac{S^2+2}{S^4+3S^2+3}
\end{bmatrix}
\begin{bmatrix}
0 \\
U(S)
\end{bmatrix}
$$


따라서 $Y(S) = \frac{s^2+2}{s^4+3s^2+3} \cdot U(S)$ 이므로 전달함수 $\frac{Y(S)}{U(S)}= \frac{s^2+2}{s^4+3s^2+3}$ 이다.








