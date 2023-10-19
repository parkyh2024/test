# Control-System  

![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/91330f69-fd4c-45f6-a0ad-4c7e6758de5f)  

$$
\\frac{{V_a - V_1(s)}}{R} + \frac{{V_a - V_2(s)}}{\frac{1}{sC}} = 0\
$$

여기서 
 
$$
V_a = V_b = 0\
$$

이므로

$$
\-\frac{V_{1}(s)}{R}  -\frac{V_{2}(s)}{\frac{1}{sC}} = 0\
$$

정리하면  

$$
\frac{V_{2}(s)}{V_{1}(s)} = -\frac{1}{RCs}\
$$

![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/3f5d6808-7034-4a8f-a820-fc501004331a)  

$$
\ Y(s) = R(s) \cdot \frac{1}{s + 50} \
$$

이 때 r(t)=unit step이므로  

$$
\ r(t) = 1 \ , \ R(s) = \frac{1}{s} \
$$  

그러므로 식은 다음과 같이 정리된다.  

$$
\ Y(s) = \frac{K}{s(s+50)} \
$$

그리고 t → ∞ 일때 y(t) → 1 이므로

$$
\ \lim_{{t \to \infty}} y(t) = \lim_{{s \to 0}} sY(s) \
$$

$$
\ \lim_{{t \to \infty}} y(t) = \lim_{{s \to 0}} \frac{sK}{{s(s+50)}} \
$$

$$
 \frac{K}{50} = 1 , K = 50
$$  

![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/3c6eb060-c2f8-488d-a985-48e1892386f9)  
![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/3395feda-b0c5-422b-a0c3-8aacde33aeca)  

$$
\ M\frac{d^2x}{dt^2} + kx + b\frac{dx}{dt} = \delta(t) \
$$  

라플라스 변환을 해주고 초기조건이 0인 것을 이용하면  

$$
\ Ms^2X(s) + bsX(s) + kX(s) = 1 \
$$

$$
\ X(s) = \frac{1}{{Ms^2 + bs + k}} \
$$  

$$
x(t) = \frac{2 \cdot \exp\left(-\frac{b \cdot t}{2M}\right) \cdot \sin\left(\frac{t \cdot \sqrt{-b^2 + 4Mk}}{2M}\right)}{\sqrt{-b^2 + 4Mk}}\
$$
![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/f01c3a61-b94c-4f24-a50a-2ba5be5c1d11)  
![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/bb947e48-c9fa-4d9e-8c16-ce20cc65bbeb)  

질량 M에 대해 식을 세우면

$$
\ M\frac{d^2x(t)}{dt^2} + b\frac{d(x(t)-y(t))}{dt} + k(x(t)-y(t)) = F(t) \
$$

이를 라플라스 변환을 시켜주면  

$$
\ Ms^2X(s) + bs(X(s)-Y(s)) + k(X(s)-Y(s)) = F(s) \
$$

질량 m에 대해 식을 세우면  

$$
\ m\frac{d^2y(t)}{dt^2} + b\frac{d(y(t)-x(t))}{dt} + k(y(t)-x(t)) = 0 \
$$

이를 라플라스 변환을 시켜주면  

$$
\ ms^2Y(s) + bs(Y(s)-X(s)) + k(Y(s)-X(s)) = 0 \
$$  

이 식을 X(s)에 대하여 식을 정리해주면  

$$
\ X(s) = \frac{Y(s)(ms^2 + bs + k)}{bs + k} \
$$

이 식을 질량 M에 대해 라플라스변환한 식에 대입을 하고 정리를 하면  

$$
\ \frac{Y(s)}{F(s)} = \frac{bs + k}{(Ms^2 + bs + k)(ms^2 + bs + k) - (bs + k)^2} \
$$

![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/8331d875-c7a2-4355-9dd4-b52a79d31e3a)  
![image](https://github.com/kangjunhyeong/Control-System/assets/144297425/dde4efa0-2157-440d-b486-11b293d8942e)  

질량 m1에 대해 식을 세우면  

$$
\ m_1\frac{d^2x(t)}{dt^2} + K_1x(t) + K_2(x(t)-y(t)) = 0 \
$$  

m1=m2=1, K1=K2=1 이므로  

$$
\ \frac{d^2x(t)}{dt^2}+2x(t)-y(t) = 0 \
$$

이와 같이 m2에 대해서 식을 세우면 다음과 같이 정리된다.  

$$
\ \frac{d^2y(t)}{dt^2}-x(t)+y(t)+u = 0 \
$$

이 두 식을 라플라스변환을 해주면  

$$
s^2X(s) + 2X(s) - Y(s) = 0\ , s^2Y(s) - X(s) + Y(s) + U(s) = 0\
$$  

첫 식을 X(s)에 대해 정리해주면  

$$
\ X(s) = \frac{Y(s)}{s^2 + 2} \
$$  

이 식을 대입해주고 정리하면 다음과 같은 식이 나온다.  

$$
\ \frac{Y(s)}{U(s)} = \frac{s^2 + 2}{1 - (s^2 + 1)(s^2 + 2)} \
$$
