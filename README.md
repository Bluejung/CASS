# CASS
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

[Option 1] --class kr.ac.yonsei.delab.DELScanReuseES --master yarn --deploy-mode cluster [Option 2] --num-executors [Option 3] [Option 4] --num-partitions [Option 5] --do-profile [Option 6] [Option 7] [Option 8]

2) If you do not want to save intermediate results (edge similarity)

[Option 1] --class kr.ac.yonsei.delab.DELScanFromFile --master yarn --deploy-mode cluster [Option 2] --num-executors [Option 3] [Option 4] --num-partitions [Option 5] --do-profile [Option 6] [Option 7] [Option 8]

# Option
Option 1 [Required] : Enter the directory of the spark-submit executable file.

Option 2 [optional] : This option is used to record events occurring on the spark. If you do not want to record the event separately, leave it blank.

Option 3 [optional] : This is the part to set the number of executor. If it is not listed separately, it is set to 2 by default.

Option 4 [Required] : Directory of executable file

Option 5 [Required] : This is the part to set the number of partition of graph data on spark. Basically, it is recommended to set it equal to the number of excutors set in Option 3, but if the partitioned graph data is too large to fit in memory, set it to a value larger than the number of excutors.

Option 6 [Required] : This is the part that sets the epsilon value used in the SCAN algorithm. The epsilon value is a threshold value for the structural similarity of the nodes included in the same cluster. If the epsilon is large, the structural similarity between the nodes included in the same cluster becomes large while the trade-off of the cluster size and the number of clusters becomes low .

Option 7 [Required] : It sets the Bloom-filter false-positive rate on spark. Bloom-filter is used to reduce unnecessary computation in algorithm process. The lower the false-positive rate, the more accurate the filtering, but the more resources it uses.

Option 8 [Required] : Enter the director of the graph data file to execute the algorithm.
