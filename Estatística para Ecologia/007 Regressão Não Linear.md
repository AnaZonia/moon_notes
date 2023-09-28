[A Gentle Introduction to Linear Regression With Maximum Likelihood Estimation - MachineLearningMastery.com](https://machinelearningmastery.com/linear-regression-with-maximum-likelihood-estimation/#:~:text=Coefficients%20of%20a%20linear%20regression,squares%20solution%20to%20linear%20regression.)

[Likelihood.pdf (mcgill.ca)](https://www.medicine.mcgill.ca/epidemiology/hanley/bios601/Likelihood/Likelihood.pdf)
[A Gentle Introduction to Maximum Likelihood Estimation | by Jonathan Balaban | Towards Data Science](https://towardsdatascience.com/a-gentle-introduction-to-maximum-likelihood-estimation-9fbff27ea12f)

**Verossimilhança:**

A verossimilhança é um conceito usado em estatísticas e modelagem para avaliar quão bem um modelo estatístico ou uma hipótese se ajusta aos dados observados. Ela é uma função da diferença entre os valores observados e os valores previstos pelo modelo. Quanto mais próximos os valores previstos do modelo estiverem dos valores observados, maior será a verossimilhança. A ideia fundamental é que a verossimilhança mede a **probabilidade de observar os dados observados sob a suposição de que o modelo é verdadeiro.**


- **Verossimilhança:** É usada para avaliar a concordância entre os dados observados e as previsões feitas por um modelo. Ela se refere a situações em que os dados já foram observados e está relacionada à adequação do modelo aos dados.
    

Portanto, enquanto a probabilidade está mais ligada à incerteza sobre eventos futuros, a verossimilhança está focada em avaliar quão bem um modelo explica os dados que já foram observados.



**Máxima Verossimilhança (Maximum Likelihood):**

A Máxima Verossimilhança (Maximum Likelihood) é um método estatístico que busca encontrar os parâmetros de um modelo que maximizem a probabilidade de observar os dados que foram realmente observados. Em outras palavras, procura-se encontrar os parâmetros que tornariam os dados observados mais prováveis de ocorrer, de acordo com o modelo proposto. A Máxima Verossimilhança é geralmente aplicada quando há uma distribuição de probabilidade subjacente aos dados e o objetivo é encontrar os parâmetros que melhor ajustam essa distribuição aos dados observados.

Em resumo, enquanto o NLS se concentra na minimização das diferenças entre os valores observados e os previstos pelo modelo, a Máxima Verossimilhança se concentra em encontrar os parâmetros que tornam os dados observados mais prováveis de acordo com uma distribuição de probabilidade subjacente. Ambos os métodos têm suas aplicações e podem ser usados para ajustar modelos a dados em diferentes contextos.

###########

A Negative Log-Likelihood (NLL), ou Log-Likelihood Negativo, é um conceito usado em estatísticas e inferência estatística, especialmente na estimativa de parâmetros de modelos probabilísticos usando a abordagem da Máxima Verossimilhança (Maximum Likelihood).

Vamos dividir o conceito em partes:

1. **Verossimilhança (Likelihood):** A verossimilhança é uma medida que avalia quão bem um modelo estatístico representa os dados observados. Em outras palavras, é a probabilidade de observar os dados que realmente foram observados, sob as suposições do modelo. A função de verossimilhança varia conforme os parâmetros do modelo são ajustados.
    
2. **Log-Likelihood:** A log-verossimilhança é simplesmente o logaritmo natural da função de verossimilhança. O uso do logaritmo é vantajoso porque transforma a multiplicação (que é comum na verossimilhança) em adição, tornando os cálculos mais eficientes.
    


3. **Negative Log-Likelihood (NLL):** A Negative Log-Likelihood é o negativo da log-verossimilhança. Isso significa que você está multiplicando por -1 a log-verossimilhança. A razão para essa transformação é que, quando estamos maximizando a verossimilhança (para encontrar os parâmetros que melhor ajustam os dados), estamos na verdade minimizando a NLL. Isso torna o processo mais intuitivo, já que a maioria dos algoritmos de otimização é projetada para minimização.
    

Em resumo, a Negative Log-Likelihood é uma medida usada para quantificar o quão bem um modelo probabilístico ajusta-se aos dados observados, com a vantagem de tornar os cálculos mais eficientes e se alinhar melhor com algoritmos de otimização. O objetivo ao utilizar a NLL é encontrar os valores dos parâmetros do modelo que minimizam essa medida, o que, por sua vez, maximiza a probabilidade de observar os dados reais sob o modelo.
