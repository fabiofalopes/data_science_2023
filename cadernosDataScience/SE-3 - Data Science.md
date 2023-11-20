Q1.
	**a) Treinar o modelo:** Faze após feita a aproximação, em que avaliamos a performance do modelo face aos resultados esperados para o que está a ser modulado.
	**b) Extrair os coeficientes:** É o passo de para realização da regressão linear, em que estimamos os valores para os coeficientes B0 (beta 0) e B1 (beta 1).
	**c) Calcular os erros padrão para cada coeficiente:** valor pelo qual o coeficiente varia em diferentes casos.
	**d) Testar a hipótese nula de que cada coeficiente é zero:** Assumimos que para determinada relação linear entre predictor e variável independente, a influencia do predictor é nula, visto que para B1 (beta 1) = 0, o declive da recta do modelo é 0 pelo que rende a relação irrelevante entre as duas vereáveis. No caso de testarmos a hipótese nula e chegarmos a conclusão que de facto não se observa relação então aceitamos a hipótese nula, caso contrário rejeitamos e existe uma relação.
	**e) Determinar a forma final do modelo:** Após calcularmos os coeficientes betas, podemos chegar a equanção do modelo de regressão linear e deste modo podemos também representar-lo na forma gráfica.

>>>

Q2.
	Calculamos os RSE (Residual standard error) e o $R^2$ de modo a obter medidas que nos traduzam a fiabilidade do modelo. Como RSE nos dá uma mediada standard para o desvio de e (error na equação de regressão linear), para valores mais elevados do mesmo, iremos obter resultados mais imprevisíveis de acordo com o modelo real.

>>>

Q3.
	Neste caso rejeitamos a hipótese nula. Sendo o resultado da regressão linear o demonstrado, e com o B1 = 1.5, sendo o p_value = 0.041 e se queremos 95% de confiança, então: 
		- o p_value nunca pode ser maior que 0.05.
			- neste caso p_value < 0.05
	Logo rejeitamos a hipotese nula em favor do b1 calculado a partir deste processo de regressão linear.

>>>

Q4
	A principal diferença entre um modelo de regressão linear e um modelo de classificação é que o primeiro estima um modelo de aproximação de todos os pontos de uma relação e o segundo estima um modelo para divisão (classificação) em 2 amostras dos dados inseridos para o modelo.

>>>

Q5
	Num modelo de classificação, para casos em que temos amostras positivas que ficam na zona dos negativos chamamos falso positivo e falso negativo para o caso contrário. 

>>>
