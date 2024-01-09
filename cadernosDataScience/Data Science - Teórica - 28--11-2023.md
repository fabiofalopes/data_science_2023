#### Overview e correcção do teste  
- Testes estatísticos vs $R^2$ e RSE  

- RSE 
	- Unidade de medida da var independente

- $R^2$ 
	- projeção (0-1) permite nos dizer se modelo bom ou mau (0.8 -> Bom) (0.2 -> mau)
	 - modelos no mesmo domino, se queremos comprar entre modelos é uma boa medida

- Outlier
	- Distante mais que 3 vezes o desvio padrão em relação a media
	- 75% a 90% deve estar da media (Expectativa)

- Estrutura rectangular, queremos fazer previsão de var dependente com vários potenciais predictors
	- Scatter plots
		- Observar relações ou tendências lineares
			- Caso encontremos essas relações, podemos avançar com o modelo
	- Não tem valor estatístico, mas é observável

- Resíduo: 1 resido. distancia entre data point e linha 

- Erro padrão (SE): taxa de erro do modelo. Consolidação numérica entre todos os "palitos" (resíduos). Medida numérica sintetizada que descreve a medida geral dos desvios.

- Modelo de regressão, o que significa quando reduzimos a soma de resíduos ao quadrado:
	-  Temos linha que queremos que fique o mais próximo possível de todos os pontos
		- É a linha mais próxima dos data points 

- Chapéu em cima da variável:
	- Estimativa via data

- Razão dados de teste quando produzimos modelo de regressão linear
	- Para determinar se podemos esperar que tenha a mesma performance em dados que nunca viu
	- Is this model generalizável or not? 

- Gráfico dispersão (Scatter plot)
	- Um gráfico de projecção de n variáveis para as quais existem data points, nas dimensões das variáveis que estão a ser analisadas.
	
- Qual é o teste de hipótese nula que testamos num modelos de regressão linear: 
	- Testamos o B para uma variável  $x_{i}$ e a variáveis dependente Y

- 95% confiança na nosso inferência
	- p_values = 0.051
	- P_VALUE: probabilidade de observarmos que a hipótese nula 
		- Como p_value < 0.05 logo aceitamos a nula
		- Ponto de corte. **alpha = 0.05**

- Erro de tipo 1: 
	- Quando rejeitamos a hipótese nula erradamente

- Classificar do item como verdadeiro mas no dados esta como falso: 
	- Falso positivo

- Explique de forma analítica $B{_0}$ (intercepção com origem) e $B_{1}$ (declive da recta) e p_values.
- Questão com os vários gráficos 
	- Devemos mencionar os testes de hipótese para cada Beta

- Testes, p_values e CRIT
	- Qual é a prob de alguma rejeição ser errada: $0.95^{16}$
	- Qual prob erro tipo 1 testes de hipótese: 
		- Perda rigor no modelo.
	- Identifique os p_values (tabela)
		- p_values <= CRIT (correspondente)

--- 
#### Hierarchical clustering 

Data points de um género (palavras etc)
medida de similaridade que correlacione pontos
	- medias das distancias

cada domínio vai ser a sua medida de similaridade 

trabalho de clustering:
	- algoritmo identify areas (grupos) 


- Regressão logística:  Algoritmos supervisionados
	 - Temos dados pelo qual podemos avaliar o modelo (ground truth)

- Neste caso (Clustering): Algoritmos não supervisionados 

- Clustering aglomerativo
	- Começos data points
	- agrupamento  gradual dos data points
	- ponto de corte pela qual definimos quantos clusters tempos


Conceito do **linkage**: que medida de proximidade para determinar distancia entre dois clusters 
- Single (Default)-> distancia entre pontos mais próximos 
	- Mais espalhado
- Complete -> par que tenha a distancia mais longe 
	- mais condensado 
- Average -> é a media de todos so pontos
- Central

- wait e ward : são mais complexos e nao sao o foco para ja


--- 

O resumo da aula teórica de Data Science do dia 28 de Novembro de 2023 aborda vários conceitos fundamentais em estatística e aprendizado de máquina, com foco em regressão linear e clustering hierárquico.

**Regressão Linear:**
- **Testes Estatísticos vs $R^2$ e RSE:** A aula discutiu a diferença entre usar testes estatísticos e medidas como o coeficiente de determinação ($R^2$) e o erro padrão da regressão (RSE) para avaliar modelos de regressão.
- **RSE:** Representa a unidade de medida da variável independente e é uma forma de quantificar o erro do modelo.
- **$R^2$:** Varia entre 0 e 1 e indica a proporção da variância explicada pelo modelo. Valores próximos de 1 indicam um bom ajuste.
- **Outliers:** São pontos distantes mais de 3 vezes o desvio padrão da média, com a expectativa de que 75% a 90% dos dados estejam próximos da média.
- **Estrutura de Dados e Scatter Plots:** A aula mencionou a importância de visualizar a relação entre variáveis através de gráficos de dispersão antes de avançar com a modelagem.
- **Resíduos e Erro Padrão (SE):** O resíduo é a distância entre um ponto de dados e a linha de regressão, enquanto o SE é uma medida agregada desses desvios.
- **Modelo de Regressão:** A minimização da soma dos resíduos ao quadrado resulta na linha de melhor ajuste.
- **Validação do Modelo:** A razão para usar dados de teste é verificar a capacidade de generalização do modelo para novos dados.
- **Teste de Hipótese Nula em Regressão Linear:** Testa-se a relação entre uma variável independente $x_{i}$ e a variável dependente Y.
- **Interpretação de p-values e Erros Estatísticos:** Um p-value abaixo de 0.05 (alpha) geralmente leva à rejeição da hipótese nula. Erros de Tipo 1 ocorrem quando a hipótese nula é rejeitada incorretamente.

**Clustering Hierárquico:**
- **Clustering:** A aula abordou o conceito de clustering hierárquico, um método de análise de agrupamento não supervisionado.
- **Medidas de Similaridade:** A importância de escolher uma medida de similaridade adequada para correlacionar pontos de dados foi destacada.
- **Algoritmos de Clustering:** Foram discutidos os algoritmos aglomerativos que agrupam pontos de dados de forma gradual.
- **Conceito de Linkage:** O método de linkage determina como as distâncias entre clusters são calculadas, com opções como single, complete, average e outras.

A aula também mencionou a regressão logística como um exemplo de algoritmo supervisionado, em contraste com os algoritmos de clustering não supervisionados. Além disso, foram discutidos aspectos práticos como a interpretação de gráficos e a análise de p-values em relação a um critério de significância (CRIT).