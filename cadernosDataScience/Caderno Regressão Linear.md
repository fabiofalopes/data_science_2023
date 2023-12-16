1. **Regressão Linear Simples**: Método estatístico que modela a relação entre uma variável dependente e uma variável independente através de uma linha reta.

2. **Variáveis Dependentes e Independentes**: Variável dependente é aquela que se tenta prever ou explicar; variável independente é o fator que se presume influenciar a variável dependente.

3. **Hipótese Nula (β̂1 = 0)**: Suposição de que não existe relação entre as variáveis independente e dependente, ou seja, o coeficiente da variável independente na regressão é zero.

4. **Erro Padrão Residual (RSE)**: Medida de desvio das observações em relação à linha de regressão, indicando a precisão das previsões do modelo.

5. **Coeficiente de Determinação (R2)**: Proporção da variância na variável dependente que é explicada pela variável independente, variando de 0 a 1.

6. **Sobreajuste (Overfitting)**: Situação em que um modelo é excessivamente complexo e se ajusta muito bem aos dados de treino, mas não generaliza bem para novos dados.

7. **Diagnóstico de Modelo**: Avaliação do modelo de regressão para verificar a adequação do ajuste, a presença de outliers, e se as suposições do modelo são atendidas.

8. **Significância Estatística**: Probabilidade de que a relação observada entre as variáveis em um modelo de regressão não seja devido ao acaso.

9. **Avaliação da Qualidade de Ajuste de um Modelo**: Processo de determinar quão bem um modelo estatístico se ajusta aos dados observados.

10. **Interpretação de Métricas em Regressão Linear**: Análise e compreensão das métricas resultantes do modelo de regressão, como RSE e R2, para julgar a eficácia do modelo.

---- --- 
Este caderno aborda a avaliação da qualidade de ajuste de um modelo de regressão linear simples. O documento, na sua versão 0.1, explora como verificar se existe uma relação estatisticamente significativa entre as variáveis dependentes e independentes, rejeitando a hipótese nula de que o coeficiente β̂1 é igual a zero.

Para avaliar o quão bem o modelo se ajusta aos dados, são utilizadas duas métricas principais: o Erro Padrão Residual (RSE) e o coeficiente de determinação (R2).

O RSE é uma medida que indica o quanto as previsões do modelo podem desviar-se, em média, dos valores observados. Um RSE baixo sugere previsões precisas, enquanto um valor alto indica previsões potencialmente imprecisas. É importante considerar a escala da variável dependente ao interpretar o RSE e compará-lo com a média da variável resposta para avaliar a precisão do modelo.

O R2, por outro lado, é uma proporção que varia entre 0 e 1 e indica quanto da variância na variável dependente é explicada pelas variáveis independentes. Um R2 próximo de 1 sugere que o modelo tem um bom ajuste, enquanto um valor próximo de 0 indica um ajuste pobre. No entanto, adicionar mais preditores ao modelo pode inflacionar artificialmente o R2, o que pode levar a um sobreajuste.

O documento enfatiza que não existe um valor de R2 universalmente aceite que defina um modelo como "bom", e que o R2 não deve ser a única métrica a ser considerada na avaliação do ajuste do modelo. Outros diagnósticos do modelo e o contexto do problema também devem ser levados em conta.

O caderno encoraja a prática do cálculo do RSE e a interpretação dos resultados, bem como a compreensão do R2 através de um exemplo prático que relaciona o tempo para terminar um jogo de vídeo com o número de horas de treino diário.