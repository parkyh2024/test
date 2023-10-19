#P2.7

KCL을 적용한다.
$$i_{1}=i_{2}+i_{-}$$
$$\frac{v_{1}(t)-V_{-}}{R}=C\frac{\text{d}(V_{-}-v_{2}(t))}{\text{d}t}+i_{-}$$
$$V_{-}=V_{+}=0, i_{-}=i_{+}=0$$
$$\frac{v_{1}(t)}{R}=C\frac{\text{d}(-v_{2}(t))}{\text{d}t}$$


라플라스 변환을 적용한다.
$$\frac{V_{1}(s)}{R}=-Cs{V_{2}(s)}$$
$$\therefore\frac{V_{2}(s)}{V_{1}(s)}=-\frac{1}{sRC}$$


---
#P2.12

전달함수를 구해보면
$$\frac{Y(s)}{R(s)}=\frac{K}{s+50}$$
R(s)가 unit step function이기에 라플라스 변환을 적용하면
$$R(s)=1/s$$
Y(s)를 구해보면
$$Y(s)=\frac{K}{s(s+50)}$$
Y(s)에 부분분수로 변환하면
$$Y(s)=\frac{K}{50}(\frac{1}{s}-\frac{1}{s+50})$$
Y(s)에 역라플라스 변환을 적용하면
$$y(t)=\frac{K}{50}(1-e^{-50t})$$
$t\rightarrow\infty$일때 $y(t)\rightarrow1$이 된다. 따라서
$$y(\infty)=\frac{K}{50}(1-e^{\infty})=\frac{K}{50}=1$$
$$\therefore K=50$$


---
#P2.15

미분방정식을 작성하면
$$M\frac{\text{d}^2x(t)}{\text{d}^2t}+b\frac{\text{d}x(t)}{\text{d}t}+kx(t)=\delta(t)$$
라플라스 변환을 적용하면
$$Ms^2X(s)+bsX(s)+kX(s)=1$$
$$X(s)(Ms^2+bs+k)=1$$
$$X(s)=\frac{1}{Ms^2+bs+k}$$
라플라스 역변환을 적용하면  
<img src = "https://drive.google.com/uc?id=1axQftd0zmlrIE4LbvblE-xFJ_EPIzitg" height="300" width="300">

$$\therefore \frac{2\sin(\frac{t\sqrt{-b^2+4km}}{2m})e^{\frac{-bt}{2m}}}{\sqrt{4km-b^2}}$$


---
#P2.26

물체 M에 대한 free body diagram을 작성 후 미분방정식을 세우면
$$M\frac{\text{d}^2x}{\text{d}^2t}+\frac{\text{d}(x(t)-y(t))}{\text{d}t}+k(x(t)-y(t))=f(t)$$
라플라스 변환을 적용하면
$$Ms^2X(s)+bs(X(s)-Y(s))+k(X(s)-Y(s))=F(s)$$
$$X(s)(Ms^2+bs+k)+Y(s)(-bs-k)=F(s)$$
$$X(s)=\frac{F(s)+(bs+k)Y(s)}{Ms^2+bs+k}$$
물체 m에 대한 free body diagram을 작성 후 미분방정식을 세우면
$$m\frac{\text{d}^2y}{\text{d}^2t}+\frac{\text{d}(y(t)-x(t))}{\text{d}t}+k(y(t)-x(t))=0$$
라플라스 변환을 적용하면
$$ms^2X(s)+bs(Y(s)-X(s))+k(Y(s)-X(s))=F(s)$$
$$Y(s)(ms^2+bs+k)+X(s)(bs+k)=F(s)$$

$Ms^2+bs+k=\alpha, ms^2+bs+k=\alpha', bs+k=\beta$라고 가정하고 두 식을 치환해서 정리하면
$$X(s)=\frac{F(s)+\beta Y(s)}{\alpha}, Y(s)\alpha'-X(s)\beta=0$$
Y(s)식에 X(s)식을 대입해서 정리하면
$$Y(s)\alpha'-\frac{F(s)+\beta Y(s)}{\alpha}\beta=0$$
$$Y(s)\alpha'\alpha-\beta F(s)-\beta^2 Y(s)=0$$
$$Y(s)(\alpha'\alpha-\beta^2)=\beta F(s)$$
$$\frac{Y(s)}{F(s)}=\frac{\beta}{\alpha'\alpha-\beta^2}$$
$$\frac{\beta}{\alpha'\alpha-\beta^2}$$
$$\frac{\beta}{\alpha'\alpha-\beta^2}=\frac{bs+k}{(Ms^2+bs+k)(ms^2+bs+k)-(bs+k)^2}$$
해당식을 정리하면
$$\therefore\frac{Y(s)}{F(s)}=\frac{bs+k}{Mms^2+s^2(bs+k)(M+m)}$$


---
#P2.37

(a)  
물체 m1에 대한 free body diagram을 작성 후 미분방정식을 세우면
$$m_{1}\frac{\text{d}^2x(t)}{\text{d}^2t}+k_{1}x(t)+k_{2}(x(t)-y(t))=0$$
물체 m2에 대한 free body diagram을 작성 후 미분방정식을 세우면
$$m_{2}\frac{\text{d}^2y(t)}{\text{d}^2t}+k_{2}(y(t)-x(t))+u=0$$

(b)  
$m_{1}=m_{2}=1, K_{1}=K_{2}=1$이기에 이를 대입하여 식을 정리하면
$$\frac{\text{d}^2x(t)}{\text{d}^2t}+x(t)+(x(t)-y(t))=0$$
$$\frac{\text{d}^2y(t)}{\text{d}^2t}+(y(t)-x(t))+u=0$$
m1식에 라플라스 변환을 적용하면
$$s^2X(s)+X(s)+X(s)-Y(s)=0$$
$$X(s)(s^2+2)=Y(s)$$
$$X(s)=\frac{Y(s)}{s^2+2}$$
m2식에 라플라스 변환을 적용하면
$$s^2Y(s)+Y(s)-X(s)+U(s)=0$$
X(s)로 정리한 m1의 미분방정식을 m2의 미분방정식에 대입하면
$$s^2Y(s)+Y(s)-\frac{Y(s)}{s^2+2}=-U(s)$$
$$(s^2+1-\frac{1}{s^2+2})Y(s)=-U(s)$$
$$\frac{+s^4+3s^2+1}{s^2+2}Y(s)=-U(s)$$
$$\therefore\frac{Y(s)}{U(s)}=-\frac{s^2+2}{s^4+3s^2+1}$$






```python
from google.colab import drive
drive.mount('/content/drive')
```


```python
!jupyter nbconvert --to markdown /content/drive/MyDrive/Colab\ Notebooks/Control_ch2.ipynb
```

    [NbConvertApp] Converting notebook /content/drive/MyDrive/Colab Notebooks/Control_ch2.ipynb to markdown
    [NbConvertApp] Writing 2924 bytes to /content/drive/MyDrive/Colab Notebooks/Control_ch2.md



