# MNIST-Digit-Recognizer-Kaggle
Classifier for identifying digits from a dataset of ten thousands of handwritten images.

# INTRODUÇÃO
O MNIST (“Modified National Institute of Standart and Technology”) é uma competição do Kaggle de introdução perfeita para técnicas como redes neurais usando um conjunto de dados clássico de fato “hello word”da visão computacional. Ele teve seu lançamento em 1999 e trata-se de um conjunto de dados clássico de imagens manuscritas que serviu de base para algoritmos de classificação de benchmarking. À medida que surgem novas técnicas de aprendizado de máquina, o MNIST é um ótimo recurso confiável para pesquisadores e alunos.

# OBJETIVO
O objetivo é identificar corretamente os dígitos de um conjunto de dados de dezenas de milhares de imagens manuscritas.

# DESCRIÇÃO
Este código foi utilizado durante a disciplina de Inteligência Computacional em que o objetivo foi realizar um “model selection” para escolher o melhor conjunto de hiperparâmetros possível para o classificador designado, no caso, o SVM One-vs-One (OVO) com kernel polynomial de ordem 4, focando em maximizar a acurácia do modelo no conjunto de validação. Um modelo “baseline”, com hiperparâmetros “default”, também é treinado e medido sua acurácia para comparação de resultados.

# METODOLOGIA
O arquivo ‘train.csv’ disponibilizado foi importado e dividido em dois conjuntos: um de treino e outro de validação. Com o primeiro, foram realizados os treinamentos dos classificadores e com o segundo, as predições e medições de acurácia.

O SVM também foi reinado com o conjunto de dados normalizado, porém teve o desempenho de 85,13%, abaixo do desempenho sem a normalização. Por isso, as técnicas para seleção do melhor modelo foram realizadas com os dados originais.

Foi realizado o ‘Data Augmentation’ para aumentar o conjunto de dados para treinamento. Cada exemplo do conjunto de treino foi copiado e transposto por um pixel, tanto nos sentidos verticais quanto horizontais, e adicionados ao conjunto. Isso permite que o classificador aumente sua acurácia por ter mais exemplos para criar seu modelo.

# RESULTADOS
O classificador SVM One-vs-One (OVO) com kernel polynomial de ordem 4 e ‘Data Augmentation’ teve uma acurácia de 98% de previsão para o conjunto de validação. Sem o ‘Data Augmentation’, a taxa foi de 96,38%.

Já o modelo ‘baseline’, Boosting de Decision Tree, teve uma acurácia de 94,16% para o conjunto de validação.

Os hiperparâmetros escolhidos para nosso SVM foram ‘C’ igual a 1 e ‘gamma’ igual a 1, pois foram os melhores parâmetros encontrados após a realização de uma ‘grid search’ (ao analisar os ’scores’, percebemos que as combinações tiveram o mesmo desempenho, então utilizamos os selecionados pela função).

Quando submetido o código no Kaggle: a posição, ao realizar as previsões para o conjunto de testes no arquivo ’test.csv’, foi 918 com precisão de 97,86% no ranking da competição ‘Digit Recognizer’: ![descrição da imagem](https://www.kaggle.com/c/digit-recognizer/leaderboard)
