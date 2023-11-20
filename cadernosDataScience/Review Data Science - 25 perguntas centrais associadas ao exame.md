## 1. **Por que queremos realizar testes estatísticos nos coeficientes de um modelo linear?**
*Resposta*: Realizamos testes estatísticos nos coeficientes de um modelo linear para determinar se os mesmos têm um impacto significativo na variável dependente. Isto ajuda a entender quais variáveis independentes influenciam a variável de resposta e se essa influência é estatisticamente significativa.

## 2. **O que é um teste estatístico?**
*Resposta*: Um teste estatístico é um procedimento que permite tomar decisões sobre uma população com base em amostras dessa população (dados). Utiliza-se para testar uma hipótese e determinar a probabilidade de obter os resultados observados, sob a suposição de que a hipótese nula é verdadeira.

## 3. O que é uma hipótese nula e alternativa?
*Resposta*: A hipótese nula é uma afirmação de inexistência de efeito ou diferença, enquanto a hipótese alternativa é o contrário, indicando a existência de um efeito ou diferença. Em estatística, testamos a hipótese nula e rejeitamo-la ou não com base nos dados. No caso dos modelos lineares a hipótese nula é que um determinado coeficiente do modelo é zero.

## 4. O que entendemos por aprendizagem estatística?
*Resposta*: A aprendizagem estatística envolve o uso de métodos estatísticos para interpretar e prever dados. Envolve algoritmos e modelos que podem aprender a partir de dados e fazer previsões ou inferências sobre dados não observados.

## 5. O que é um valor-p?
*Resposta*: Um valor-p é a probabilidade de observar um resultado tão extremo ou mais extremo do que o observado nos dados, sob a suposição de que a hipótese nula é verdadeira. É usado para determinar a significância estatística de um resultado.

## 6. Qual é a diferença entre ajuste do modelo (RSE e R^2) e os testes estatísticos nos coeficientes?
*Resposta*: O ajuste do modelo, representado por RSE (Erro Padrão Residual) e R^2 (Coeficiente de Determinação), mede quão bem o modelo se ajusta aos dados. Os testes estatísticos nos coeficientes determinam a significância individual de cada variável independente no modelo.

## 7. O que acontece quando aceitamos a hipótese nula para todos os coeficientes em um modelo linear?
*Resposta*: Se aceitarmos a hipótese nula para todos os coeficientes, teremos de concluir que nenhuma das variáveis independentes tem um efeito significativo na variável dependente. Isso sugere que o modelo pode não ser útil para prever ou explicar a variável dependente.

## 8. O que é um modelo de classificação, e qual é a principal diferença com um modelo linear?
*Resposta*: Um modelo de classificação é usado para prever categorias ou classes discretas de dados. A principal diferença em relação a um modelo linear é que este último é usado para prever valores contínuos. Os modelos de classificação trabalham com variáveis dependentes categóricas, enquanto modelos lineares com variáveis contínuas.

## 9. O que queremos dizer quando afirmamos que um vetor de características X pertence a uma categoria?
*Resposta*: Dizer que um vetor de características X pertence a uma categoria significa que, com base nessas características, o objeto ou observação representado por X é classificado ou identificado como pertencente a essa categoria específica. Dito por outras palavras, isto é o que queremos de um modelo de classificação consiga fazer corretamente.

## 10. O que queremos dizer quando afirmamos que um vetor de características X pertence a uma categoria com alguma probabilidade?
*Resposta*: Isso significa que, com base nas características de X, há uma certa probabilidade de que X pertença a uma categoria específica. É uma maneira de expressar incerteza ou variabilidade na classificação.

## 11. Se tenho um modelo com três coeficientes, qual é a confiança que no resultado do conjunto de três testes estatísticos se para cada um o nível de confiança é 95%?
*Resposta*: 0.95 x 0.95 x 0.95 

## 12. O que é um erro do tipo I em estatística?
*Resposta*: Um erro do tipo I ocorre quando rejeitamos a hipótese nula sendo ela verdadeira. É o erro de identificar um efeito ou diferença quando, na verdade, não existe tal efeito ou diferença.

## 13. O que queremos dizer quando afirmamos que precisamos corrigir valores-p devido a múltiplos testes?
*Resposta*: Isso significa que, ao realizar múltiplos testes estatísticos, o risco de cometer um erro do tipo I aumenta. Portanto, é necessário ajustar os valores-p para controlar a taxa de erro global, como a taxa de erro familiar (FWER) ou a taxa de falsa descoberta (FDR).

## 14. Qual é o papel da função sigmóide na regressão logística?
*Resposta*: Na regressão logística, a função sigmóide (ou logística) é usada para transformar valores lineares em probabilidades. Esta função mapeia qualquer valor real para um valor entre 0 e 1, facilitando a classificação binária.

## 15. O que significa a expressão $E(Y|X=4)$?
*Resposta*: A expressão $E(Y|X=4)$ representa o valor esperado de Y dado que X é igual a 4. É a média de Y nos casos em que X tem valor 4.

## 16. Quais são os dois métodos que temos para estimar o valor de Y dado um vetor de dados (características) X?
*Resposta*: Normalmente a média se tivermos suficientes pontos. Caso não termos pontos que relacionem X e Y para um determinado valor de X olhamos para pontos na vizinhança de X. Isto pode ser um problema se temos muitas variáveis independentes porque a medida que esse número cresce, mais distantes estão os pontos uns dos outros.

## 17. Qual é a diferença entre epsilon e um resíduo em um modelo linear?
*Resposta*: Em um modelo linear, epsilon refere-se ao termo de erro inobservável que representa fatores não incluídos no modelo. Um resíduo, por outro lado, é a diferença entre o valor observado de Y e o valor previsto pelo modelo. Os resíduos são observáveis, enquanto epsilon não é.

## 18. Como calculamos a soma quadrada dos resíduos para um dado modelo, dados alguns dados?
*Resposta*: A soma quadrada dos resíduos é calculada somando o quadrado das diferenças entre os valores observados e os valores previstos pelo modelo. Matematicamente, é a soma de (Y observado - Y previsto)^2 para todos os pontos de dados.

## 19. Qual é a diferença entre dados semi-estruturados e estruturados?
*Resposta*: Dados estruturados são aqueles que seguem um formato definido e organizado, geralmente armazenados em tabelas como em bases de dados relacionais. Dados semi-estruturados não seguem uma estrutura rígida, mas ainda contêm tags ou marcadores para separar elementos semânticos, como XML ou JSON.

## 20. Explique o processo analítico inicial que devemos seguir, dado um conjunto de variáveis independentes candidatas e uma variável dependente, para preparar o treinamento de um modelo de regressão linear?
*Resposta*: O processo inicial inclui: análise exploratória dos dados para entender sua distribuição e relações; seleção de variáveis relevantes através de métodos como análise de correlação ou seleção de características; observação de scatter plots; e preparação dos dados, que pode incluir normalização ou transformação de variáveis.

## 21. Por que dizemos que todos os modelos são imperfeitos?
*Resposta*: Dizemos que todos os modelos são imperfeitos porque os modelos são sempre simplificações da realidade. Nenhum modelo pode capturar completamente a complexidade dos dados reais ou representar todas as variáveis e relações envolvidas. Sempre existem limitações e suposições que afetam a precisão do modelo.

## 22. O que entendemos por sobreajuste (overfit)?
*Resposta*: Overfitting, ou sobreajuste em português, é um fenómeno em modelos estatísticos, onde o modelo aprende tão bem os dados de treino que acaba por capturar também o ruído ou as flutuações aleatórias presentes nesses dados. Em vez de generalizar a partir do padrão verdadeiro subjacente aos dados, o modelo torna-se excessivamente complexo, adaptando-se a peculiaridades específicas do conjunto de treino. Como resultado, apesar de apresentar um bom desempenho nos dados de treino, o modelo geralmente tem um desempenho pobre em dados novos, não vistos anteriormente. Evitar overfitting é crucial para garantir que o modelo seja útil na previsão ou compreensão de novos dados, mantendo a sua capacidade de generalização.

## 23. Qual é a relação entre o intervalo de confiança para um coeficiente de um modelo linear e o erro padrão desse coeficiente?
*Resposta*: A relação entre o intervalo de confiança de um coeficiente num modelo linear e o seu erro padrão é estreita. O intervalo de confiança é geralmente calculado a partir do coeficiente estimado, estendendo-se em ambas as direcções por um número de vezes o erro padrão (por exemplo, $±2$ vezes o erro padrão para um intervalo de confiança de 95%). Assim, um erro padrão maior resulta num intervalo de confiança mais amplo, indicando maior incerteza na estimativa do coeficiente.

## 24. Qual é a hipótese nula que testamos nos coeficientes de um modelo linear?
*Resposta*: A hipótese nula testada nos coeficientes de um modelo linear é que cada coeficiente é igual a zero, o que implica que a variável correspondente não tem efeito significativo na variável dependente. Em outras palavras, testa-se se cada coeficiente tem um impacto estatisticamente significativo na previsão da variável dependente.
    
## 25. Por que não podemos simplesmente usar um regressor linear para um modelo de classificação com três possíveis resultados?
*Resposta*: Não se pode simplesmente usar um regressor linear para um modelo de classificação com três possíveis resultados devido à natureza da variável dependente. Num modelo de classificação, a variável dependente é categórica, enquanto que a regressão linear é adequada para variáveis contínuas ou quantitativas. Para classificação com múltiplas categorias, métodos como regressão logística multinomial ou técnicas de classificação específicas são mais apropriados, pois podem modelar probabilidades de cada categoria e lidar adequadamente com as características categóricas da variável dependente