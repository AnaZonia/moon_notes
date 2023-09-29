
1. **Critério de Informação AIC (Akaike Information Criterion) e BIC (Bayesian Information Criterion):** O AIC e o BIC são métricas usadas para comparar a qualidade de diferentes modelos. Geralmente, um modelo com um valor de AIC ou BIC menor é considerado mais adequado. No entanto, eles têm interpretações ligeiramente diferentes e podem ser mais eficazes em contextos diferentes.
O AIC

$$AIC = n + ln(SQE/n) +2k$$
com n sendo o tamanho da amostra
SQE - squared error
k=numero de parametros/variaveis independentes e interações.
quanto maior o n, maior o AIC.
Quanto menor o AIC, melhor
quanto mais complexo o modelo, aumenta o AIC
o que faz sentido. quanto menor a amostra, melhor.
AIC é sempre positivo.

O BIC
$$BIC = 2k + 2ln(\hat{F})$$

k = numero de parametros
F = valor da função de verossimilhança

Regressão logística usa máxima verossimilhança

Outros modelos usam máxima verossimilhança restrita.
GEE, GLM, GMM - AIC
Dá pra ver que os dois são muito parecidos, mas já que o AIC usa SQE, ele se comporta melhor pra modelos lineares. Pra modelagem de equação estrutural geralmente é melhor o BIC. Um problema do BIC é não levar em conta n, então não é útil com extremamente grandes valores de n.




2. **Likelihood Ratio Test (Teste de Razão de Verossimilhança):** Esse teste compara a verossimilhança entre dois modelos, um mais simples (modelo nulo) e outro mais complexo (modelo alternativo). Se o modelo alternativo melhorar significativamente a verossimilhança, ele é preferido.

3. **Cross-Validation (Validação Cruzada):** A validação cruzada envolve dividir os dados em conjuntos de treinamento e teste para avaliar a capacidade de generalização do modelo. O erro de previsão nos dados de teste é usado para comparar a capacidade de diferentes modelos se ajustarem aos dados não vistos anteriormente.

4. **Residual Analysis (Análise dos Resíduos):** Ao analisar os resíduos dos modelos, você pode avaliar a distribuição, homogeneidade e padrões restantes nos erros. Um modelo com resíduos mais próximos de uma distribuição normal e sem padrões significativos geralmente é preferido.

6. **Métricas de Desempenho Específicas do Domínio:** Dependendo do seu domínio de aplicação, pode haver métricas específicas para avaliar a qualidade dos modelos. Por exemplo, em problemas de classificação, você pode usar precisão, recall, F1-score, etc.

9. **Comparação de Medidas de Ajuste:** Em modelos de regressão, você pode comparar medidas de ajuste como R-quadrado, que mede a proporção da variabilidade explicada pelo modelo.



