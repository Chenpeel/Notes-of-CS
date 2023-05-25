### $ \int_{-\infty}^\infty  e^{x^2} =\frac{\sqrt{\pi}}{2} $


### $\int \frac {x\sin{x}} {(x\cos{x} - \sin {x})^2 } $


### $\iint\limits_{D} \ln{(1+x^2+y^2)} d\rho$    ,    $ D ={\set{(\rho,\theta)| 0\le\rho\le 1 , 0\le\theta\le{\frac{\pi}{2}}}} $


### $D_1 =\set{ {(x,y)|0\le y \le \sqrt{a x - x^2}},0 \le x\le a } = \set{(\rho,\theta)|0\le \rho \le a \cos\theta , 0\le \theta \le \frac{\pi}{2}}$


### $$ V = 2 \iint\limits_{D_1}(x^2+y^2)dxdy = 2\iint \limits_{D_1} \rho ^2 \cdot \rho  d\rho d\theta  = 2\int_{0}^{\frac{\pi}{2}} d\theta \int_{0}^{a\cos\theta} \rho ^3  d\rho = \frac{a^4}{2} \int_{0}^{\frac{\pi}{2}} \cos ^4 \theta d\theta = \frac {3}{32} \pi a^4 $$


### $ \int_{0}^{\frac {\pi}{2}} \sin ^n x =\int_{0}^{\frac{\pi}{2}}\cos ^n x =   \begin{cases} \cfrac{n-1}{n} \cdot \cfrac{n-3}{n-2} \cdot \cdot \cdot \cfrac{2}{3}\cdot{1} & n \text{ is odd.} \\ \cfrac{n-1}{n}\cdot \cfrac{n-3}{n-2}\cdot\cdot\cdot \cfrac{1}{2}\cdot\cfrac{\pi}{2} &n\text { is even.} \end {cases} $



设当$x > -1$ 时，可微函数$f(x)$满足条件$f'(x)+f(x) - \cfrac{1}{x+1} \int_{0}^{x}f(t)dt =0$ ,且$f(0)=1$ ,试证：当$x \ge0$ 时，有$e^{-x}\le f(x) \le {1}$ 成立.

证明：

​	由题意知，$f'(0) =-1 $ 

​	所给方程可变形为：$(x+1)(f'(x)+f(x)) = \int_{0}^{x} f(t)dt$

​	对两边求导得：$(x+1)f''(x)+(x+1)f'(x) = 0$

​	积分得：	$f'(x) = {\cfrac{Ce^{-x}}{x+1}}$

​	由于$f'(0) =-1$ 故:$f'(x) = -\cfrac {e^{-x}}{x+1}$

​	显然$x\ge 0 $时$f'(x)<0$,$f(x)$单调递减	

​	而$f(0)=1$ 因此 $x\ge 0$时$f(x)\le 1$

​	对$f'(t) = -{\cfrac {e^{-x}}{x+1}}$在$[0,x]$上积分可得：

​	$f(x)=f(0)-\int_{0}^{x}{\cfrac{e^{-t}}{t+1}}dt \ge 1-\int_{0}^{x}e^{-t}dt = e^{-x} $ .





