#### Em grupo - 8-10 Questões para o midterm. O que achamos?

1. Indique as etapas para fazer um modelo de regressão linear para determinado caso. Exemplo Sales por Price etc, no caso do modelo de advertising.
	1. Train the model -> calculate coefficients -> Calculate standard errors for each coefficient -> test null hypothesis -> plot  
2. Explique as diferenças entre  B^ e B ?
	1. Valor estimado e valor real
3. O que é o RSE?
	1. Uma estimativa do desvio padrão dos resíduos, representando a distância média que os pontos de dados se afastam da linha de regressão. Um RSE menor indica previsões melhores do modelo.
4. O que nos indica R²?
	1. Uma medida que explica a proporção da variância na variável dependente que pode ser prevista pelas variáveis independentes. Varia de 0 a 1, onde 1 indica um ajuste perfeito e 0 indica nenhuma relação entre as variáveis
5. Com os resultados de uma regressão linear múltipla, inicialmente feita: Sales ~ Price + US + Etc + Etc_2 indique quais predictors são mais relevantes para prever Sales num modelos de regressão múltipla.
	1. Validação do modelo
	2. Testar estatisticamente cada vareavel com a vareavel resposta
		1. H.Nula , coeficiente é 0? 
	3. p_value , prob que h.n. é ou nao aceite.
6. O que entende como dados rectangulares?
7. Explique a típica abordagem de 70% / 30% no que diz respeito a Training data vs testing data.
	1. Testing vai treinar modelo
	2. Deixamos 30% dados para testing de forma a que possamos trinar 
8. Se p_value = 0.2 numa determinada regressão linear, com um alpha = 5% (95%) aceita ou rejeita a hipótese nula para o seguinte predictor?
9. Apresente e fundamente a diferença entre modelos de classificação e regressão.

#### Brainstorm
- Regressão Linear simples e múltipla
-  B0 e B1 , intercept e slope 
	- Diferencas entre B^ e B -> Estimador / real
- RSE ou R²
- p_values
- Erro padrão 
- Residuais
- Intervalo de confiança, hipostese nula

- Etapas para treinar um modelo de regrassao
- Training data vs testing data. como abordar? 70% vs 30% 

- Estrutura rectangular (entidades / varáveis)

- Dados estruturados vs semi estruturados e nao estruturados

- Classificação : Falsos positivos vs falsos negativos 
- Diferenças entre modelos de classificação e regressão





--- 

Get the data -> Look at the data 

Modelar regressao linear (resposta / preditores)
Scaterplot

RSE e R² tipicamente sao calculado no testing data

Testes estatisticos para validar se varevaeis sao bons preditors


----
#### Quao bom é o modelo ?

RSE : 
- agarrada a escala do y 
- domain dependent
- dominio do problema, sera que RSE é relevante ou nao ? 

R² : 
- domain independent
- 0.8 - 0.9 , normalmente é um intervalor confiante aceitavel para o r squared


------  -- 

y = b0 + b1x1 + b2x2
95%
5% de aceitarmos H.N 

vamos ter 3 testes para p_value, etc

quando fazemos multiplos teste temos que regular o intervalo de confianda 


0.95 * 0.95 = 0.9025 , caso para 2 testes com dois Betas

0.95 ^ 30 = 20% 




Metodo: false discovery rate (FDR)

Cria nova tabela:
- ordenas todos os p_values, ascending, numa coluna (n)
- indices de cada posicao, coluna (i)
- crit (critical value) = (i/n)*Q , Q is for FDR parameter
- 
identifica qual o maior p_value que é igual ou menor ao seu respetivo crit

A partir dessa linha : tudo o que esta para tras, aceitamos a hipotese nula e a partir dessa linha rejeitamos




----- 
Do quadro 

### FDR 

a) Sort p_values (ascending)
b) Create column with indexes 
c) Compute CRIT = $(i/m)*Q$
d) Find the largest p_value that is less or equal to crit


----- 

### Formalizar regressão logistica: 

Varevael resposta não é numerica. é qualitativa. quermos etiquetas

feature vector, 1 ou mais vareaveis preditores , que nos indicam em que campo as vareaveis encaixam

outro tipo de saida pode ser uma probabilidade de algo acontecer , para determinado modelo de classificação 
	exemplo : probabilidade de happy
		se 40% happy
			entao 60% sad


Linear vs Logistic Regression 



Maximum likelihood 
-> onde existe o ponto de corte onde a maioria dos 0 ficam 0s e a maioria dos 1s passam a 1




--- - -- - - -

Prompt Summary of this class:

As notas da aula teórica de Data Science de 7 de Novembro de 2023 abordam vários conceitos e metodologias chave relacionados à análise de regressão (regression analysis) e avaliação de modelos (model evaluation), bem como a distinção entre modelos de regressão e de classificação.

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