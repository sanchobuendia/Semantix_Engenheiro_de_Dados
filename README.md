# Semantix_Engenheiro_de_Dados
Semantix teste Engenheiro de Dados

## **Qual o objetivo do comando cache em Spark?**
### **R:** O comando cache tem o propósito de armazenar na memória, por exemplo um DataFrame que é lido, para que ele esteja disponível para ser usado sem a necessidade de lê-lo novamente. Sendo assim, o método cache( ) ê um comando para usar o nível de armazenamento padrão, que ê o StorageLevel. MEMORY_ONLY, para armazenar objetos na memória)

## **O mesmo código implementado em Spark é normalmente mais rápido que a implementação equivalente em MapReduce. Por quê?**
### R: A principal diferença entre Spark e MapReduce está relacionada em como eles processam os dados. Spark faz tudo utilizando a memória enquanto Mapreduce persiste os dados no disco. Por não precisar ler no disco os dados o Spark torna as operações muito mais rápidas.

## **Qual é a função do SparkContext?**
### R: Principal ponto de entrada para a funcionalidade Spark. Um SparkContext representa a conexão com um cluster Spark e pode ser usado para criar RDDs, acumuladores e variáveis de transmissão nesse cluster.

## **Explique com suas palavras o que é Resilient Distributed Datasets (RDD).**
### R: RDDs é uma coleção de objetos somente leitura, particionados em um conjunto de nós do cluster, que são criados por determinadas funções, como: map, filter, join, groupBy. Os RDDs suportam dois tipos de ações: Transformations (map, filter, join, union, etc) e Actions (reduce, count, first, etc).

## **GroupByKey é menos eficiente que reduceByKey em grandes dataset. Por quê?**
### R:O groupByKey agrupa os valores de cada chave no RDD em uma única sequência, o que também permite controlar o particionamento do par de valores-chave resultante do RDD. Esta operação pode ter um peso computacional muito grande se o dataset for muito grande. Caso seja necessário agrupar para executar uma agregação (como uma soma ou média) sobre cada chave, usar o agregateByKey ou o reduzirByKey fornecerá um desempenho muito melhor.

## **Explique o que o código Scala abaixo faz.**
'''val textFile = sc.textFile("hdfs://...")
val counts = textFile.flatMap(line => line.split(" "))
.map(word => (word, 1))
.reduceByKey(_ + _)
counts.saveAsTextFile("hdfs://...")'''

### R: O código em questão conta as palavras de um arquivo de texto. O código lê o arquivo setando o caminho até ele, separa (split) as palavras utilizando um espaço como condição (“ “), em seguida conta as palavras e salva o resultado em um arquivo de texto
