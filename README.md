# Análise de Sentimentos com Rede Neural (Bag of Words)

## Descrição
Este notebook realiza a análise de sentimentos de revisões críticas de filmes do IMDB, utilizando uma rede neural de 2 camadas lineares com a técnica de **Bag of Words**. O objetivo é treinar o modelo para classificar as revisões como positivas ou negativas, com base no conteúdo textual.

O modelo é treinado por 5 épocas, com o tempo de execução de aproximadamente 2 segundos por época quando configurado para rodar com GPU T4, e cerca de 15 segundos por época com CPU. A acurácia do modelo no conjunto de testes é aproximadamente **86%**.

## Instruções
### 1. **Objetivo do Exercício Prático**
O objetivo deste exercício é melhorar a performance do modelo, otimizando o processo de treinamento e implementando melhorias específicas, de acordo com as seguintes instruções:

- **Tempo de Execução**: Reduzir o tempo de execução por época para 1-2 segundos com GPU T4 ou 15 segundos com CPU.
- **Tokenizador**: Melhorar o tokenizador usado para processar o texto.
- **Learning Rate (LR)**: Ajustar o learning rate para melhorar a acurácia do modelo.
- **Loss**: Corrigir o erro conceitual no cálculo da loss e imprimi-la corretamente durante o treinamento e validação.
- **Validação**: Incluir a validação no processo de treinamento, com a impressão da loss tanto para o treino quanto para a validação.

### 2. **O que foi alterado**
As seguintes alterações foram realizadas no notebook para atender aos requisitos:

- **Tokenização**: Foi usado um tokenizador manual, tendo em vista a simplicidade do treinamento e do dataset.
- **Learning Rate**: O learning rate foi selecionado por grid search como 0.05 para uma melhor convergência e desempenho do modelo.
- **Correção da Loss**: O erro conceitual na impressão da loss foi identificado e corrigido. Agora, o cálculo da loss é realizado corretamente durante o treinamento e validação.
- **Laço de Validação**: Um laço de validação foi adicionado, incluindo a perda tanto de treino quanto de validação a cada época. A divisão do conjunto de treino em treino e validação foi realizada para proporcionar uma avaliação mais precisa do modelo.
- **Acurácia**: A acurácia foi otimizada para ser maior que 65% no conjunto de teste, com ajustes feitos nos parâmetros e validação da técnica de Bag of Words.

### 3. **O que não foi alterado**
As seguintes restrições foram respeitadas:

- **Modelo Neural**: O modelo de rede neural de 2 camadas lineares não foi alterado. O número de parâmetros, a arquitetura e as funções de ativação permanecem as mesmas.
- **Técnica de Bag of Words**: A técnica de Bag of Words não foi modificada.
- **Dataset**: O dataset de 25 mil amostras de treino e 25 mil amostras de teste foi mantido, sem alterações.
- **Função de Loss e Otimizador**: A função de Loss e o otimizador não foram alterados. Apenas o learning rate (LR) foi ajustado para otimizar a performance.
- **DataLoader do Pytorch**: Continuamos utilizando o DataLoader do Pytorch para carregar o dataset, sem tentar carregar todo o dataset diretamente na GPU.

### 4. **Instruções de Execução**
1. **Configuração do Ambiente**:
   - Este notebook foi desenvolvido para ser executado no Google Colab. Garanta que a GPU T4 esteja ativada para otimizar o tempo de execução.
   - Caso não tenha acesso à GPU, o modelo ainda pode ser executado em CPU, mas o tempo de execução por época será maior.

2. **Executando o Notebook**:
   - Faça o download ou clone o notebook para sua área de trabalho.
   - Abra o notebook no Google Colab.
   - Siga as instruções no notebook para treinar o modelo e avaliar o desempenho.

3. **Métricas de Avaliação**:
   - Durante o treinamento, será exibida a loss para o conjunto de treino e validação, além da acurácia final no conjunto de testes.
   - A meta é alcançar uma acurácia superior a 65% no conjunto de testes.

### 5. **Conclusão**
O notebook tem como objetivo proporcionar uma compreensão básica de como melhorar um modelo de análise de sentimentos, utilizando técnicas de pré-processamento, ajuste de hiperparâmetros e implementação de validação. O modelo base, com suas limitações, foi otimizado conforme os requisitos fornecidos, alcançando um desempenho superior ao anterior.
