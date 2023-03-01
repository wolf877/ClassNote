
### Soft Wall
Equação, $$y''(z) + \left( k^4 z^2 + \frac{3}{4z^2}\right)y(z) =m^2 y(x)$$ obtida na dissertação em  Mello e Silva (2009). Usando [[Mathematica ⟶ Aprendendo#DSolve|DSolve]] obtem duas soluções para essa equação a função hipergemeotrica ([[Mathematica ⟶ Aprendendo#HypergeometricU|HypergeometricU]]$\left[-\frac{m^2}{4k^2}, \; 0, \; k^2x^2 \right]$)  e os polinomios associados de Laguerre ([[Mathematica ⟶ Aprendendo#LaguerreL|LaguerreL]]$\left[\frac{m^2}{4k^2}, \; -1, \; k^2x^2 \right]$) fora pré-termos.

>$\frac{m^2}{4k^2}$ deve ser inteiro?

### Bulk Mass 
Equação diferencial -> [[No-Wall Holographic Model for QCD - Afonin, 2011| No-Wall Holographic Model for QCD]]  equação 12 $$\partial_z\left(\frac{y'(z)}{z} \right) - k^4 z y(x) = - m^2 \frac{y(x)}{z}$$ usando novamente [[Mathematica ⟶ Aprendendo#DSolve|DSolve]] vemos que as soluções para ambas as equações são as mesmas. 

### Encontra as Massas
Usando a equação derivada da equação de movimento $$\partial_z\left(e^{-B(z)} \partial_z \psi(z) \right) + p^2 e^{-B(z)}\psi(z) = 0$$
onde temos que $$B(z)=Ln(z) + k^2z^2$$utiliza-se  [[Mathematica ⟶ Aprendendo#ParametricNDSolveValue|ParametricNDSolve]]  para se obter uma solução numerica de acordo aos parametros $p$, $k$, $z_0$ e $M$ -> $z_0$ e $M$ são zero não aparecem na equação.
* Utilizado condições de contorno em  $z=40$;

> Por que $40$ como z maximo?

* O $z_0$  é $0.08$, pois $1/z_0= 12.5$ ;
* A função é calculada em $0.08$;

Definindo o último parâmetro que falta na variavel pfun, o $k$, de $k=1.35$ para o bottomonium e de $k=0.74$ para o charmonium para encontrar as raizes da função dependente de $p$ que correspondem aos valores de massa.

> Como se chega ou de onde vem os valores para se resolver proximo? 

