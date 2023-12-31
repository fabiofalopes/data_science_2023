# Conceitos 

# Parte 2

| Aspect                       | k-means Clustering                                                                 | Hierarchical Clustering                                                                                   |
|------------------------------|------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| Cluster Shape                | Spherical shape clusters based on distance.                                        | No specific shape; can handle various forms of similarity or distance.                                    |
| Number of Clusters           | Pre-specified number of clusters (K).                                               | Number of clusters can be determined by interpreting the dendrogram.                                      |
| Cluster Representation       | Mean or median can be used as the cluster center.                                  | Nested clusters arranged as a tree.                                                                       |
| Computation                  | Less computationally intensive, suitable for large datasets.                       | Computationally expensive due to the need for computing and storing a distance matrix.                    |
| Initialization               | Random choice of clusters, results may differ in multiple runs.                    | Results are reproducible.                                                                                 |
| Algorithm Type               | Non-hierarchical, partitioning method.                                             | Can be either divisive (top-down) or agglomerative (bottom-up).                                           |
| Cluster Overlap              | Non-overlapping subsets (clusters).                                                | Set of nested clusters that are arranged as a tree.                                                       |
| Suitability for Cluster Shape| Works well with hyper-spherical clusters.                                          | Applicable to any attribute types and can handle any forms of similarity or distance.                     |
| Advantages                   | - Convergence is guaranteed.<br>- Specialized to clusters of different sizes and shapes. | - Ease of handling of any forms of similarity or distance.<br>- Applicability to any attribute types.|
| Disadvantages                | - K-Value is difficult to predict.<br>- Doesn't work well with global clusters.    | - Requires the computation and storage of an n×n distance matrix, which can be slow for large datasets.  |

---

![image](https://github.com/fabiofalopes/data_science_2023/assets/67275812/c9df02fd-6383-47e5-a6c0-2ca04a7928ff)

---

![image](https://github.com/fabiofalopes/data_science_2023/assets/67275812/56842980-f5d4-4bf7-8998-8da95aaefc89)


![image](https://github.com/fabiofalopes/data_science_2023/assets/67275812/72e9a497-f60b-4ec1-9cd0-1287db38a040)


---

![images/Screenshot_20231219_180649](https://github.com/fabiofalopes/data_science_2023/assets/67275812/22787051-d2fb-497b-8845-b63d8a73255b)


## Hierarchical Clustering Python
```
import pandas as pd
import scipy.cluster.hierarchy as shc
import numpy as np
import sklearn
import statsmodels.formula.api as smf
```

```
# plot data
plt.figure(figsize=(12,8))
plt.scatter(home_data['longitude'], home_data['latitude'])
plt.show()
```

```
# Linkage and plot 

home_data = pd.read_csv('housing.csv')


Z = shc.linkage(home_data[['longitude' , 'latitude']],
                method='complete', # 'ward', 'complete', 'average', 'single'
                metric='euclidean'
               )

labels = shc.fcluster(
    Z,3,
    criterion='maxclust'
    )

plt.scatter(home_data['longitude'], home_data['latitude'],c=labels)
```

```
# dendrogram

# rc = shc.linkage(home_data[['latitude','longitude']], 'ward','euclidean')
# fig = plt.figure(figsize=(25, 10))
dn = shc.dendrogram(Z)
plt.show()

# or 
fig = plt.figure(figsize=(25, 10))
dn = shc.dendrogram(Z,color_threshold=1.5)
plt.show()
```

# K-means python

```

kmeans = KMeans(n_clusters=20).fit_predict(home_data[['latitude','longitude']])

# kmeans.labels_

plt.scatter(home_data['longitude'], home_data['latitude'],c=kmeans)

# print(kmeans)


````

# k-means {prof}

```

#gerando o dataframe X
X = home_data[['longitude','latitude']]`

#criando modelo kmenas para 9 clusters
#k=9
#kmeans tem como restricao indicar a quantidade de cluster logo na criação do modelo
kmeans = KMeans(n_clusters=9)

#inserir nova coluna no dataframe X com os labels gerados pelo Kmeans
X["Cluster"] = kmeans.fit_predict(X)

#criar scatterplot sobre o modelo Kmeans
sns.color_palette("tab10")
g = sns.scatterplot(data=X, x="longitude", y="latitude", hue="Cluster",palette = sns.color_palette("tab10"))

```


### Hierarchical Clustering: Practical Summary

**Key Concepts:**
- Hierarchical clustering is an alternative to K-means that doesn't require pre-specifying the number of clusters.
- It creates a dendrogram, a tree-like diagram that records the sequences of merges or splits.

**Interpreting a Dendrogram:**
- Each leaf represents an observation.
- Fusions of leaves into branches represent similar observations.
- The height of fusion indicates the level of dissimilarity.
- Observations that fuse at the bottom are similar; those near the top are quite different.
- Proximity on the horizontal axis does not imply similarity.
- Similarity is determined by the height at which the last common ancestor in the dendrogram is found.

**Creating Clusters from a Dendrogram:**
- Make a horizontal cut across the dendrogram.
- The number of distinct sets of observations below the cut represents the number of clusters.
- The height of the cut controls the number of clusters, similar to K in K-means.
- Clusters obtained by cutting at a given height are nested within clusters from a higher cut.

**Algorithm for Hierarchical Clustering:**
1. Start with each observation as its own cluster.
2. Find the pair of clusters that are least dissimilar and merge them.
3. Repeat step 2 until all observations are in a single cluster.

**Linkage Criteria (Defining Cluster Dissimilarity):**
- **Complete Linkage:** Maximal intercluster dissimilarity.
- **Single Linkage:** Minimal intercluster dissimilarity.
- **Average Linkage:** Mean intercluster dissimilarity.
- **Centroid Linkage:** Dissimilarity between the centroids of clusters.

**Choice of Dissimilarity Measure:**
- Often Euclidean distance is used, but other measures can be more appropriate depending on the context.
- Correlation-based distance measures similarity in terms of profile shapes, not magnitudes.

**Considerations for Practical Application:**
- The choice of linkage and dissimilarity measure can greatly affect the resulting dendrogram.
- Scaling variables to have standard deviation one before computing dissimilarities can give each variable equal importance.
- The decision to scale variables depends on the context and the nature of the data.

**When to Use Hierarchical Clustering:**
- When the number of clusters is not known a priori.
- When a nested set of clusters is meaningful for the analysis.
- When a visual representation of cluster formation is helpful.

**Limitations:**
- May yield less accurate results than K-means for a given number of clusters if the true clusters are not nested.
- The assumption of hierarchical structure might not always be realistic for the data.

**Practical Tips:**
- Examine the dendrogram to choose a sensible number of clusters.
- Be aware of the potential for different reorderings of the dendrogram; focus on vertical distances for similarity.
- Consider the nature of the data and the research question when choosing a dissimilarity measure and linkage method.

---





--- 

# Parte 1

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
