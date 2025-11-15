# **Batch-then-Drain Trace**

## Abstract
We compare 4 implementations of a priority queue being BinaryHeapInVector, BinomialQueue, LinearBaseLine, and QuadraticOracle.
We test them using the batch-then-drain workload profile. It consists of inserting n elements at once and then extracting n elements all at once.
After running this trace generator, it generates trace files with a seed that's fixed to 23 and its results are represented in a chart.
In the chart, we see that linear base and binary heap have linear constant growth while binomial starts to suffer when having a larger N during the drain phase.



## Question
We ask how the different implementations will behave with inserting all elements at once and then extracting all at once. 


## Hypothesis
We expect that since were batching all at once and then draining all at once that the implementations that favor
inserting and deleting will outperform those that are weak in that field. 

## Method
The method used for this project follows the huffman trace very closely. We first create a file containing a random seed
and generate a random number of inserts. Then we insert an n number of values all at once, and after that's done, we extract 
an N number of values all at once. The file that is created is stored in a directory inside the trace folder. Our
harness reads those trace files and tests them using the four different implementations those being, BinaryHeapInVector, BinomialQueues,
LinearBaseLine, and Oracle. Our harness then outputs a csv file of each implementation that we use to see a chart 
of the runtime of our batch-then-drain trace with the four implementations. 

## Results
![](/Screenshot 2025-11-14 at 2.39.22 PM.png)
In this chart we can see a major trend with binomial queue. It started very strong however, it starts to suffer with larger data sets
and can't keep up with binary_heap and linear_base which stay consisted even with large date sets.

## Interpretation
The batch then drain profile works very well with implementations that prioritize delete and insert. BinaryHeap worked very well because 
insert and delete both run in O(log N) time meanwhile Oracle and Binomial Queue suffered because in Binomial Queues case it's merge cost for every insert and delete.
Therefore, we can interpret the batch then drain profile to be suiting for a certain type of implementations that favor inserting and removing/findmin.