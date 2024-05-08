- Introdução à regressão linear
- GLM
- Mínimos Quadrados Não Lineares (NLS)
- Correlação
[6.1 - Introduction to GLMs | STAT 504 (psu.edu)](https://online.stat.psu.edu/stat504/lesson/6/6.1#:~:text=The%20term%20%22general%22%20linear%20model,%28with%20fixed%20effects%20only%29.)
- Regressão Logística
- Exemplos
- [(1) Kareem Carr | Data Scientist | 📊📈 on X: "Here are three different ways of thinking about linear regression and why it works. https://t.co/y4po9BpaCD" / X (twitter.com)](https://twitter.com/kareem_carr/status/1688225360184512513)
- Log transforming
- Regressão Múltipla
[Overview of Multivariate Analysis | What is Multivariate Analysis? (mygreatlearning.com)](https://www.mygreatlearning.com/blog/introduction-to-multivariate-analysis/#:~:text=Multivariate%20analysis%20(MVA)%20is%20a,analyzed%20simultaneously%20with%20other%20variables.)

[(1) Cameron Patrick on X: "sigh, the original meaning of "multivariate" in statistics is completely a lost cause now hey https://t.co/9GFzwV6t3X" / X (twitter.com)](https://twitter.com/camjpatrick/status/1696744910475690456)

[BIOS² Education resources - Generalized Linear Models for Community Ecology (bios2.github.io)](https://bios2.github.io/posts/2021-07-19-glm-community-ecology/)

[regression - Why is multicollinearity different than correlation? - Cross Validated (stackexchange.com)](https://stats.stackexchange.com/questions/545148/why-is-multicollinearity-different-than-correlation#:~:text=Multicollinearity%20may%20occur%20even%20when,sum%20of%20the%20other%20predictors.)

Os coeficientes.
[Pearson Correlation Coefficient (r) | Guide & Examples (scribbr.com)](https://www.scribbr.com/statistics/pearson-correlation-coefficient/)

[[Mínimos Quadrados]]

[[Variáveis Censuradas e Truncadas]]

# Mínimos Quadrados Não Lineares

**Mínimos Quadrados Não Lineares (NLS):**

O método de Mínimos Quadrados Não Lineares (NLS) é usado para ajustar modelos matemáticos não lineares a dados observados. Ele busca encontrar os parâmetros do modelo que minimizam a soma dos quadrados das diferenças entre os valores observados e os valores previstos pelo modelo. Esse método é amplamente utilizado quando se tem uma função matemática que descreve a relação entre as variáveis, mas a relação não é linear. O NLS é sensível aos valores iniciais dos parâmetros e pode requerer ajustes cuidadosos para convergir para uma solução.
É uma extensão dos mínimos quadrados lineares



1. **Residual Standard Error:** Também conhecido como erro padrão residual ou erro padrão dos resíduos, isso representa a estimativa da variabilidade não explicada pelo modelo. Em outras palavras, é uma medida da dispersão dos resíduos, que são as diferenças entre os valores observados e os valores previstos pelo modelo. Quanto menor o valor do erro padrão residual, melhor o modelo ajusta-se aos dados, pois os resíduos estarão mais próximos de zero.
    
2. **53.75:** Esse é o valor numérico do erro padrão residual. No contexto da sua análise, esse valor indica a dispersão média dos resíduos ao redor das previsões do modelo. Quanto maior o valor, maior a variabilidade não explicada pelo modelo, e vice-versa.
    
3. **on 1097016 degrees of freedom:** Aqui, "degrees of freedom" (graus de liberdade) refere-se à quantidade de informação disponível para estimar os parâmetros do modelo. Quanto mais graus de liberdade, mais informações você tem para ajustar o modelo. Nesse caso, você tem 1.097.016 graus de liberdade para o cálculo do erro padrão residual. Essa quantidade está relacionada ao tamanho do seu conjunto de dados e ao número de parâmetros estimados pelo modelo.




[Numeracy, Maths and Statistics - Academic Skills Kit (ncl.ac.uk)](https://www.ncl.ac.uk/webtemplate/ask-assets/external/maths-resources/statistics/regression-and-correlation/coefficient-of-determination-r-squared.html#:~:text=%C2%AFy)
2.-,R%202%20%3D%201%20%E2%88%92%20sum%20squared%20regression%20(SSR)%20total,from%20the%20mean%20all%20squared.)
O coeficiente de determinação \(R^2\) é uma métrica estatística utilizada em regressão linear para avaliar o ajuste do modelo aos dados. Ele mede a proporção da variabilidade total dos valores observados que é explicada pelo modelo de regressão. O \(R^2\) varia de 0 a 1, onde 0 indica que o modelo não explica nenhuma variação dos dados e 1 indica que o modelo explica toda a variação dos dados.

O \(R^2\) múltiplo (ou \(R^2\) de múltipla regressão) é usado quando se ajusta um modelo de regressão múltipla com várias variáveis independentes. Ele mede a proporção da variabilidade total da variável dependente que é explicada pelas variáveis independentes do modelo. Em essência, o \(R^2\) múltiplo indica o quão bem as variáveis independentes explicam as variações na variável dependente.

O \(R^2\) ajustado, por outro lado, corrige o \(R^2\) múltiplo para o número de variáveis independentes no modelo e o tamanho da amostra. O \(R^2\) múltiplo tende a aumentar quando mais variáveis independentes são adicionadas ao modelo, mesmo que essas variáveis não sejam realmente relevantes. O \(R^2\) ajustado penaliza modelos com muitas variáveis independentes que não contribuem significativamente para a explicação da variabilidade da variável dependente. Ele é uma medida mais conservadora que ajuda a evitar a inclusão excessiva de variáveis independentes irrelevantes.

Portanto, enquanto o \(R^2\) múltiplo enfoca a proporção de variabilidade explicada pelas variáveis independentes, o \(R^2\) ajustado fornece uma medida mais realista e ajustada do ajuste do modelo, levando em consideração a complexidade do modelo e o tamanho da amostra.


[[Correlação e Colinearidade]]