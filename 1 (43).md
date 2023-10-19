## 1.
<img width="281" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/ed1a38d0-26d5-436d-842a-cf29f3da8f45">  

### 문제 풀이  
위의 회로는 이상적인 연산증폭기이다  
이 회로의 동작조건으로 $V_2(S)$와 $V_1(S)$간에 입출력 관계식은

$$
V_2(S) = -\frac{Z_2(S)}{Z_1(S)}V_1(S)
$$

그리고  $Z_1(S) = R, Z_2(S) = \frac{1}{C_S}$이라고 가정한다  
다시 $V_2(S)$에 대해 정리하여 식을 쓰면  

$$
V_2(S) = -\frac{1}{RC_S}V_1(S)
$$

가 된다. 여기까지 구한 후 라플라스 변환을 통해 전달함수를 구한다.  

$$
G(S) = \frac{V_2(S)}{V_1(S)} = -\frac{1}{RC_S}
$$  

## 2.  
<img width="242" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/a4af91aa-bb80-4832-a608-d5d9e5fd2333">

### 문제 풀이  
먼저 라플라스를 사용하여 입출력 간의 관계를 나타낸다. (초기조건 0)  

$\frac{Y(S)}{X(S)} = \frac{K}{S+50}$  

단위계단 입력으로 인해 $r(t)$의 라플라스 변환값은 $R(S) = \frac{1}{S}$ 가 된다.  
따라서 입출력 관계식은  

$$
Y(S) = \frac{K}{S+50}R(S) = \frac{K}{S(S+50)} = \frac{K}{50}(\frac{1}{S}-\frac{1}{S+50})
$$  

가 되고 이 식을 역 라플라스 변환을 통해 y(t)로 정리해준다  

$$
y(t) = \frac{K}{50}(1-e^{-50t})
$$  

이러한 식이 완성되고 문제에서의 조건이 $t \to \infty, y(t) \to 1$ 이기 때문에 $K=50$이 된다.  

## 3.  

<img width="283" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/ac7c6ff2-417c-4cbd-81d7-316ed503abef">

### 문제 풀이  
스프링-질량-감쇠기 시스템은 기계적인 운동이다 따라서 뉴턴의 운동법칙을 적용하여 문제를 풀 수 있다  
마찰력, 스프링의 장력, 물체의 중력에 대한 식을 이용하여 푼다  

$$
m\frac{d^2x(t)}{dt^2} + b\frac{dx(t)}{dt} + kx(t) = 0
$$

이 식을 라플라스 변환을 통해 정리해준다  

$$
m(S^2X(S) - Sx(0^-) - \frac{dx(t)}{dt}) + b(SX(S) - x(0^-)) + kX(S) = 0
$$

$$
r(t)=0,x(0^-)=x_0,\frac{dx(t)}{dt})=0 \to mS^2\cdot X(S) -mSx_0 + bSX(S) - bx_0 + kX(S) = 0
$$

가 된다. 최종적으로 $X(s)$ 에 대해 정리한다.  

$$
mS^2X(S) + bSX(S) + kX(S) = mSx_0 + bx_0
$$

$$
X(S) = \frac{mS+b}{mS^2+bS+k}x_0
$$

가 되고 이 수식을 역라플라스 변환을 시켜줘야하는데 매우 복잡하기 때문에 Matlab으로 진행하였다.  

```
syms S m b k
XS = (m*S + b) / (m*S^2 + b*S + k);
xt = ilaplace(XS);
disp('역라플라스:')
disp(xt);
역라플라스:
exp(-(b*t)/(2*m))*(cosh((t*(b^2/4 - k*m)^(1/2))/m) + (b*sinh((t*(b^2/4 - k*m)^(1/2))/m))/(2*(b^2/4 - k*m)^(1/2)))
```

최종적으로  

$$
e^-{\frac{bt}{2m}}(cosh(\frac{t\sqrt{\frac{b^2}{4}-km}}{m})+b\frac{sinh(\frac{t\sqrt{\frac{b^2}{4}-km}}{m})}{2\sqrt{\frac{b^2}{4}-km}}) \cdot x(0)
$$  

이라는 답이 나온다.  

## 4.  
<img width="246" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/fa103971-59f5-45e8-991a-619834bf64c2">

### 문제 풀이  
스프링-질량-감쇠기 모델은 기계적인 운동이다. 따라서 뉴턴의 운동법칙을 적용할 수 있다  
두 물제의 질량은 각각 M,m이며 움직인 거리를 $x(t)$, $y(t)$라 가정한다  
각각의 식을 구한다  

$$
M\frac{\mathrm{d^2x(t)}}{\mathrm{d} x^2} +b( \frac{\mathrm{dx(t)} }{\mathrm{d} x} -\frac{\mathrm{dy(t)} }{\mathrm{d} x}) + K(x(t)-y(t)) = F(t)
$$

$$
M\frac{\mathrm{d^2y(t)}}{\mathrm{d} x^2} +b( \frac{\mathrm{dy(t)} }{\mathrm{d} x} -\frac{\mathrm{dx(t)} }{\mathrm{d} x}) + K(y(t)-x(t)) = 0
$$

이 두 개의 식을 라플라스 변환을 통해 정리한다  

$$
MS^2X(S) +bSX(S) + KX(S) - bSY(S) - KY(S) = F(S)
$$


$$
mS^2Y(S) +bSY(S) + KY(S) - bSX(S) - KX(S) = 0
$$

전달함수  $\frac{Y(S)}{F(S)}$ 를 행렬식으로 구한다  

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

그 다음으로 역행렬을 통해 $Y(S)$를 구한다  

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

이 문제 또한 너무 복잡하기 때문에 Matlab을 통하여 다음 연산을 진행해준다  

```
syms S M m b k F

% 행렬 A 정의
A = [M*S^2 + b*S + k, -(b*S + k);
     -(b*S + k), m*S^2 + b*S + k];

% 행렬 A의 역행렬 구하기
A_inv = inv(A);

% 입력 벡터 정의
B = [F; 0];

Y = inv(A) * B;

% Y(S)/F(S) 계산
transfer_function = Y(2)/F;

% 결과 출력
disp('A의 역행렬:');
disp(A_inv);

disp('Y(S)/F(S) = ');
disp(transfer_function);
A의 역행렬:
[(m*S^2 + b*S + k)/(b*m*S^3 + k*m*S^2 + M*b*S^3 + M*k*S^2 + M*m*S^4),         (k + b*S)/(b*m*S^3 + k*m*S^2 + M*b*S^3 + M*k*S^2 + M*m*S^4)]
[        (k + b*S)/(b*m*S^3 + k*m*S^2 + M*b*S^3 + M*k*S^2 + M*m*S^4), (M*S^2 + b*S + k)/(b*m*S^3 + k*m*S^2 + M*b*S^3 + M*k*S^2 + M*m*S^4)]
 
Y(S)/F(S) = 
(k + b*S)/(b*m*S^3 + k*m*S^2 + M*b*S^3 + M*k*S^2 + M*m*S^4)
```
위의 연산을 통해 전달함수를 구할 수 있다.  

$$
G(S) = \frac{Y(S)}{F(S)} = \frac{k+bS}{MmS^4+bmS^3+MbS^3+kmS^2+kMS^2}
$$

## 5.  
<img width="243" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/857b00d7-978f-4089-98f6-f4758999a3f1">

### 문제 풀이  
#### (a) 이 시스템을 표현하는 미분방정식을 구하라  
먼저 아래의 두 식을 통해 접근할 수 있다  

$$
m_{1}\frac{\mathrm{d^2}x(t)}{\mathrm{d} t} + k_1x(t) + k_2(x(t)-y(t)) = 0
$$

$$
m_{2}\frac{\mathrm{d^2}y(t)}{\mathrm{d} t} + k_2(y(t)-x(t)) = u(t)
$$

이 식에 $m_1 = m_2 = K_1 = K_2 = 1$을 대입하여 미분방정식으로 다시 정리한다  

$$
\frac{\mathrm{d^2}x(t)}{\mathrm{d} x} = -2x(t) + y(t)
$$

$$
\frac{\mathrm{d^2}y(t)}{\mathrm{d} t} = u(t) + x(t) -y(t)
$$  

#### (b) $U(S))에서 $Y(S)$까지의 전달함수를 계산하라.
(a)에서 구한 식을 라플라스 변환을 시켜준다  

$$
S^2X(S) = -2X(S) + Y(S) \to (S^2+2)X(S) - Y(S) = 0
$$

$$
S^2Y(S) = U(S) + X(S) - Y(S) \to -X(S) + (S^2 + 1)Y(S) = U(S)
$$

이 식도 마찬가지로 행렬식을 이용하여 다시 풀어준다  

$$
\begin{bmatrix}
S^2+2 & -1\\ 
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

최종적으로 $Y(S)$로 싹 정리해준다  

$$
\begin{bmatrix}
X(S) \\
Y(S)
\end{bmatrix}
&equals;
\begin{bmatrix}
\frac{S^2+1}{S^4+3S^2+1} & \frac{1}{S^4+3S^2+1}\\ 
\frac{1}{S^4+3S^2+1}& \frac{S^2+2}{S^4+3S^2+1}
\end{bmatrix}
\begin{bmatrix}
0 \\
U(S)
\end{bmatrix}
$$

$Y(S)$로 정리하면 $Y(S) = \frac{S^2+2}{S^4+3S^2+1}U(S)$ 가 되고 전달함수를 다시 구하면  

$$
G(S) = \frac{Y(S)}{(U(S)} = \frac{S^2+2}{S^4+3S^2+1}
$$

최종적으로 이러한 식이 도출될 수 있다


