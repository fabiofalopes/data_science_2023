
Temos auto-avaliação até 6ª
Midterm vai ser daqui a 2 semanas ~


Depois de termos 1 modelo:
	Podemos colocar modelo em prod:
		T test retorna o P value ?
			- Vou assumir que não existe relação entre predictor e independent var  (hipotese nula)

Grau de confiança : 95% ?
	ponto de corte 5% -> p_value < 0.05 para rejeitarmos hipótese nula

- alpha(critical) = 0.05 (95%)
- 
			p-value - representa prob de observar dados num universo definido na hipótese nula 


num exemplo em que o p_value = 0..24 temos que aceitar hipótese nula 


Se p_value 0.0002 rejeitamos a nula , em relação ao modelo 
é uma relação de previsão 

- R² 
	- Sempre entre 0 e 1 
		- 0 shit model
		- 1 perfeito 
	- Entre 0.8 e 0.95 normalmente são bons modelos

- Residual stdr error (RSE)
	-> Quando fazemos previsão, quão off target posso esperar o resultado? 


Problemas de **classificação** 

verificar exemplo dos slides

neste caso vimos na aula uma probelma de classificação de vinhos, 

y- age (young - old)
x goumet (wooden-fruty)

classificador (1,0) (sim,nao) (happy,sad)

traçamos uma linha linha (regressao linear) e assumimos resultamos acima da linha sao "happy" e por baixo "sad"

resultados abaixo da linha que sejam happy são (TN) ou (FN)
true negative e false negative 

vamos aproximar a reta para minimizar estes valores 

Confusion matrix -> popular com True negatives e true positives e nos permite a at



--- 
Regressão logistica , metodo de classificação 

Vimos na aula um exemplo em que um celula de gordura passa a neurónio como a densidade de protainas

y = 0 , 1 (nao neuronio , neuronio)

vimos que regressão linear embora possa parecer bem para a zona de conversão, temos que calcular o sigmoid usando a regressao linear que entra no z do sigmóide. ver forma grafica


sabendo que nao podemos usar regressao linear 

Sigmoid = 1/(1 + e^(-z))

-- - - - - - -

Prompt Summary of this class:

Na aula teórica de Data Science do dia 31 de Outubro de 2023, foram abordados os seguintes tópicos:

1. **Auto-avaliação e Midterm**: Foi mencionado que há uma auto-avaliação pendente até sexta-feira e que o exame intercalar (midterm) ocorrerá em duas semanas.
    
2. **Modelos em Produção e Teste T**: Discutiu-se a colocação de um modelo em produção e a utilização do teste T para obter o valor-p (p-value), que ajuda a determinar se existe uma relação estatisticamente significativa entre a variável preditora e a variável independente. A hipótese nula assume que não há relação.
    
3. **Nível de Confiança e Valor-p**: Foi estabelecido um grau de confiança de 95%, o que implica um ponto de corte de 5% (alpha crítico = 0.05). Se o valor-p for menor que 0.05, rejeita-se a hipótese nula. Por exemplo, um valor-p de 0.24 significa que devemos aceitar a hipótese nula, enquanto um valor-p de 0.0002 indica que devemos rejeitá-la, sugerindo uma relação de previsão no modelo.
    
4. **R² (Coeficiente de Determinação)**: Este coeficiente varia entre 0 e 1, onde 0 indica um modelo ineficaz e 1 um modelo perfeito. Valores entre 0.8 e 0.95 são considerados indicativos de bons modelos.
    
5. **Erro Padrão Residual (RSE)**: Refere-se à expectativa de quão distante os resultados das previsões podem estar do alvo real.
    
6. **Problemas de Classificação**: Foi discutido um exemplo de classificação de vinhos, onde a idade (jovem ou velho) e o sabor (madeira ou frutado) foram usados como variáveis. Utilizou-se um classificador binário (1,0) para categorizar os resultados como "happy" ou "sad". A regressão linear foi aplicada para traçar uma linha divisória, e os resultados foram analisados em termos de verdadeiros negativos (TN) e falsos negativos (FN), com o objetivo de aproximar a linha para minimizar esses valores.

7. **Matriz de Confusão**: Foi mencionado que essa matriz é populada com verdadeiros negativos e verdadeiros positivos, permitindo análises adicionais.

8. **Regressão Logística**: No contexto de um exemplo em que uma célula de gordura se transforma em neurônio, a regressão logística foi apresentada como um método de classificação. Foi explicado que, embora a regressão linear possa parecer adequada para a zona de conversão, é necessário calcular o sigmoid usando a regressão linear que entra na variável z do sigmoid. A função sigmoid é dada por $1/(1 + e^(-z))$ e é preferível à regressão linear para este tipo de problema de classificação.
    

Em resumo, a aula focou-se em conceitos estatísticos aplicados à construção e avaliação de modelos preditivos, com ênfase em testes de hipóteses, medidas de ajuste de modelo e métodos de classificação, como a regressão logística.