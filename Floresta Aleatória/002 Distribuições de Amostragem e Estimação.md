
   - Distribuições de Amostragem
	   - Função de Massa de Probabilidade (PMF)
	   - Função de Densidade de Probabilidade (PDF)
	   - Função Cumulativa de Distribuição (CDF)
	   - Binomial, Poisson, Normal, Weibull
- Esperança
- Padronização e Normalização

# Função de Massa de Probabilidade (Probability Mass Function - PMF)

Indica a probabilidade de ocorrência de cada valor de uma variável discreta.
A pmf pode ser definida de formas diferentes:
Por exemplo, temos doze caixas pretas: 7 contêm aranhas e 5 contêm coelhos. Quatro caixas são selecionadas aleatoriamente. Y é a variável aleatória indicando o número de aranhas selecionadas.
Digamos que eu tenho um amigo que tem muito medo de aranhas, e tolera no máximo três - uma escolha de 4 aranhas, e ele desmaia.

A pmf pode ser calculada como:
- a probabilidade de não escolher nenhuma aranha
$$
\dfrac{{7 \choose 0}{5 \choose 4}}{12 \choose 4}
$$
- a probabilidade de escolher exatamente quatro aranhas
$$
\dfrac{{7 \choose 4}{5 \choose 0}}{12 \choose 4}
$$
- a probabilidade de escolher de uma a três aranhas


Neste caso, a pmf seria 
$$
p(y) = 
       \left\{
       \begin{array}{lll}
         ? & \qquad y = 0 \\
         ? & \qquad 0 < x < 4 \\
         ? & \qquad x = 4.
       \end{array}
       \right.
$$
A soma total precisa ser 1 - o que quer dizer que dentre as possibilidades totais de coisas acontecerem, "algo precisa acontecer".

# Função de Densidade de Probabilidade (PDF)

Uma Função de Densidade de Probabilidade (PDF) indica como a probabilidade de resultados de um acontecimento está distribuída. Vamos seguir com o acontecimento sendo o lançamento de uma moeda, onde os únicos resultados são cara ou coroa. Cada lançamento de moeda é um "ensaio de Bernoulli" - um evento que tem exatamente dois resultados possíveis.

Isso significa a probabilidade de obter $x$ sucessos com $n$ lançamentos de moeda é:
$$P(X = x) = {n \choose x} p ^ {x} (1 - p) ^ {n - x}$$

$$
F(x) = P(X \le x) = 
       \left\{
       \begin{array}{lll}
         0 & \qquad x < 0 \\
         1 - p & \qquad 0 \leq x < 1 \\
         1 & \qquad x \geq 1.
       \end{array}
       \right.
$$




```
  Quantidade de caras  | Freq. absoluta | Freq. relativa
-------------------------------------------------
0     |   1      |   30      |   20      |
1     |   4      |   30      |   20      |
2      |   6      |   40      |   10      |
3     |   4      |   30      |   20      |
4     |   1      |   30      |   20      |
total     |   16      |   30      |   20      |
```
# Função de Distribuição Acumulada (Cumulative Density Function - CDF)

Indica a probabilidade de que uma variável aleatória seja *maior ou menor a determinado valor* - ou seja, como a probabilidade se acumula dentre os valores indicados por esse intervalo.
$$F(x) = P(X \le x)$$
A CDF pode ser pensada como uma somatória cumulativa da PMF - ou seja, a soma de todas as probabilidades em um intervalo contínuo.

* inserir desenhos*

Nesse caso, podemos imaginar a probabilidade de obter "cara" conforme lançamos a moeda novamente, e novamente, e novamente. A probabilidade nunca vai ser exatamente 100% - você pode lançar uma moeda mil vezes, e ainda há a possibilidade que todos os lançamentos sejam coroa. No entanto, com mais lançamentos, a probabilidade vai de zero caras com zero lançamentos, 0.5 com um lançamento, 0.75 com dois lançamentos, e aí em diante.

Constant random variable is different from this - all boxes with cockroaches would make more sense.



```
Cálculo:
limite de F(x) -> - infinity = 0
limite de F(x) -> + infinity = 1
```

# Esperança

A esperança é o valor esperado do **centro da distribuição.** 

A esperança de Y é a soma dos valores de y, multiplicados pela probabilidade de cada evento.
$$E(y) = \sum{y p(y)}$$

Por exemplo, vejamos o Paradoxo de São Petesburgo.



```
Lei dos Grandes Números

A média tende à esperança.
```

Então, **a média de uma amostra é a melhor maneira de medir a esperança teórica de uma distribuição**, que esperamos que se aproxime dos valores da população real.

Um outro termo que é importante saber é que o **momento de ordem n**  em estatística é:
$$E[X^n]$$
Ou seja, o primeiro momento de uma distribuição é sempre igual a zero:

$$\mu_1 = E[X-E(X)]^1 = E(X)-E(X)=0
$$

A variância é o segundo momento de uma variável aleatória.

$$V(Y) = \sigma^2 = E[(Y-\mu)^2]
$$
Se você não tem variância, você também não tem esperança. (filosófico, não?)

Da variância, podemos calcular o erro médio (standard error) - o valor medido do que é o real desvio padrão.

Nós podemos mostrar que 
$$V(Y) = E[Y^2]-(EY)^2
$$
$$V(Y) = E[(Y-E(Y))^2]
$$
Pra ver a variação, o quadrado serve para retirar as diferenças positivas e negativas, e há a weighing by the probability itself, so we understand what is the variance.

$(Y-E(Y))^2$ é uma variável aleatória.

Momentos de potencias maiores levam a coeficientes de assimetria e curtose, que por enquanto eu não conheci aplicação para ecologia, então paro por aqui.

Distribuições discretas:
# Bernoulli

[Distribuição Binomial (professorguru.com.br)](https://www.professorguru.com.br/estatistica/distribuicao-binomial.html)


No início do capítulo, falamos sobre lançamentos de moeda e um amigo aracnofóbico.

Nesse caso, temos eventos com resultados binários - a moeda é cara ou coroa, com probabilidades 0.5, e o amigo desmaia diante de uma caixa aberta, de acordo com a probabilidade que a caixa contenha uma aranha: 
$$P(X = x) = {n \choose x} p ^ {x} (1 - p) ^ {n - x}$$
Esse tipo de evento leva ao que chamamos de uma Distribuição Binomial.

A distribuição de Bernoulli é uma distribuição binomial com n=1.

Ou seja, uma distribuição binomial que não é Bernoulli seria uma em que há ** n possibilidades de ver y sucessos**. Ou seja, precisamos 

Voltando na combinatória, um caso com n = 12
Seja _X_ uma variável aleatória que contém o número de caras saídas em 12 lançamentos de uma moeda honesta. A probabilidade de sair 5 caras em 12 lançamentos, é dada por:

$$P(X = 5) = {12 \choose 5} 0.5 ^ {5} (1 - 0.5) ^ {12 - 5}$$


A esperança da distribuição Binomial é
E(x) = np

E a variância:

Var(x) = np(1-p)

6 individuos são testados para uma doença com prevalencia de 20%.
Qual a probabilidade que 2 ou mais testem positivo?
$$Y ~Binomial 
$$P(Y>=2)=1-P(y<2) = 1-P(Y=0)-P(Y=1)=1-(6  0)(0.8)^6-(6  1)0.2*0.8^5
answer is 34%

# Poisson
[Distribuição de Poisson (professorguru.com.br)](https://www.professorguru.com.br/estatistica/distribuicao-poisson.html)

O processo de Poisson calcula a quantidade de vezes que um evento ocorre em um período de tempo, área, distância, ou qualquer outra medida contínua.
Por exemplo, um exemplo clássico - quantas vezes no espaço de uma hora um ônibus passa pelo meu ponto.

$$P(x) = \dfrac{\lambda^x e^{-\lambda}}{x!}$$
No caso de uma variável aleatória binomial, $\lambda = np$.

# Padronização e Normalização
[LinkedIn](https://www.linkedin.com/pulse/padroniza%C3%A7%C3%A3o-vs-normaliza%C3%A7%C3%A3o-jose-r-f-junior/?originalSubdomain=pt)
[Standardization and Normalization | Towards Data Science](https://towardsdatascience.com/normalization-vs-standardization-explained-209e84d0f81e#:~:text=What%20is%20Normalization%3F,%28X%20max%20%E2%80%94%20X%20min%29)

Central moment
