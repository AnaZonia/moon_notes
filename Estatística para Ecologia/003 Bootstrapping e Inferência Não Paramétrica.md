- Tabela de Contingência
- Bootstrapping
- Gráfico Q-Q
- Métodos Não-Paramétricos (sem distribuição)
- Teste Qui-Quadrado
- Teste Mann-Whitney U

[TESTE DO QUI-QUADRADO (ufpr.br)](http://www.leg.ufpr.br/lib/exe/fetch.php/disciplinas:ce001:teste_do_qui-quadrado.pdf)

[Inferência estatística não paramétrica (ufpr.br)](http://leg.ufpr.br/~lucambio/Nonparam/Nparam.html)
[Regressão não paramétrica (ufpr.br)](http://leg.ufpr.br/~lucambio/Nonparam/NparamIV.html)

# Tabela de Contingência

Uma tabela de contingência, também conhecida como tabela de contingência cruzada ou tabela de dupla entrada, é uma tabela que mostra a frequência de observações dentre *variáveis categóricas* e identificar possíveis padrões ou associações.

Por exemplo, considere uma pesquisa que deseja investigar a relação entre o gênero e a preferência de esporte. Uma tabela de contingência poderia ser construída da seguinte forma:

```
              | Esporte A | Esporte B | Esporte C |
-------------------------------------------------
Masculino     |   50      |   30      |   20      |
Feminino      |   20      |   40      |   10      |
```


# Bootstrapping

O bootstrapping é uma técnica estatística de reamostragem que envolve a criação de múltiplas amostras simuladas a partir de um conjunto de dados original. Essa técnica é frequentemente usada para estimar a variabilidade de estatísticas de interesse, como média, desvio padrão, intervalos de confiança e outros, quando não é possível obter novos dados reais.

Aqui estão os passos básicos do bootstrapping:

1. **Amostragem com Substituição:** Dado um conjunto de dados original com tamanho \(N\), o bootstrapping envolve a criação de uma nova amostra aleatória a partir dos dados originais, mas com substituição. Isso significa que cada vez que um elemento é escolhido para a nova amostra, ele é devolvido ao conjunto original antes da próxima seleção.

2. **Tamanho da Amostra de Bootstrap:** A nova amostra gerada através do bootstrapping terá o mesmo tamanho do conjunto de dados original, ou seja, \(N\).

3. **Estimação da Estatística:** Para cada nova amostra de bootstrap, a estatística de interesse (por exemplo, média, desvio padrão, mediana) é calculada.

4. **Repetição:** Esse processo de amostragem com substituição e cálculo da estatística é repetido várias vezes (geralmente milhares de vezes) para criar uma distribuição das estatísticas de bootstrap.

5. **Estimativas e Intervalos de Confiança:** Com base nas estatísticas de bootstrap calculadas, você pode obter estimativas pontuais da estatística de interesse e também construir intervalos de confiança, que mostram a faixa de valores dentro da qual a estatística é mais provável de cair.

O bootstrapping é útil quando você deseja entender a variabilidade de uma estatística sem fazer suposições sobre a distribuição subjacente dos dados. Ele permite que você obtenha uma aproximação da distribuição das estatísticas de interesse sem depender de fórmulas analíticas complexas. No entanto, é importante lembrar que o bootstrapping não cria novas informações; ele apenas utiliza as informações presentes nos dados originais para estimar a variabilidade.

# Gráfico Q-Q