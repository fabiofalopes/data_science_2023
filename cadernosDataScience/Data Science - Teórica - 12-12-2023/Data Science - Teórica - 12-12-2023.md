Hierarchical clustering 
- From bottom -> up 
- Iteração termina quando só temos um grande clusters

Threshold: Relativo ao contexto
- Caso de aeroportos mundiais, por continentes, talvez queremos ver 5 clusters (5 continentes)

K-means
- Como posso particionar estes data points em k grupos em que não haja sobreposição!
- Faze de inicialização;
- Faze iterativa; 
- Condição de paragem;

1. Selecionar k data points aleatóriamente para seram os centroides iniciais; (Inicialização)
2. Perguntar a cada data point, qual o teu centroide mais proximo (1ª parte iterativa) -> agora fazes parte deste grupo.
3. Revisão do centroide - Todos os data point em cada clusters. Para cada dimensão de datapoint calculamos media. então o novo centroid passa a ser essa media calculada. (2ª parte iterativa)
4. Os data point em seguida vão saltando entre culsters a medida que o algotrimo estabiliza a posição dos centroides
5. Paragem quando, os centroides ja nao mudam e portanto estabilizam as clusters.


Quiz teórico e componente prática:
	- Componente teorica hiherachical crustering e k means
	- Fazer from scratch