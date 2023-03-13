
### Print 
- Exibi na dela o argumento, colocar o comando **Style** para definir fonte, cor e etc.
- [Mais informações](https://reference.wolfram.com/language/ref/Print.html)   


### DSolve
- Resolve equações diferenciais para um função $f(x)$ . Sintaxe 
```mathematica
	DSolve[eqd, f(x), x]
```
pode ser incluido condições de contorno junto a $eqd$ por meio da substituição $eqn \to \{eqn, \; c1, \;c2 \,. . .\}$, notar que o numero de condições de contorno é no maximo igual a ordem da equação diferencial, assim como valores da variável a que se procura ($\{x, \; x_{min}, \; x_{max}\}$ ).
- [Mais informações](https://reference.wolfram.com/language/ref/DSolve.html)

### HypergeometricU
- Dá o valor da  _função hipergeometrica_   de parametros $a$  e $b$ e de variável $x$. Sintaxe 
~~~mathematica
	HypergeometricU[a, b, x]
~~~
- [Mais informações](https://reference.wolfram.com/language/ref/HypergeometricU.html ) 


### LaguerreL
- Fornece o _polinômio de Laguerre_ de ordem $n$  com desrespeito a variável $x$ ($L_n (x)$), usando  $$\mbox{LaguerreL}[n,\; x]$$ ou o polinio associado de Laguerre ($L_n^a (x)$) usando 
~~~mathematica
	LaguerreL[n, a, x]
~~~
- [Mais informações](https://reference.wolfram.com/language/ref/LaguerreL.html)


### ParametricNDSolveValue
- Dá o valor numerico da função $f(x)$  determinado pela equação diferencial $eqd$, no determinado intervalo da variável $x$, com a adição de parametros. Sintaxe 
~~~mathematica
	ParametricNDSolveValue[eqd, f(x),{x,  xmin, xmax}, pars]
~~~
novamente pode-se incluir as condições de contorno por meio da substituição $eqn \to \{eqn, \; c1, \;c2 \,. . .\}$. Exemplo de uso  
~~~mathematica
	pfun = ParametricNDSolveValue[{y'[t]==a * y[t], y[0]==1},
	                             y, {t, 0, 10},  {a} ]   
~~~
Que gera um conjunto de funções parametrizadas por $a$ , para se ter o valor de uma basta substituirmos `pfun[a][t]` , por exemplo 
~~~mathematica
	pfun[1][10]
~~~
retorna $22.0910$
 Por fim, podemos resolver para um ponto especifico de $t$ , fazendo a substituição $y \to y[\mbox{valor de } t]$. 
- [Mais informações](https://reference.wolfram.com/language/ref/ParametricNDSolveValue.html) 


### FindRoot 
- Encontre a raiz de uma função ou equação, próximo ao ponto especificado. Sintaxe 
~~~mathematica
	FindRoot[f[x], {x,x0}]
~~~ 
ou no caso da equação 
~~~mathematica
	FindRoot[eqd, {x,x0}]
~~~  
Exemplo de uso 
~~~mathematica
	FindRoot[Cos[x] == x, {x, 0}]
~~~ 
 que procura a raiz proximo ao ponto $0$ desta equação. Pode-se se achadas raizes de funções simultâneas colocando as varias funções entre chaves ($\{\}$)  tais quais os respectivos pontos.
[Mais informações](https://reference.wolfram.com/language/ref/FindRoot.html) 


### Plot
- Cria o grafico de um função $f(x)$ em  um intervalo de $x$ determinado. Sintaxe 
~~~mathematica
	Plot[f[x], {x, xmin, xmax}]
~~~
Obviamente a um conjunto de parametros de estilos e plots que podem ser incluidos.
- [Mais informações](https://reference.wolfram.com/language/ref/Plot.html) 


### NIntegrate 
- Faz a integração numerica de uma função $f$ em um determinado intervalo. Sintaxe
~~~mathematica
	NIntegrate[f, {x, xmin, xmax}]
~~~  
Exemplo
~~~mathematica
	NIntegrate[Sin[x], {x, 0, 2}]
~~~
que nos fornece como saida o valor $1.41615$.

Pode ser usado para integração de varias variaveis
~~~mathematica
	NIntegrate[f, {x, xmin, xmax}, {y, ymin, ymax}, ...]
~~~
- [Mais informações](https://reference.wolfram.com/language/ref/NIntegrate.html)


### NDSolve
- Resolve Numericamente a equação diferencial para uma função $f$ e de uma variavel independe $x$ . Sintaxe
~~~mathematica
	NDSolve[f, x, {x, xmin, xmax}]
~~~
Lembrando que deve ser incluida as condições de contorno.
- [Mais informações](https://reference.wolfram.com/language/ref/NDSolve.html) 


### Table 
- Faz uma lista do comando `cmd` usando as especificações dada nos parametros, semelhante a um loop for da programação. Sintaxe
~~~mathematica
	Table[cmd, {i, imin, imax, di}]
~~~
No exemplo estamos definindo o passo em que o range deve ser definido.
- [Mais informações]()


### ListPlot
- Cria graficos a partir de pontos coordenados `{x, y}`, tem todas as opções do [[Mathematica ⟶ Aprendendo#Plot|Plot]] regular. Sintaxe 
~~~mathematica
	ListPlot[{{x1, y1}, ..., {xn, yn}}]
~~~
- [Mais informações]()


### Series
- Faz uma expansão em serie de Taylor da função $f$ em torno do ponto $x_0$  de potencia $n$. Sintaxe, 
~~~mathematica
	Series[f, {x, x_0, n}]
~~~
obviamente, $x$ denota a variavel em que a expansão está sendo feita.
- [Mais informações]()

