# Conceitos 

# Modelo de Regressão
Um modelo de regressão da-nos uma função que descreve a relação entre 1 ou mais variáveis independentes e uma resposta ou variável dependente (target value).

## RSS ou SSR (Residual sum squares)
Valor que quantifica o quão dispersos estão os data points da linha de regressão. (Esta relacionado com o conceito estatístico de variância)
Somatório do numero de pontos de (x - x^)^2.
e = x - x^ -> Residual

## RSE (Residual Standard Error)
Refere-se à expectativa de quão distante os resultados das previsões podem estar do alvo real.

## **R² (Coeficiente de Determinação)**
Este coeficiente varia entre 0 e 1, onde 0 indica um modelo ineficaz e 1 um modelo perfeito. Valores entre 0.8 e 0.95 são considerados indicativos de bons modelos.




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
3. Calculamos a soma média dos quadrados dos resíduos nos dados de teste: 
	1. Por quê?
		1. Para observar como o modelo se comporta em dados não vistos anteriormente.
4. Se treinarmos e testarmos com os mesmos dados, o modelo pode ficar muito ajustado aos dados  de treino e ter um mau desempenho nos dados de teste, isso é chamado de overfitting (sobreajuste).


-------- - - --
# Summaries 

## Ch2_Statistical_Learning
#### The regression function f (x)
The regression function f(x) is a mathematical function that describes the relationship between the input variables and the output variable in a predictive model. 
It can be defined for a single input variable or for multiple input variables. 
The regression function is used to predict the value of the output variable based on the values of the input variables. The ideal or optimal predictor of Y with regard to mean-squared prediction error is **$f(x) = E(Y|X=x)$**, which is the function that minimizes **$E[(Y − g(X))2|X=x]$** over all functions g at all points X=x. 

The total prediction error of a model can be decomposed into two components:
- The **reducible error** is the part of the error that can be reduced by improving the model. It is caused by the discrepancy between the true regression function and the estimated regression function. This error can be reduced by using more complex models, increasing the number of input variables, or improving the estimation technique. 
- The **irreducible error** is the part of the error that cannot be reduced by improving the model. It is caused by the inherent variability of the data and the noise in the measurement process. This error is irreducible because even if we had a perfect model that perfectly captures the true regression function, we would still have some error due to the noise in the data. 
The goal of Statistical Learning is to minimize the total prediction error by reducing the reducible error as much as possible, while acknowledging that there will always be some irreducible error that cannot be eliminated.

#### How to estimate f

So we cannot compute E(Y |X = x)!
 Relax the definition and let $f^(x) = Ave(Y |X ∈ N (x))$
where $N(x)$ is some neighbourhood of x.

Nearest neighbour averaging can be pretty good for small p
— i.e. p ≤ 4 and large-ish N .

#### Curse of dimensionality 
The curse of dimensionality refers to the phenomenon where the performance of certain algorithms, such as k-nearest neighbours, deteriorates as the number of input variables or dimensions increases. This is because as the number of dimensions increases, the volume of the space increases exponentially, and the available data becomes sparse. As a result, it becomes increasingly difficult to find patterns or relationships in the data, and the predictive accuracy of the algorithm decreases. This is a common problem in Statistical Learning, and various techniques have been developed to address it, such as feature selection and dimensionality reduction.

#### Assessing Model Accuracy
To assess the accuracy of a model, we can compute the average squared prediction error over the training data or the test data. 
The average squared prediction error is also known as the **mean squared error (MSE)**. 
The MSE measures the average of the squared differences between the predicted values and the actual values. A low MSE indicates that the model is a good fit for the data. However, computing the MSE over the training data may be biased towards more overfit models. Therefore, it is recommended to compute the MSE using fresh test data if possible.

Tr = $\left. Tr = \{xi , yi\} \right|_{1}^{N}$
We could compute the average squared prediction error  
over Tr:  $MSE_{Tr} = Ave_{i∈Tr}[yi − \hat{f} (xi)]2$
Instead we should, if possible, compute it using fresh test
data $\left. Te = \{xi , yi\} \right|_{1}^{M}$
$MSE_{Te} = Ave_{i∈Te}[yi − \hat{f} (xi)]2$

## Ch3_Linear_Regression

#### 1. Linear regression
A simple approach to supervised learning that assumes the dependence of Y on X1, X2, ..., Xp is linear. 
#### 2. Regression function
A function that describes the relationship between the dependent variable Y and one or more independent variables X. 
#### 3. Coefficient
A value that represents the slope of the regression line and indicates the strength and direction of the relationship between the dependent and independent variables. 
#### 4. Least squares method
A method used to estimate the coefficients of the regression equation by minimising the sum of the squared differences between the observed and predicted values of the dependent variable. 
#### 5. Assumptions of linear regression
The assumptions that the relationship between the dependent and independent variables is linear, that the errors are normally distributed, and that the variance of the errors is constant. 
#### 6. Multiple linear regression
A type of linear regression that involves more than one independent variable. 
#### 7. All subsets regression
A direct approach to deciding on the important variables in linear regression that involves computing the least squares fit for all possible subsets and then choosing between them based on some criterion that balances training error with model size. 
#### 8. Hierarchy principle
The principle that interactions are hard to interpret in a model without main effects, and that interaction terms also contain main effects if the model has no main effect terms. 
#### 9. Limitations of linear regression
The limitations that linear regression assumes a linear relationship between the dependent and independent variables, and may not be appropriate for non-linear relationships.

## Ch4_Classification

Classification problems are a type of supervised learning problem where the response variable Y is qualitative. For example, the response variable could be whether an email is spam or ham, or the digit class of an image. The goal of classification problems is to build a classifier C(X) that assigns a class label from a set of possible classes to a future unlabelled observation X. In addition to building a classifier, we also want to assess the uncertainty in each classification and understand the roles of the different predictors among X = (X1, X2, ..., Xp). There are various techniques for building classifiers, such as logistic regression, support vector machines, and decision trees

## Classification Slides
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
