# GBM vs AdaBoost vs Stochastic Gradient Boosting

Embora tanto o AdaBoost quanto o GBM sejam algoritmos de boosting que buscam melhorar o desempenho do modelo combinando vários modelos mais fracos, as diferenças na maneira como atribuem pesos às amostras, constroem modelos e ajustam as previsões os tornam adequados para diferentes tipos de problemas e podem levar a resultados diferentes em diferentes cenários.

# Cinco diferenças entre GBM e AdaBoost

1. O GBM constrói um conjunto de modelos, geralmente árvores de decisão, mas de forma sequencial.
2. O GBM possui um hiperparâmetro chamado learning_rate, que controla a taxa de aprendizado do algoritmo com valores geralmente menores que 0.1, o que evita, na maioria dos casos o overffiting.
3. No GBM, a previsão final é a soma das previsões dos modelos individuais, sem pesos associados a cada modelo
4. O GBM não atribui pesos diretamente às amostras. Em vez disso, ele ajusta os erros residuais das previsões dos modelos anteriores, permitindo que cada novo modelo se concentre nas partes do conjunto de dados que não foram previstas com precisão.
5. No Gradient Boosting Machine (GBM), os modelos subsequentes são ajustados para reduzir os erros residuais dos modelos anteriores, visando a redução gradual dos erros.

6. # Cinco hiperparâmetros importantes do Gradient Boosting Machine (GBM) são:

1. **loss**: A função de perda a ser otimizada, podendo ser 'log_loss' para deviance binomial e multinomial, usado na regressão logística, ou 'exponential', que recupera o algoritmo AdaBoost.

2. **learning_rate**: A taxa de aprendizado que controla o encolhimento da contribuição de cada árvore de decisão para a previsão final.

3. **n_estimators**: O número de estágios de boosting a serem executados. Um grande número geralmente resulta em melhor desempenho, mas é importante encontrar um equilíbrio.

4. **subsample**: A fração de amostras a serem usadas para ajustar cada árvore. Valores menores que 1.0 resultam em Stochastic Gradient Boosting, o que pode reduzir a variância.

5. **criterion**: A função para medir a qualidade de uma divisão, que pode ser 'friedman_mse' para erro médio quadrático de Friedman ou 'squared_error' para erro médio quadrático.


# A maior diferença entre GBM e Stochastic Gradient Boosting

Ele faz um subsample do conjunto de dados de treino randomicamente, sem reposição. Fazendo ele ser muito mais rápido e robusto.

A maior diferença entre os dois modelos é a técnica de treinamento. O GBM usa gradient descent para treinar os fracos aprendizes, enquanto o Stochastic GBM usa stochastic gradient descent. O stochastic gradient descent é uma variante do gradient descent que usa apenas uma amostra aleatória dos dados para calcular o gradiente da função de perda. Isso torna o Stochastic GBM mais rápido de treinar, especialmente em grandes conjuntos de dados.


# Resumo do artigo completo de Jerome H. Freedman
[Artigo](https://jerryfriedman.su.domains/ftp/stobst.pdf)

## Introdução

O artigo apresenta o algoritmo de boosting estocástico, uma modificação do algoritmo de boosting tradicional que usa o gradiente estocástico para treinar os fracos aprendizes. O boosting é um algoritmo de aprendizado de máquina em conjunto que constrói um modelo iterativamente adicionando fracos aprendizes. Em cada iteração, um fraco aprendiz é treinado nos resíduos do modelo anterior. Os resíduos são a diferença entre os valores previstos e os valores reais.

## Gradiente estocástico

O gradiente estocástico é uma variante do gradiente descendente que usa apenas uma amostra aleatória dos dados para calcular o gradiente da função de perda. Isso torna o gradiente estocástico mais rápido de treinar do que o gradiente descendente, especialmente em grandes conjuntos de dados.

## Vantagens do boosting estocástico

O boosting estocástico apresenta várias vantagens sobre o boosting tradicional:

1. É mais rápido de treinar, especialmente em grandes conjuntos de dados.
2. É mais resistente a overfitting.
3. Pode ser usado para treinar fracos aprendizes mais complexos.
Experimentos

O artigo apresenta resultados experimentais que mostram que o boosting estocástico supera outros algoritmos de aprendizado de máquina em uma variedade de tarefas de classificação e regressão.

## Conclusão

O boosting estocástico é um algoritmo de aprendizado de máquina poderoso e versátil que é amplamente utilizado na prática. É uma boa escolha para ambos os problemas de classificação e regressão, e é especialmente adequado para grandes conjuntos de dados.

## Detalhes adicionais

Além das vantagens mencionadas acima, o boosting estocástico também é mais flexível do que o boosting tradicional. Isso ocorre porque o gradiente estocástico é menos propenso a ficar preso em mínimos locais do que o gradiente descendente. Isso significa que o boosting estocástico pode ser usado para treinar fracos aprendizes mais complexos, que podem levar a um melhor desempenho do modelo.

O boosting estocástico é um algoritmo de aprendizado de máquina maduro e bem-sucedido. É uma ferramenta valiosa para uma ampla variedade de problemas de aprendizado de máquina.
