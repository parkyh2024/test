# 5주차 / 과제

# 1번 - p2.7

---
![KakaoTalk_20231006_190346628](https://github.com/JaeGyeongByeon/repository-basic/assets/144103220/ba0e3c58-6009-4a08-b272-a9700f92b130)


KCL을 통해서 문제를 풀면

$$
G(s) = \frac{V_2}{V_1} =-\frac{1}{RCs} 
$$

# 2번 - p2.12

---

![KakaoTalk_20231006_190346957](https://github.com/JaeGyeongByeon/repository-basic/assets/144103220/65d944fb-15e4-4fe9-8e9b-ab52c50abd10)

$$
Y(s) = k \frac{1}{s+50} \frac{1}{s} = \frac{k}{50}(\frac{1}{s}-\frac{1}{s-50}) 
$$

이를 라플라스 변환하여 K를 구할 수 있다. 

k=50

# 3번 - p2.15ㅇ

---

![KakaoTalk_20231006_190347307](https://github.com/JaeGyeongByeon/repository-basic/assets/144103220/03f79864-114d-4465-a658-f41ea52ec6b5)

$$
X(s) = \frac{ms+b}{ms^2+bs+k}
$$

이를 라플라스 변환하면

수식은 다음과 같다.

```matlab
syms s m b k 

X = (m*s+b)/(m*s^2+b*s+k)
Output = ilaplace(X)
```

# 4번 - p2.26

---

![KakaoTalk_20231006_190347688](https://github.com/JaeGyeongByeon/repository-basic/assets/144103220/cc184bfa-90ed-4a55-992c-1619cc1dcd03)

$$
\frac{Y(s)}{F(s)}=-\frac{1}{(k+bs)-(\frac{ms^2+bs+k}{k+bs})(ms^2+bs+k)}
$$

# 5번 - p2.36

---

![KakaoTalk_20231006_190348073](https://github.com/JaeGyeongByeon/repository-basic/assets/144103220/c3ebd1c0-ce4a-4db6-8ba6-81d60b852d40)

$$
\frac{Y(s)}{U(s)} = \frac{-s^2-2}{s^4+s^2-2}
$$
