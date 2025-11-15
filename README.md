Student Info: Name: Anthony Villalobos Student ID: 008394627 Repo Link: https://github.com/villaloban/cs315Batch-Then-Drain

Collaboration & Sources: In this project I collaberated with classmates, the framework and emperical anlysis provided, and finally consulted chat gpt in errors I didn't know how to solve. The error that I consulted with AI was running my harness and compiling it. When I got an error I would ask it what other file I needed to add to the command and it gave me a list of files I needed to add in order for the compile command to work. I also looked up how to write to csv in order to get the csv portion of the project working as well. 

Implementation & Details: In this Project we were tasked implement a batch-then-drain profile to test different implementatis and performance of a priority queue such as BinaryHeapInVector, BinomialQueues, LinearBaseLine, and Oracle. A batch-then-drain profile uses a random seed and a fixed N number of operations. In this profile it inserts all at once an N number of times and extracts all at once an N number of times. This generates trace files with a fixed seed being 23 and those trace files get used by the harness. The hareness then reads those trace files and tests them using the 4 implementations mentioned earlier. Then writes the results to a csv file which gets used in order to see the runtime in chart format. 

Testing & Status: 
With the testing in this project I ended up having a lot of trials and errors with running it on the terminal. The way that I had it set up on clion was different then how the terminal would have liked. When trying to run the batch-then-drain main.cpp It wasn't reading the file and I had to change the way that file were reading from the directory. They were originally ../ since that's how clion was reading them but in the main they changed to not have it since they were in the current working directory. I also had this issue with how csvs were being written and how the harness was reading the trace files. I also had issue with how to compile the harness. I was compiling it like I would any other program but there were many other files that I had to include in there as well in order for it to compile. The commands I used in to run the harness 
include:  g++ -std=c++17 -O2 src/harness/main.cpp src/implementations/BinomialQueues/BinomialQueue.cpp src/implementations/BinomialQueues/BQnode.cpp src/implementations/LinearBaseLine/LinearBaseLine.cpp src/implementations/BinaryHeapInVector/BinaryHeapInVector.cpp src/implementations/Oracle/QuadraticOracle.cpp utils/comparator.cpp -I./implementations -I./utils -o harness

./harness

Output: 
Starting the throw-away run for N = 1024
Run 0 for N = 1024
Run 1 for N = 1024
Run 2 for N = 1024
Run 3 for N = 1024
Run 4 for N = 1024
Run 5 for N = 1024
Run 6 for N = 1024
Starting the throw-away run for N = 1024
Run 0 for N = 1024
Run 1 for N = 1024
Run 2 for N = 1024
Run 3 for N = 1024
Run 4 for N = 1024
Run 5 for N = 1024
Run 6 for N = 1024
Starting the throw-away run for N = 1024
Run 0 for N = 1024
Run 1 for N = 1024
Run 2 for N = 1024
Run 3 for N = 1024
Run 4 for N = 1024
Run 5 for N = 1024
Run 6 for N = 1024


And when running the batch-then-drain main.cpp the input was 
Input:  g++ -std=c++17 -O2 src/trace-generators/batch-then-drain/main.cpp -o batch_then_drain_generator
./batch_then_drain_generator

Output: 
File name: traces/batch-then-drain/batch-then-drain_N_13_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_1024_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_2048_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_4096_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_8192_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_16384_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_32768_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_65536_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_131072_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_262144_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_524288_S_23.trace
File name: traces/batch-then-drain/batch-then-drain_N_1048576_S_23.trace
