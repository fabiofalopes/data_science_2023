# Conceitos 

## Modelo de Regressão
Um modelo de regressão da-nos uma função que descreve a relação entre 1 ou mais variáveis independentes e uma resposta ou variável dependente (target value).

## Como estimar f(x) ou Y
- Não podemos obter $E(Y |X = x)!$ exatamente pois o modelo não vai traduzir exatamente o mesmo resultado.
	- Podemos "*relaxar*" a definição anterior para:
		$f^ (x) = Ave(Y |X ∈ N (x))$
		onde  $N(x)$ é uma vizinhança de x.
	- Aproximação por Nearest Neighbour Averaging pode ser boa para pequenas ***p*** dimensões
		-  i.e. p ≤ 4 and large-ish N.



## RSS ou SSR (Residual sum squares)
Valor que quantifica o quão dispersos estão os data points da linha de regressão. (Esta relacionado com o conceito estatístico de variância)
Somatório do numero de pontos de (x - x^)^2.
e = x - x^ -> Residual

## RSE (Residual Standard Error)
Refere-se à expectativa de quão distante os resultados das previsões podem estar do alvo real.

## **R² (Coeficiente de Determinação)**
Este coeficiente varia entre 0 e 1, onde 0 indica um modelo ineficaz e 1 um modelo perfeito. Valores entre 0.8 e 0.95 são considerados indicativos de bons modelos.

## Método dos mínimos quadrados (Least squares method)
Método para estimativa dos coeficiente da equação da regressão linear, que procura minimizar a sum of squared differences entre os dados observados e os valores estimados para a variavél dependente. 
- Modelo: $f(x)$
- Residual: $r_{i} = y_{i} - f(x)_{i}$
- Soma dos quadrados residuais: S = $\sum_{i=1}^{n} r^2_i$ -> ***(RSS)***

## FDR (False Discovery Rate) (Taxa de Falsas Descobertas) 
Termo usado em estatística para descrever a proporção esperada de erros do Tipo I (falsos positivos) entre todas as hipóteses que foram identificadas como significativas num conjunto de múltiplos testes estatísticos. Noutras palavras, o FDR é uma forma de controlar a taxa de erros cometidos quando se declara que um efeito ou associação é estatisticamente significativa, quando na verdade não é.

O método FDR envolve os seguintes passos:

1. Ordenar os valores p em ordem crescente.
2. Atribuir um rank a cada valor p, começando em 1 até m (o número total de testes).
3. Calcular um valor crítico (crit) para cada rank usando a fórmula $(i/m)*Q$, onde Q é a taxa de falsas descobertas que estamos dispostos a aceitar (geralmente 10%).
4. Identificar o maior valor p que é menor ou igual ao seu valor crit correspondente. Todos os valores p abaixo desse são considerados significativos, rejeitando a hipótese nula.



## Validação do modelo:
1. Ao obter os dados, dividimos em conjuntos de treino e teste (geralmente 70:30).
2. Minimizamos a média da soma dos quadrados dos resíduos (SSR - Sum Square Residual) para ajustar o modelo (treino).
3. Calculamos a soma média dos quadrados dos resíduos (MSS) nos dados de teste: 
	1. Por quê?
		1. Para observar como o modelo se comporta em dados não vistos anteriormente.
4. Se treinarmos e testarmos com os mesmos dados, o modelo pode ficar muito ajustado aos dados  de treino e ter um mau desempenho nos dados de teste, isso é chamado de **overfitting**.


## Prediction error 
- **Erro redutível:** parte do erro que pode ser reduzida, melhorando o modelo. Existe devido a discrepância entre o modelo real e o modelo estimado via função de regressão. Pode ser resolvido portanto com melhores modelos para determinada solução, com mais variareis de previsão ou usando melhores técnicas de estimativas. 
- **Erro irredutível:** parte do erro que não pode ser reduzida melhorando a eficiência do modelo. É causada pela variância inerente aos dados e/ou a ruídos introduzidos no processo de medição.


## Curse of dimensionality 
Refere-se ao fenómeno onde a performance de alguns algoritmos, como  o k-nearest neighbours se deteriora a medida que aumentamos o numero de variáveis de input. 
Isto acontece pois a medida que o numero de dimensões aumenta, o volume do espaço aumenta exponencialmente e os dados disponíveis ficam demasiado espalhados no espaço, e assim tornando mais difícil para encontrar padrões e relações nos dados e a precisão da estimativa diminui.

-- -------- ---- --

### Summary (Data Science - Teórica - 31-10-2023)

1. **Auto-avaliação e Midterm**: Foi mencionado que há uma auto-avaliação pendente até sexta-feira e que o exame intercalar (midterm) ocorrerá em duas semanas.
    
2. **Modelos em Produção e Teste T**: Discutiu-se a colocação de um modelo em produção e a utilização do teste T para obter o valor-p (p-value), que ajuda a determinar se existe uma relação estatisticamente significativa entre a variável preditora e a variável independente. A hipótese nula assume que não há relação.
    
3. **Nível de Confiança e Valor-p**: Foi estabelecido um grau de confiança de 95%, o que implica um ponto de corte de 5% (alpha crítico = 0.05). Se o valor-p for menor que 0.05, rejeita-se a hipótese nula. Por exemplo, um valor-p de 0.24 significa que devemos aceitar a hipótese nula, enquanto um valor-p de 0.0002 indica que devemos rejeitá-la, sugerindo uma relação de previsão no modelo.
    
4. **R² (Coeficiente de Determinação)**: Este coeficiente varia entre 0 e 1, onde 0 indica um modelo ineficaz e 1 um modelo perfeito. Valores entre 0.8 e 0.95 são considerados indicativos de bons modelos.
    
5. **Erro Padrão Residual (RSE)**: Refere-se à expectativa de quão distante os resultados das previsões podem estar do alvo real.
    
6. **Problemas de Classificação**: Foi discutido um exemplo de classificação de vinhos, onde a idade (jovem ou velho) e o sabor (madeira ou frutado) foram usados como variáveis. Utilizou-se um classificador binário (1,0) para categorizar os resultados como "happy" ou "sad". A regressão linear foi aplicada para traçar uma linha divisória, e os resultados foram analisados em termos de verdadeiros negativos (TN) e falsos negativos (FN), com o objetivo de aproximar a linha para minimizar esses valores.

7. **Matriz de Confusão**: Foi mencionado que essa matriz é populada com verdadeiros negativos e verdadeiros positivos, permitindo análises adicionais.

8. **Regressão Logística**: No contexto de um exemplo em que uma célula de gordura se transforma em neurônio, a regressão logística foi apresentada como um método de classificação. Foi explicado que, embora a regressão linear possa parecer adequada para a zona de conversão, é necessário calcular o sigmoid usando a regressão linear que entra na variável z do sigmoid. A função sigmoid é dada por $1/(1 + e^(-z))$ e é preferível à regressão linear para este tipo de problema de classificação.
    

Em resumo, a aula focou-se em conceitos estatísticos aplicados à construção e avaliação de modelos preditivos, com ênfase em testes de hipóteses, medidas de ajuste de modelo e métodos de classificação, como a regressão logística.
### Summary (Data Science - Teórica - 07-11-2023)

1. **Etapas do Modelo de Regressão**: O processo para criar um modelo de regressão linear inclui treinar o modelo, calcular os coeficientes, determinar os erros padrão para cada coeficiente, testar a hipótese nula e traçar os resultados.

2. **B^ vs. B**: A diferença entre B^ (coeficiente estimado) e B (coeficiente verdadeiro) é discutida, destacando a distinção entre valores estimados pelo modelo e valores reais.

3. **Erro Padrão Residual (RSE)**: RSE é uma estimativa do desvio padrão dos resíduos, indicando o quão longe os pontos de dados desviam da linha de regressão. Um RSE mais baixo sugere melhores previsões do modelo.

4. **R-quadrado (R²)**: R² é uma medida que explica a proporção da variância na variável dependente que pode ser prevista pelas variáveis independentes. Varia de 0 a 1, com 1 indicando um ajuste perfeito.

5. **Regressão Linear Múltipla**: A importância de validar o modelo e testar estatisticamente cada variável preditora contra a variável de resposta é enfatizada. A hipótese nula (de que o coeficiente é zero) e os valores-p são usados para determinar a significância dos preditores.

6. **Dados Retangulares**: O conceito de dados retangulares é mencionado, mas não explicado nas notas.

7. **Dados de Treino vs. Teste**: A abordagem típica de divisão 70/30 para dados de treino e teste é explicada, com 70% usados para treinar o modelo e 30% para testar seu desempenho.

8. **Interpretação do valor-p**: Um cenário é apresentado onde um valor-p de 0,2 é comparado com um nível alfa de 5% para decidir se aceita ou rejeita a hipótese nula para um preditor em uma regressão linear.

9. **Modelos de Classificação vs. Regressão**: A diferença entre esses dois tipos de modelos é discutida, com modelos de classificação lidando com variáveis de resposta qualitativas e modelos de regressão com quantitativas.

Tópicos adicionais abordados incluem:
- Regressão linear simples e múltipla.
- Os conceitos de intercepto (B0) e inclinação (B1).
- O uso de testes estatísticos para validar se as variáveis são bons preditores.
- O conceito de taxa de descoberta falsa (FDR) para lidar com múltiplos testes de hipóteses.
- Regressão logística, que lida com variáveis de resposta qualitativas e pode produzir probabilidades para modelos de classificação.

As notas também tocam na relevância do RSE e R² na avaliação do modelo, com o RSE sendo dependente do domínio e o R² independente do domínio. Um bom valor de R² é tipicamente entre 0,8 e 0,9. Para testes múltiplos, o método FDR é sugerido para ajustar o intervalo de confiança, e um procedimento para aplicar o FDR é delineado.

Por fim, a regressão logística é formalizada como um modelo onde a variável de resposta é qualitativa, e o conceito de máxima verossimilhança é usado para encontrar o ponto de corte que melhor separa as classes nos dados.

### Summary (FDR Caderno Resumo)

1. **Testes Múltiplos**: Realização de vários testes estatísticos simultaneamente no mesmo conjunto de dados.
    
2. **Erro Tipo I**: Erro estatístico que ocorre quando a hipótese nula é incorretamente rejeitada (falso positivo).
    
3. **Regressão Linear**: Modelo estatístico usado para prever o valor de uma variável dependente com base em uma ou mais variáveis independentes.
    
4. **False Discovery Rate (FDR)**: Proporção esperada de erros Tipo I entre as hipóteses rejeitadas em múltiplos testes estatísticos.
    
5. **Valores p**: Probabilidade de obter um resultado estatístico tão extremo quanto o observado, assumindo que a hipótese nula é verdadeira.
    
6. **Ajuste de Valores p**: Processo de modificação dos valores p em testes múltiplos para controlar o FDR e reduzir a probabilidade de erros Tipo I.
    
7. **Método FDR**: Técnica estatística para ajustar valores p em múltiplos testes, controlando a taxa de falsas descobertas.
    
8. **Procedimento de Benjamini-Hochberg**: Método comum de ajuste de valores p que controla o FDR em múltiplos testes estatísticos.
    
9. **Biblioteca Pandas**: Ferramenta de software em Python para manipulação e análise de dados, com estruturas de dados para manipular tabelas numéricas e séries temporais.
    
10. **`fdrcorrection`**: Função da biblioteca `statsmodels.stats.multitest` em Python que implementa o ajuste de valores p para controlar o FDR.
    
11. **Taxa de Falsas Descobertas (Q)**: Limite pré-definido para a proporção de falsas descobertas que um pesquisador está disposto a aceitar ao usar o método FDR.
    
12. **Valor Crítico (crit)**: Limiar calculado no método FDR que determina se um valor p é considerado estatisticamente significativo após o ajuste.



--- - ----- 

### Summary (Classification Slides)
#### 1. Classification
The task of predicting a qualitative response variable based on a feature vector. 
#### 2. Qualitative variables
Variables that take values in an unordered set, such as eye color or email type. 
#### 3. Feature vector
A vector of measurements or features used to represent an object or phenomenon. 
#### 4. Response variable 
The variable being predicted or classified. 
#### 5. Probabilistic classification
The task of estimating the probability that a feature vector belongs to each category in the response variable set. 
#### 6. Linear regression
A statistical method for modeling the relationship between a quantitative response variable and one or more predictor variables. 
#### 7. Logistic regression 
A statistical method for modeling the relationship between a binary response variable and one or more predictor variables. 
#### 8. Decision trees 
A non-parametric method for classification and regression that uses a tree-like model of decisions and their possible consequences. 
#### 9. Random forests 
An ensemble learning method that constructs a multitude of decision trees and outputs the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees. 
#### 10. Support vector machines (SVMs) 
A supervised learning model that analyzes data for classification and regression analysis. SVMs are used for classification, regression, and outlier detection.



---- - -  -
