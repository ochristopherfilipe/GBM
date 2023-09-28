# GBM vs AdaBoost

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

6. 
