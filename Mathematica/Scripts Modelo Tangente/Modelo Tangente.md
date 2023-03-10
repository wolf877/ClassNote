 Dado o potencial do tipo $$V(z) =\frac{B'^2}{4} - \frac{B''}{2}$$ temos primeiramente um fator do tipo $$B= \ln{z} + k^2z^2 + \frac{1}{\left(Mz + \frac{z_0}{k}\right)^2}$$ notar que esse fator é diferente do usado no script [[Modelo Funcionando]] o qual tem o termo $$B= \ln{z} + k^2z^2 + \frac{k}{M^4\left(z + z_0\right)^2}$$
 >Por que essa diferença?
 
 usando o [[Mathematica ⟶ Aprendendo#Series|Series]] se expande o potencia no infinito e em $z=0$, obtendo $$V(z \to \infty)k^4z^2 + \frac{\frac{1}{2} + \frac{1}{4}\left(1 - \frac{8k^2}{M^2} \right)}{z^2} + O\left[\frac{1}{z} \right]^3$$ **expandido até segunda potencia** e $$V(z \to 0) =  \frac{3}{4z^2}+\frac{k^3 M}{z_0^3z} + \frac{k^6M^2}{z_0^6} + O[x]^1$$ **espandido a potencia $0$**. Respectivamente.

Agora modificamos o campo e incluimos o termo da tangente 
 