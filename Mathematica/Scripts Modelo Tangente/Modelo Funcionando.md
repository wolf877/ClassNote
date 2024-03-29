Novamente, se inicia resolvendo analiticamente  a equação para o campo vetorial no formato da equação de Schröendinger $$-y'' (z) + \left(k^4 z^2 + \frac{3}{4z^2} \right)y(z) = p^2 y(z)$$ tal qual em   [[Testando Bulk Mass e Soft Wall]], utilizando de novo [[Mathematica ⟶ Aprendendo#DSolve|DSolve]] e encontrando as mesmas soluções. 
O grafico das soluções é feito com o [[Mathematica ⟶ Aprendendo#Plot|Plot]] no intervalo $0 \to 5$ 

> Valido somente nesse intervalo? A segunda solução diverge para z maior que $6$.

As soluções são equivalentes.
>Mas os valores são diferentes nos mesmos pontos de $z$ 

-> Obtendo as constantes de decaimento:
- Equação da constante  decaimento para o campo vetorial (Luiz Fernando, 2018):$$f_n = \lim_{z \to 0} \frac{e^{-k^2z^2}}{m_n g_5 z}\frac{\partial}{\partial z}\Phi_n$$
- Primeiramente se faz a integração numerica da solução encontrada com o o polinomio de laguerre usando [[Mathematica ⟶ Aprendendo#NIntegrate|NIntegrate]] da equação $$NSW= \int^5_0 \left(-\frac{e^{-\frac{1}{2} k^2 z^2} c L^{-1}_{\frac{p^2}{4k^2}}(k^2z^2)}{\sqrt{z}}\right)^2 dz$$
~~~mathematica
	NSW = NIntegrate[(-ysol2S[z, 1, 2])^2, {z, 0, 5}]
~~~
como `ysol2S[x_, k_, p_]` então $k=1$ e $p=2$.$$NSW= \int^5_0 \left(-\frac{e^{-\frac{1}{2}  z^2} c L^{-1}_{1}(z^2)}{\sqrt{z}}\right)^2 dz$$
>Novamente o limite.
>>Essa integração!

>De onde vem o valor de $p$

 Calculando a constante $$f_0 = \frac{1}{2}\frac{e^{-z^2}}{z}\frac{1}{\sqrt{NSW}}\frac{\partial}{\partial z}\left.\left( -\frac{e^{-\frac{1}{2}  z^2} c L^{-1}_{1}(z^2)}{\sqrt{z}}\right)\right|_{z=0}= 1.41422$$ $\frac{1}{2} \; \to \; \frac{1}{p}$ 
repete para o proximo valor de $p=2.82843$, ou seja, $f_1$.

#### Caso numérico

Novamente partisse da equação $$-y'' (z) + \left(k^4 z^2 + \frac{3}{4z^2} \right)y(z) = p^2 y(z)$$Resolvemos a equação numeriricamente, porém diferente do que foi feito em [[Testando Bulk Mass e Soft Wall]], definimos o valor  de $p$ já na equação de modo que não usemos o [[Mathematica ⟶ Aprendendo#ParametricNDSolveValue|ParametricNDSolveValue]] e sim o [[Mathematica ⟶ Aprendendo#NDSolve|NDSolve]].

>Como descobrir as condições de contorno para a solução?

Depois utiliza o [[Mathematica ⟶ Aprendendo#Plot|Plot]] para mostrar as soluções encontradas no dominio.

>Porque multiplicar por aqueles fatores, já estão incluidos na resolução? 

Utiliza exatamente os mesmos passos para o calculo das constantes de decaimento, substituindo apenas a solução anterior pela solução numerica.

>Cálculos de diferente constantes $n=0, 1$ com a mesma solução para $p$?

## Tentativa Nelson e Alfredo

Definidos os valores $$\kappa = 3.2, \quad M = 3.25, \quad z_0 = 0.058$$ Temos a modificação no dilaton para $$A(z, k) = \frac{1}{2}\ln{z} + \frac{1}{2} k^2z^2 + \frac{1}{2} \frac{k^2}{M^4\left(z + z_0 \right)^2}$$ campo auxiliar $$Aux(z, k) = \frac{1}{2}ln{z} + \frac{1}{2} k^2 z^2 + \frac{1}{2}\frac{k^2}{M^4(z + z_0)^2}$$ E o potencial é dado por  $$V(z, k) = A'^2 - A''$$ de modo que a equação diferencia seja $$-y''(z) + \left(A'^2 - A'' \right)y(z) = p^2 y(z)$$
>Notar:$$-y''(z) + \left(\frac{1}{4}B'^2 - \frac{1}{2} B''\right)y(z) = p^2 y(z)$$
>>Onde:$$B(z, k) = ln{z} +  k^2 z^2 + \frac{k^2}{M^4(z + z_0)^2}$$<span style="color: red", style="text-align:center" >São a mesma equação!</span>  -> $B$ é a o campo do modelo!

Usasse o [[Mathematica ⟶ Aprendendo#NDSolve|NDSolve]] para resolver colocando o momento como $p=7.626770313095943$. Se faz o [[Mathematica ⟶ Aprendendo#Plot|Plot]] para vermos o comportamento da solução.

- Usando [[Mathematica ⟶ Aprendendo#NIntegrate|NIntegrate]] no limite $0.31$ a $1.6$ armazenando  a solução $NSWNA$ então para o $f_0$ $$f_0 = \frac{1}{2\pi(7.626770313095943)}\left.\left( \frac{e^{-B(z, 3.2)}}{\sqrt{NSWNA}}\frac{\partial}{\partial z}Sol\, e^{B(x, 3.2)} \right)\right|_{z=0.31}$$
- Para $f_1$ mudasse o limite para $0.0001$ a $3$ e a constante $\kappa$ para $1.6$, valor de $p$ na equação é de $4.487978799921911$.
>Por que mudou os o limite e a constante  $\kappa$?

>Apesar de mudar na equação de $f_1$ a solução usada é dada para para o mesmo valor de $f_0$.

>Na equação de $f_1$ $z \to 0.00000001$ ao invés de $0.0001$ que é o limite inferior da integração?

- Para $f_2$ os limites de integração são $0.0001$ a $3.4$ e $\kappa =1.5$ e o momento usado é de $4.88679$.
>Valor de $p$ bem proximo de $f_1$

>Novamente limites e valor de $\kappa$ são diferente porém com a solução para o mesmo momento de $f_0$. 

>Novamente $z \to 0.00000001$.

Se repete o procedimento para $f_0$ e $f_1$ no entando ambos tem o mesmos limites $0.0001$ a $2.7$ e $\kappa=1.52$  e mundando apenas os limite tomados na derivada.


## Constante de decaimento e massa por Nelson 

Tem-se um fator $$B(z, \kappa, z_0, M) = \ln{z} + \kappa^2z^2 + \frac{\kappa^2}{M^4\left(z + z_0\right)^2}$$ usasse [[Mathematica ⟶ Aprendendo#ParametricNDSolveValue|ParametricNDSolveValue]] para resolver a equação de movimento $$\partial_z\left(e^{-B}\partial_z f(z)\right) + p^2e^{-B}f(z) =0$$ com as mesmas condições de contorno vistas em [[Testando Bulk Mass e Soft Wall]], com as condições de contorno em $z=40$, porém o $z_{min}=10^{-5}$ embora a função a função seja resolvida em $z=10^{-3}$  e o $z_0 = 0.08$.
> A função deveria ser resolvida em $z_0$?

Usasse o [[Mathematica ⟶ Aprendendo#Table|Table]] para mostrar as massas obtidas em uma variação de $M$, sendo $M$ a massa não hadronica.

<div style="background-color: rgb(0, 0, 50);">
	 <span style="color: red", style="text-align:center"><strong>Destaque</strong></span>
	<br>	
	<span>	 
	 O uso de `p/.FindRoot` para atribuir o valor encontrado no `FindRoot` a variavel `p` formando assim de um par ordenado.
	 </span>
</div>

Depois se usa o [[Mathematica ⟶ Aprendendo#ListPlot|ListPlot]] para plotar os graficos dos pontos. Procedimento é repetido dessa vez fixando $M=4.53$ e variando o $z_0$ 

>Mesmo comportamento de grafico -> Mesmo Perfil.

E por fim se faz a variação do $\kappa$, este grafico por sua vez apresenta um perfil diferente. 

Por fim, se faz o plot das soluções em relação a $p$ 
> Mesmo grafico do softwall
> Varias os valores de $\kappa$ para saber qual se encaixa melhor com o a solução do softwall?

Equação utilizada para o cálculo $$fn(z, m_n, \kappa, z_0, M) = \left.\frac{1}{2\pi m_n}\frac{e^{-B(z, \kappa, z_0, M)}}{\sqrt{\int_{10^{-10}}^{20}dx e^{-B(x, \kappa, z_0, M)}\Phi(x, \kappa, z_0, M, m_n)}}\frac{\partial}{\partial y}\Phi(y, \kappa, z_0, M, m_n)\right|_{y=z}$$
>Nova equação para o cálculo da constante de decaimento?