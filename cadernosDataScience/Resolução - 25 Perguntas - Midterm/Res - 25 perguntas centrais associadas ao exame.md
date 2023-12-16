### 1. **Por que queremos realizar testes estatísticos nos coeficientes de um modelo linear?**
R: Para determinar se os mesmos têm um impacto significativo na variável dependente

### 2. **O que é um teste estatístico?**
Testes estatísticos ou testes de hipótese são procedimentos que nos permitem aceitar ou rejeitar parâmetros determinada amostra, avaliando a relevância da influencia dos mesmo em determinado modelo.

São utilizados para determinar quais variáveis independentes (predictors) podem levar à rejeição da hipótese nula $H_{0}$, tendo em conta um nível de significância pré–estabelecido, num estudo da sua relevância para um modelo.

### 3. O que é uma hipótese nula e alternativa?
- Hipótese nula $H_{0}$: é a hipótese assumida como verdadeira para a construção do teste. É a teoria, o efeito ou a alternativa que se está interessado em testar.
- Hipótese alternativa $H_{1}$ : é considerada quando a hipótese nula não tem evidência estatística.
- Erro do tipo I (α): é a probabilidade de se rejeitar a hipótese nula quando ela é verdadeira.
- Erro do tipo II: é a probabilidade de se rejeitar a hipótese alternativa quando ela é verdadeira.

![[Pasted image 20231121002249.png]]

# 4. O que entendemos por aprendizagem estatística?



# 5. O que é um valor-p?
Numa regressão linear, o p_value é um valor que representa a probabilidade do coeficiente de determinada variável ser nulo de acordo com testes de hipótese aplicados ao modelo. 

**Nível de Confiança e Valor-p**: Foi estabelecido um grau de confiança de 95%, o que implica um ponto de corte de 5% (alpha crítico = 0.05). 
Se o p_value for menor que 0.05, rejeita-se a hipótese nula. Por exemplo, um valor-p de 0.24 significa que devemos aceitar a hipótese nula, enquanto um valor-p de 0.0002 indica que devemos rejeitá-la, sugerindo uma relação de previsão no modelo.

# 6. Qual é a diferença entre ajuste do modelo (RSE e $R^2$) e os testes estatísticos nos coeficientes?
Testes estatísticos nos coeficientes permitem-nos determinar a pertinência, ou não, de incluirmos certa variável no modelo de regressão calculando, através de testes estatísticos, medidas (p.e: p_value) que nos permitem avaliar se o coeficiente é nulo ou se tem algum peso para o modelo.

As medidas de ajuste de modelo (RSE e $R^2$) permitem-nos medir o quão bem o modelo representa os dados. 
**R² (Coeficiente de Determinação)**: Este coeficiente varia entre 0 e 1, onde 0 indica um modelo ineficaz e 1 um modelo perfeito. Valores entre 0.8 e 0.95 são considerados indicativos de bons modelos.
**Erro Padrão Residual (RSE)**: Refere-se à expectativa de quão distante os resultados das previsões podem estar do alvo real.

# 7. O que acontece quando aceitamos a hipótese nula para todos os coeficientes em um modelo linear?
Estamos a dizer que a relevância dessas variáveis independentes para o modelo linear é nula.

# 8. O que é um modelo de classificação, e qual é a principal diferença com um modelo linear?
Um modelo de classificação agrupa amostras de dados em classes, ou estados, valores (0,1) , ou booleanos (true , false), etc , através de modelos logísticos. 


# 9. O que queremos dizer quando afirmamos que um vetor de características X pertence a uma categoria?
Se um vetor de características X pertence a uma categoria, temo que com base nessas características, o objeto ou observação é representado por X é classificado ou identificado como pertencente a essa categoria específica. Logo nesse caso o modelo de classificação funciona correctamente.

# 10. O que queremos dizer quando afirmamos que um vetor de características X pertence a uma categoria com alguma probabilidade?
Com base nas caracteristicas de X, existe certa probabilidadwe de este pertencer a certa categoria.
É uma representação de incerteza ou vareabilidade na classificação.

# 11. Se tenho um modelo com três coeficientes, qual é a confiança que no resultado do conjunto de três testes estatísticos se para cada um o nível de confiança é 95%?
0.95 x 0.95 x 0.95 


# 12. O que é um erro do tipo I em estatística?
Erro do tipo I (α): é a probabilidade de se rejeitar a hipótese nula quando ela é verdadeira. 
Logo é, p.e. no contexto da regressão linear, ter em conta uma variavél independente como predictor no modelo, quando na realidade esta devia ou podia ser descartada dada a hipótese nula ser verdadeira. 

# 13. O que queremos dizer quando afirmamos que precisamos corrigir p_values devido a múltiplos testes?
É necessário corrigir ou ajustar os p values de forma a controlar a taxa de erro global, quando realizamos múltiplos testes estatísticos (o que aumenta o risco de erros de tipo 1) 

# 14. Qual é o papel da função sigmóide na regressão logística?
O papel dessa função é transformar valores lineares em probabilidades. Essencialmente dividindo a relação entre grupos ou classes. A função sigmóide mapeia qualquer valor entre 0 e 1. Logo util para classificadores binários. 

# 15. O que significa a expressão $E(Y|X=4)$?
Representa a estimativa para o modelo Y no ponto x = 4.

# 16. Quais são os dois métodos que temos para estimar o valor de Y dado um vetor de dados (características) X?
Regressão linear e regressão

17. Qual é a diferença entre epsilon e um resíduo em um modelo linear?
18. Como calculamos a soma quadrada dos resíduos para um dado modelo, dados alguns dados?
19. Qual é a diferença entre dados semi-estruturados e estruturados?
20. Explique o processo analítico inicial que devemos seguir, dado um conjunto de variáveis independentes candidatas e uma variável dependente, para preparar o treinamento de um modelo de regressão linear?
21. Por que dizemos que todos os modelos são imperfeitos?
22. O que entendemos por sobreajuste (overfit)?
23. Qual é a relação entre o intervalo de confiança para um coeficiente de um modelo linear e o erro padrão desse coeficiente?
24. Qual é a hipótese nula que testamos nos coeficientes de um modelo linear?
# 25. Por que não podemos simplesmente usar um regressor linear para um modelo de classificação com três possíveis resultados?
Num modelo de classificação a variavél dependente representa uma classe ou uma categoria enquanto que num modelo linear representa de uma forma continua no domínio dos dados uma estimativa para cada ponto. 