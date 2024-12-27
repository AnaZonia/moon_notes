
   - [[#Conceitos Fundamentais]]
	   - População e amostra
	   - Probabilidade
	   - Variáveis aleatórias contínuas e discretas
   - [[#Combinatória básica]]
   - [[#Medidas de Tendência Central e Dispersão]]
	   - Média, mediana, moda
	   - Amplitude, desvio padrão, variância, intervalo interquartil, coeficiente de variação, intervalo de confiança.
	   - Escore Z

## Conceitos Fundamentais

Depois de aprender matemática na faculdade e experimentar um pouco de tudo, eu percebi que meu interesse está em usar dados reais pra estudar ecossistemas em larga escala. A ferramenta ideal pra isso é a estatística - **o campo da matemática que inclui a análise e interpretação de dados**.

Esses dados são obtidos a partir *amostras* de uma *população*. A população é o grupo que representa as informações que queremos representar - no caso do meu projeto de pesquisa, todas as florestas tropicais secundárias da América Latina. A amostra é o grupo que representa essa população, que é o que é possível, dados limites logísticos, alcançar dessa população. No meu caso, são as florestas secundárias da Amazônia Brasileira. Mas no fim das contas, o que estamos estudando? A quantidade de formigas por metro quadrado, frequência de chuvas, populações ribeirinhas? Daí a necessidade de definir *variáveis de interesse* - características de interesse dessa população que serão utilizadas para a nossa análise. Note que o valor é chamado "variável" já que, evidentemente, ele varia, e é exatamente essa variação que nos interessa! No caso da minha pesquisa, quero estudar o crescimento dessas florestas, então evidentemente a biomassa é uma variável de interesse. Além disso, pra executar a nossa pesquisa, minhas variáveis de interesse também incluem pressão hídrica, frequência de queimadas, tipo de solo, entre outros, já que eu acredito que a variação dessas, bem, variáveis, afete a biomassa das florestas.

Então, sabemos que na estatística estamos lidando com a expectativa da ocorrência de certos eventos, com dados obtidos e os *erros* que podem ocorrer dentro a medição desses dados. Toda análise de dados inclui incertezas, e é essencial entender como elas funcionam. Daí, toda análise de dados precisa levar em consideração *probabilidades*.

A probabilidade é uma medida numérica que expressa a chance de um evento ocorrer. Ela varia de 0 a 1, onde 0 indica que o evento é impossível de ocorrer e 1 indica que o evento é certo de ocorrer. A probabilidade é usada para quantificar a incerteza associada a diferentes resultados possíveis. Por exemplo, ao lançar uma moeda, a probabilidade de obter "cara" é 0,5, e a probabilidade de obter "coroa" também é 0,5. As duas são igualmente prováveis, e com o ato de lançar uma moeda, o resultado é 100% garantido de ser cara ou coroa, já que 0.5+0.5=1.

```
Notação: Para indicar a probabilidade da variável X ser igual a um valor k, escrevemos:
```
$$P[X=k]$$
No caso, o resultado do lançamento da moeda, sendo cara ou coroa, é considerado uma variável categórica. Já a quantidade de observações do resultado "cara", por exemplo, é uma variável aleatória discreta.

```
Variáveis contínuas: Frações infinitas em um intervalo (temperatura, peso, altura)
Variáveis discretas: Inteiros distintos (número de indivíduos, qualquer contagem)
Variáveis categóricas: Categorias (nacionalidade, espécie)
```

Uma variável aleatória é um termo frequentemente usado pra descrever resultados dependentes de eventos aleatórios. Por exemplo, o resultado de um lançamento de dado é uma variável aleatória discreta, e a altura de uma pessoa é uma variável aleatória contínua.

Podemos pensar numa função que descreve os resultados de um evento aleatório como números.

[Jensen's Inequality (probabilitycourse.com)](https://www.probabilitycourse.com/chapter6/6_2_5_jensen%27s_inequality.php)


## Combinatória básica
```
Notação: Um número fatorial é a multiplicação de cada um dos seus inteiros antecessores:
```
$$5! = 5*4*3*2*1$$
Obs.: Se você tem interesse, há uma prova muito interessante e simples que mostra porque 1! = 0! = 1. Recomendo que busque na internet!

Antes de explorar mais profundamente a probabilidade, precisamos compreender os conceitos de combinatória e permutação.
A combinatória é um ramo da matemática que eu considero extremamente interessante, relacionada com a contagem e organização de elementos.
Uma permutação é um arranjo de objetos distintos. A maneira de ordenar n objetos dentre r posições, quando a ordem das posições importa, é:
$$P^n_r = n * (n-1) * (n-2) * ... * (n-r+2) * (n-r+1) = \dfrac{n!}{(n-r)!}$$

Isso quer dizer que para distribuir 5 livros diferentes para 10 estudantes, temos:
- 10 opções de estudantes para o primeiro livro,
- 9 para o segundo,
e assim por diante, até restar seis opções de estudantes para ganhar o último livro.
Ou seja,
$$10*9*8*7*6 = \dfrac{10!}{(10-5)!} = 30240$$
Temos 30240 maneiras de distribuir 5 livros diferentes. A isso chamamos *arranjo simples*.

Se quisermos, entretanto, distribuir livros *idênticos*, com certeza o número de combinações diferentes vai ser bem menor. Por exemplo, supomos uma situação em que os cinco estudantes sortudos escolhidos Amanda, Bianca, Carlos, Débora e Emília recebam seus livros.
Na situação anterior, Bianca ganhando "Dom Casmurro" e Carlos ganhando "O Código da Vinci", ou vice versa, são consideradas duas opções diferentes. Nesse momento, como todos estão ganhando "Dom Casmurro", então a ordem não faz diferença alguma!
Nesse caso, dentre as combinações, há que retirar as permutações possíveis dentre cada cinco estudantes escolhidos.
Quais são as maneiras de distribuir cinco livros diferentes dentre cinco estudantes?
$$5*4*3*2*1 = \dfrac{5!}{(5-5)!} =\dfrac{5!}{1} = 120$$
Assim, pra cada possibilidade de distribuir 5 livros idênticos para 5 estudantes, há 120 possibilidades de distribuir livros diferentes.

Portanto, a maneira de distribuir 5 livros idênticos dentre 10 estudantes é:
$$\dfrac{10*9*8*7*6}{5!} = \dfrac{10!}{5!(10-5)!} = 252$$
A essa fórmula chamamos *combinação simples*:
$${n \choose j} = \dfrac{n!}{j!(n-j)!}$$
Essa fórmula aparece muito em questões do tipo **de n objetos, escolhemos j**. Por exemplo, quantas maneiras há de se escolher 4 estudantes dentro um grupo de cinco para fazer um exame, dado que não nos importamos com a ordem de escolha dessas pessoas - ou seja, o grupo Amanda, Bianca, Carlos e Débora é idêntico ao grupo Bianca, Débora, Amanda e Carlos.
Assim de 5 valores, escolhemos 4:
$${5 \choose 4} = \dfrac{5!}{4!(5-4)!} = 252$$
Guarde esse conceito, que ele vai ser bem útil lá na frente!

## Medidas de Tendência Central e Dispersão

Um parâmetro é um valor fixo utilizado para descrever uma população, como porcentagem ou proporção de indivíduos com idade acima de 40 anos. A utilização de parâmetros é a estratégia tradicional da **estatística descritiva**. Outros campos da estatística serão mencionados mais à frente. Alguns dos parâmetros mais importantes são:
### Medidas de tendência central
Média - Soma de todos os elementos da amostra, dividida pelo número de elementos.
Mediana - Média dos dois valores centrais da amostra, caso os elementos sejam ímpares; ou o próprio valor central, caso sejam pares.
Moda - Valor ou elemento mais frequente na amostra.

### Medidas de dispersão
Amplitude - Diferença entre o maior e o menor dos valores da amostra.
Intervalo interquartil - intervalo entre os quartis superior e inferior (25% e 75%);
- obtenha a mediana da amostra (divide a amostra na metade maior e menor)
- obtenha a mediana de ambas as metades da amostra
- A diferença das medianas dos dois grupos é o intervalo interquartil.

Desvio padrão - Descreve a variabilidade da amostra, levando em conta todos os seus valores.
	O desvio padrão de uma amostra é representado pela letra grega sigma ($\sigma$): 
$$\sigma = \sqrt{\dfrac{\sum(x_i-\bar{x})^2}{n-1}}$$
$x_i$ -> o valor de cada observação
$\bar{x}$ -> a média da amostra
n -> o número total de elementos da amostra

Muitas vezes o desvio padrão pode ser escrito como
$$\sigma = \sqrt{\dfrac{\sum(x_i-\bar{x})^2}{n}}$$
Quando ulilizado para uma população. Há a variância tendenciosa e não tendenciosa.

Variância - 

$\sigma^2$

[Revisão sobre desvio-padrão amostral e populacional (artigo) | Khan Academy](https://pt.khanacademy.org/math/statistics-probability/summarizing-quantitative-data/variance-standard-deviation-sample/a/population-and-sample-standard-deviation-review)

[Por que dividimos por n - 1 na variância (vídeo) | Khan Academy](https://pt.khanacademy.org/math/ap-statistics/summarizing-quantitative-data-ap/more-standard-deviation/v/another-simulation-giving-evidence-that-n-1-gives-us-an-unbiased-estimate-of-variance)


Coeficiente de variação - desvio padrão dividido pela média

Intervalo de confiança - Intervalo que indica a probabilidade de conter o valor real de uma estimativa.

### Aplicações - Método de variância inversa




Escore z -> 
$$z = \dfrac{x-\bar{x}}{\sigma}$$



Esses parâmetros vão ser explorados com mais detalhes no próximo capítulo.