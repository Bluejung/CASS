4# CASS
Cass is a software to cluster large-scale network based on Structure Similarity. 

# Method
Our method is developed using Hadoop 2.7.2, Java 1.8.0, Scala 2.10, and Spark 1.6.0

Our method has the following characteristics.
1)	It is a clustering method for large-scale networks in distributed systems.
2)	Changing the process of calculating structure similarity to a form suitable for distributed system environments using a triangle structure and join operations.
3)	Reducing the execution time by considering optimization approaches such as Bloom filter and join operation.
4)  It is possible to store the edge similarity calculated by the algorithm. If the user wants to re-experiment by changing the parameters, it is possible to analyze faster by using the edge similarity calculated previously.

# Usage
There are two main ways of executing our algorithm.

1) If you want to save intermediate result (edge similarity)

2) If you do not want to save intermediate results (edge similarity)




