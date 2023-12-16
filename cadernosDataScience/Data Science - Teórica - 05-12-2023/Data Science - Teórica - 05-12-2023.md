Hierarchical clustering from scratch 

Quando temos um conjunto de data points:
- Temos alguma forma (função matemática) para calcular distancia entre 2 pontos;

Queremos saber se conseguimos agrupar data por clusters que os possam representar de alguma forma.

### Cluster analysis
- Clustering hierárquico (mais fácil)

Why it matters ? 
- Redes de aeroportos. Podemos inferir através de cluster analysis  que existem grupos de aeroportos que estão separados
- Political tweet analysis
- Wikipedia pages, paginas conseguem ser agrupadas em clusters que representam temas
- Autism risk genes, clusters de genes 

Cluster analysis: É analítico, não é estatístico.
-> Rigor (palavra chave) entre analítico e estatístico
	-> não temos p_value, etc.. 
		-> Analítica não informa decisão, ao contrario dos métodos estatísticos. 
		-> Visão das características que nos informam as condições ou características. Permite-nos aprofundar (go down the rabbit holes) que talvez valham a pena demonstrar 

Métodos analíticos + métodos estatísticos + machine leaning + AI formam esta amalgama de data science.

![[Pasted image 20231205193407.png]]

- Não estamos a olhar para relações entre variáveis independentes e dependentes.  
- Conjunto de data points, e uma distancia matemática  entre data point 
- Será que ha conjuntos de data points que a distancia entre si será menor que outros pontos. ou será que se agrupam
- Algoritmos não supervisionados pois não temos data points 

O que é um cluster? 
- O que é próximo e o que é distante? (o que definimos consoante a circunstancia)

# Importante elaborar entre diferencia entre clusters (analytical) vs métodos estatísticos 


![[Pasted image 20231205194009.png]]

Algoritmo de hierarchical clustering é simples
-> devemos entender e não tratar como black box 

Podemos usar o default: Distancia euclidiana.

Iteração (Processo de clustering)
Coordenadas dos 10 pontos e formula
- Inicializa procedimento de obtenção de clusters
- Inicialmente cada data point é o seu próprio cluster
- ![[Pasted image 20231205194851.png]]
- linkage na iteração 0 (single), quais as 2 clusters mais próximos (H-I e I-J)
- ![[Pasted image 20231205194922.png]]
- Iteração 1:
	- Mais próximos (H-I)-J
- ![[Pasted image 20231205195147.png]]
- Iteração 2
	- Se tivermos distancias iguais escolhe-se uma 
	- ![[Pasted image 20231205195245.png]]


No fim todos os data points dentro de 1 clusters 
Visível no dendrograma 

Nível de agrupamento deve maximizar a capacidade analítica do problema. Decisão subjectiva

## K-means Clustering

A priori indicamos qual o nível de clustering.

![[Pasted image 20231205200230.png]]
Ainda nao sao clusters neste paço. são apenas centroids (representante prototipico de um clusters, nao clusters)

Por cada ponto, qual o centroide mais proximo? 

no fim de iteracao 0 temos 3 clusters

![[Pasted image 20231205200858.png]]
temos que calcular as medias de (x,y) de cada clusters 

voltamos a perguntar a todos os pontos qual o centroid mais próximo 


# Fazer isto a mão!!



hieralchiacl clustering e k mean s sao metodos iterativos




