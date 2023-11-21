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


--- - - - - ---
O caderno aborda o problema dos testes múltiplos em estatística, especificamente no contexto de validar estatisticamente os coeficientes de um modelo de regressão linear. Quando se realizam múltiplos testes estatísticos, como os testes T para cada coeficiente βi, usando o mesmo conjunto de dados, aumenta-se o risco de rejeitar incorretamente a hipótese nula (erro Tipo I) devido ao acúmulo de probabilidades de erro em cada teste individual.

Para ilustrar, se realizarmos 30 testes com um nível de confiança de 95% para cada um, a confiança de que todos os testes estão corretos cai para 21%, o que é substancialmente menor do que o nível de confiança desejado. Para corrigir esse problema e recuperar o nível de confiança original, pode-se usar a técnica do False Discovery Rate (FDR), que ajusta os valores p para controlar a proporção esperada de erros Tipo I entre as hipóteses rejeitadas.

O método FDR envolve os seguintes passos:

1. Ordenar os valores p em ordem crescente.
2. Atribuir um rank a cada valor p, começando em 1 até m (o número total de testes).
3. Calcular um valor crítico (crit) para cada rank usando a fórmula (i/m)Q, onde Q é a taxa de falsas descobertas que estamos dispostos a aceitar (geralmente 10%).
4. Identificar o maior valor p que é menor ou igual ao seu valor crit correspondente. Todos os valores p abaixo desse são considerados significativos, rejeitando a hipótese nula.

O caderno também menciona um exemplo prático com 20 testes e sugere atividades para implementar o método FDR usando a biblioteca Pandas em Python e comparar com a função `fdrcorrection` da biblioteca `statsmodels.stats.multitest`, observando se o parâmetro α na biblioteca corresponde ao parâmetro Q do método FDR descrito no caderno.




FDR, ou "False Discovery Rate" (Taxa de Falsas Descobertas), é um termo usado em estatística para descrever a proporção esperada de erros do Tipo I (falsos positivos) entre todas as hipóteses que foram identificadas como significativas em um conjunto de múltiplos testes estatísticos. Em outras palavras, o FDR é uma forma de controlar a taxa de erros cometidos quando se declara que um efeito ou associação é estatisticamente significativo, quando na verdade não é.

O conceito de FDR é particularmente importante em pesquisas que envolvem a realização de um grande número de testes estatísticos simultaneamente, como em estudos genômicos, onde milhares de genes podem ser testados para associação com uma doença. Nesse contexto, aplicar um limiar de significância tradicional (como p < 0.05) sem ajuste pode levar a um grande número de resultados falsamente positivos.

Para controlar o FDR, são utilizados métodos de ajuste dos valores p, como o procedimento de Benjamini-Hochberg, que reajusta os valores p com base na ordem de sua magnitude e no número total de testes realizados. Isso permite que os pesquisadores limitem a proporção esperada de descobertas falsas, mantendo assim a integridade dos resultados da pesquisa.