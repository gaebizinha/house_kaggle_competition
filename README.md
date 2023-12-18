# House Prices - Advanced Regression Techniques

Olá! Se você está aqui, quer dizer que passamos da Sprint 3, maravilha! Agora vamos focar em descobrir padrões dos nossos dados, e esta atividade ponderada é perfeita para consolidarmos o nosso conhecimento. Em grupo, se juntem e entrem no site: [house_kaggle_competition](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques), leiam o desafio, baixem os dados, façam uma pequena análise e criem seus notebooks para solucionar o problema proposto. Boa sorte! Não esqueça de submeter o desafio global, vamos tentar chegar nos 100 primeiros do mundo!

## Para que eu possa corrigir a sua ponderada, faça o `git clone` deste repositório, faça suas modificações (lembre-se que este notebook ajudará você e seu grupo à desenvolver o relatório do Artefato, em relação à ocrrelações dos dados), crie uma branch com seu nome, e faça um commit das suas modificações NA SUA BRANCH. No card coloque o link do seu commit =)

## Claro, o Barema da ponderada segue:

Desenvolvimento e Submissão de Soluções para o Desafio House Kaggle

1. Compreensão do desafio House Kaggle, incluindo o contexto e os objetivos do desafio;
2. Implementação das soluções do desafio no notebook preparatório de forma que passem nos testes pré-setados;
3. Utilização de técnicas, algoritmos e bibliotecas para a resolução dos problemas propostos;
4. Submissão das soluções desenvolvidas ao Kaggle Open Challenge;
5. Descrição dos requisitos para o desenvolvimento das soluções e compreensão do desafio House Kaggle;
6. Explicação detalhada do desenvolvimento das soluções, avaliação, otimização e submissão ao Kaggle utilizando comentários no código;

A escrita do texto deve ser clara, precisa e livre de erros ortográficos. Será descontado até 20% dos pontos caso sejam encontrados erros de ortografia.

Avançado (9,1 - 10): cumpriu todos os 6 itens descritos acima;

Intermediário (7,1 - 9): cumpriu 5 dos 6 itens descritos acima;

Básico (4,1 - 7): cumpriu 4 dos 6 itens descritos acima;

Insuficiente (0 - 4): cumpriu menos que 3 itens descritos acima.

# Agora vamos para a nossa ponderada!

Descreva aqui as diferenças de treinamento que você encontrou entre os treinamentos de Ensemble. Passe por todos os métodos.
Descreva as modificações que você porpôs.

## Compreensão do desafio House Kaggle:

O desafio Kaggle House propõe que sejam criados modelos preditivos que façam a previsão do preço final de casas a partir de dados como características físicas, condição da propriedade, localização, etc; Os participantes podem utilizar aprendizado de máquina com linguagens R ou Python.

## Diferenças entre os Modelos e Sugestões para Melhoria:

### Ridge com log-target:

 - Pré-processamento e caching em memória.
 - Validação cruzada com 5 folds e métrica RMSE.
 - Sugestões de melhoria: Busca mais abrangente de hiperparâmetros, feature engineering, análise de resíduos.

### KNN com GridSearch:

 - Pré-processamento e caching em memória.
 - Busca em grade para otimização dos hiperparâmetros
 - Validação cruzada com 3 folds
 - Sugestões de melhoria: Experimentação com outros modelos de regressão, aumento de folds na validação cruzada.

### Random Forest com SelectFromModel:

 - Pré-processamento e seleção de características.
 - Validação cruzada com 5 folds.
 - Sugestões de melhoria: Avaliação de modelos individuais, identificação e tratamento de outliers.

### SVR com GridSearch:

 - Utiliza Support Vector Regressor com pré-processamento.
 - Busca em grade para otimização dos hiperparâmetros
 - Validação cruzada com 5 folds
 - Sugestões de melhoria: Cross-validation folds, experimentação com outros modelos.

### Decision Tree:

 - Utiliza árvore de decisão para regressão, com pré-processamento.
 - Validação cruzada com 5 folds.
 - Sugestões de melhoria: Otimização dos hiperparâmetros, tratamento de outliers.

### Ensemble (VotingRegressor):

 - Combinação de Gradient Boosting, AdaBoost, Ridge e SVM usando VotingRegressor.
 - Validação cruzada com 5 folds.
 - Sugestões de melhoria: Ensemble weight tuning, avaliação de modelos individuais.

### Ensemble (StackingRegressor):

 - Utiliza modelo de empilhamento com Gradient Boosting, AdaBoost, Ridge e SVM.
 - Validação cruzada com 5 folds.
 - Sugestões de melhoria: Experimentação com outros modelos de regressão.

### XGBoost com Cross-Validation:

 - Utiliza XGBoost para regressão com pré-processamento.
 - Validação cruzada com 5 folds.
 - Sugestões de melhoria: Otimização dos hiperparâmetros, feature engineering.

### XGBoost com Early Stopping:

 - Utiliza XGBoost com early stopping para evitar overfitting.
 - Treinamento em dois conjuntos e exibe gráfico da métrica RMSE.
 - Sugestões de melhoria: Análise de resíduos, experimentação com outros algoritmos.

## Ponderação entre modelos ensemble e diferenças de treinamento:

- RandomForestRegressor: Cria várias árvores de decisão com subconjuntos aleatórios dos dados e características. As previsões de cada árvore são combinadas para obter uma previsão final.

 - AdaBoost e GradientBoosting: Constroem modelos sequencialmente para corrigir os erros dos modelos anteriores. AdaBoost pondera exemplos incorretamente classificados, enquanto GradientBoosting ajusta a resposta dos modelos anteriores.

 - XGBoost: É uma implementação otimizada de Gradient Boosting que lida com a regularização internamente para evitar overfitting e suporta treinamento paralelo.

 - StackingRegressor: Combina os resultados de vários modelos de base, como Gradient Boosting, AdaBoost, Ridge e SVM, usando uma meta-regressão como modelo final.

## Resumo das possíveis melhorias:

 - Otimização dos Hiperparâmetros;
 - Feature Engineeringe (exploração de novas características para melhorar a capacidade preditiva do modelo);
 - Análise de Resíduos (compreensão das áreas em que os modelos estão falhando e ajuste conforme necessário);
 - Ensemble Weight Tuning (ajuste dos pesos dos modelos no ensemble para otimizar o desempenho);
 - Cross-Validation Folds (aumentar, talvez, o número de folds na validação cruzada para avaliar a estabilidade do desempenho);
 - Avaliação de Modelos Individualmente;
 - Tratamento de Outliers;
 - Experimentação com Outros Modelos.
