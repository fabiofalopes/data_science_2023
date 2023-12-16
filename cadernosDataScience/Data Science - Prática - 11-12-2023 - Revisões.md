
Como sabemos se conseguimos aplicar regressão logística
- Temos que ter uma coluna classificadora 

### Quando Podemos Aplicar Regressão Logística?

A regressão logística é um método estatístico usado para prever a probabilidade de uma variável dependente categórica. Para aplicar regressão logística, você precisa de:

1. **Coluna Classificadora (Variável Dependente Categórica):** A variável que você está tentando prever deve ser categórica, geralmente binária (por exemplo, sim/não, 0/1, verdadeiro/falso).
    
2. **Variáveis Independentes (Preditoras):** Podem ser contínuas ou categóricas. Se forem categóricas, geralmente são transformadas em variáveis dummy (indicadoras).
    
3. **Relação Linear:** Deve haver uma relação linear entre o logit da variável dependente e as variáveis independentes. O logit é o logaritmo da razão entre a probabilidade de ocorrência de um evento e a probabilidade de não ocorrência desse evento.
    
4. **Ausência de Multicolinearidade:** As variáveis independentes não devem ser altamente correlacionadas entre si.
    
5. **Tamanho da Amostra:** A regressão logística requer um tamanho de amostra relativamente grande para garantir a confiabilidade dos resultados.
    
6. **Independência das Observações:** As observações devem ser independentes umas das outras.

Qual é o Y da Reg. Logística: (Probabilidade)
- Resultado entre 0 e 1 : entre 0 e 1.
- Temos que definir um **ponto de corte** para classificar (Ex: o que esta acima de ponto de corte é up e abaixo é down) 

Coeficientes negativos contribuem negativamente para o calculo da probabilidade.

P Values e coeficientes são importantes para a interpretação

calcular prob 
e 
confusion matrix


--- 
100 % dados
- 70% -> Logit (Cria modelo a partir de 70% dos dasos)
- 30% -> Treino

| Confusion Matrix | Predito: 1 | Predito: 0 |
|------------------|--------------|--------------|
| Real: 1          | TN   (3)     | FP   (5)     |
| Real: 0          | FN   (2)     | TP  (10)     |


- **TN** é Verdadeiro Negativo (True Negative): casos em que o modelo previu corretamente a classe negativa.
- **FP** é Falso Positivo (False Positive): casos em que o modelo previu incorretamente a classe positiva.
- **FN** é Falso Negativo (False Negative): casos em que o modelo previu incorretamente a classe negativa.
- **TP** é Verdadeiro Positivo (True Positive): casos em que o modelo previu corretamente a classe positiva.

Norma colunas são a **truth** e as linhas os **modelo**

Diagonal principal: Onde da match

---

Clustering vs K-means (Unsupervised learning)



- Hierarchical Clustering
	- Métodos:
		- Single
		- Complete 
		- Average 

Qual a quantidade de clusters?
	Depende da interpretação..
	Temos que definir in threshold 