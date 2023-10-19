# Week5_Homework

## p2.7
![image](https://github.com/Yankee1231/Electricity/assets/138596644/0210d91c-b488-4db1-9781-aeeb562faf05)

## p2.12
![image](https://github.com/Yankee1231/Electricity/assets/138596644/99f7f7e4-9f0f-4852-8daf-1dd414d50177)

## p2.15
![image](https://github.com/Yankee1231/Electricity/assets/138596644/473e317c-0118-473a-86ca-c8e28d89a1df)

#### Matlab 코드 (라플라스 변환)
```
syms m b k s
F = 1/(m*s^2 + b*s + k)
f = ilaplace(F)
```
## p2.26
![image](https://github.com/Yankee1231/Electricity/assets/138596644/a4031150-4eab-483f-a9fc-262a9a131ac4)

#### Matlab 코드 (라플라스 변환)
```
syms M m b s k x1 y1 f1
eqn1 = (M*s^2 + b*s + k)*x1 + (b*s + k)*y1 == f1;
eqn2 = -(b*s + k)*x1 + (m*s^2 + b*s + k)*y1 == 0;
sol = solve([eqn1, eqn2], [x1, y1])
pretty(sol.y1)
```

## p2.37
![image](https://github.com/Yankee1231/Electricity/assets/138596644/e2678eeb-fecc-4c2e-b4f0-bbdb6f8bb9d4)

#### Matlab 코드 (라플라스 변환)
```
syms s x2 y2 u2
eqn3 = (s^2 +2)*x2 - y2 == 0;
eqn4 = x2 - (s^2 + 1)*y2 == u2;
sol = solve([eqn3, eqn4], [x2, y2])
pretty(sol.y2)
```
## Matlab 라플라스변환 스크린샷
![image](https://github.com/Yankee1231/Electricity/assets/138596644/6bf6c2d4-df62-42a2-8851-28e55c6943a5)

