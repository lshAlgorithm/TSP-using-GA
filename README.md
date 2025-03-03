# Traveling-Salesman-Problem-using-Genetic-Algorithm
Genetic algorithms are heuristic search algorithms inspired by the process that supports the evolution of life. The algorithm is designed to replicate the natural selection process to carry generation, i.e. survival of the fittest of beings. Standard genetic algorithms are divided into five phases which are: 
 

    1.Creating initial population.
    2.Calculating fitness.
    3.Selecting the best genes.
    4.Crossing over.
    5.Mutating to introduce variations.

These algorithms can be implemented to find a solution to the optimization problems of various types. One such problem is the Traveling Salesman Problem. The problem says that a salesman is given a set of cities, he has to find the shortest route to as to visit each city exactly once and return to the starting city. 

Approach: In the following implementation, cities are taken as genes, string generated using these characters is called a chromosome, while a fitness score which is equal to the path length of all the cities mentioned, is used to target a population.
Fitness Score is defined as the length of the path described by the gene. Lesser the path length fitter is the gene. The fittest of all the genes in the gene pool survive the population test and move to the next iteration. The number of iterations depends upon the value of a cooling variable. The value of the cooling variable keeps on decreasing with each iteration and reaches a threshold after a certain number of iterations.

### Algorithm: 
 

      1. Initialize the population randomly.
      2. Determine the fitness of the chromosome.
      3. Until done repeat:
          1. Select parents.
          2. Perform crossover and mutation.
          3. Calculate the fitness of the new population.
          4. Append it to the gene pool.


### Pseudo-code: 
 
        Initialize procedure GA{
            Set cooling parameter = 0;
            Evaluate population P(t);
            While( Not Done ){
                Parents(t) = Select_Parents(P(t));
                Offspring(t) = Procreate(P(t));
                p(t+1) = Select_Survivors(P(t), Offspring(t));
                t = t + 1; 
            }
         }
         

An example of running the program:


![222](https://user-images.githubusercontent.com/45950266/153172517-3a157d43-1521-4b81-afc1-6bf7cc53ff4f.png)

         
The description was from geeksforgeeks website.

# Adoption to *Intelligent control*
## Seven steps for GA
1. 确定决策变量及各种约束条件，即确定出个体的表现型X和问题的解空间；
   1. 决策变量：城市访问顺序（eg. $1->2->4->3->1$ ）
   2. 解空间：$(n-1)!$ 个闭环的、仅访问一次的解组成的解空间
2. 建立优化模型，即确定出目标函数的类型及数学描述形式或量化方法；
   1. 建模成优化问题：最小化 $J(x)$
   2. $J(x)=\sum_{i=1}^{n-1}d(x_i,x_{i+1})+d(x_n,x_1)$
3. 确定表示可行解的染色体编码方法，即确定出个体的基因型x及遗传算法的搜索空间；
   1. 编码成python列表(eg. `[1, 2, 4, 3]`)
   2. 进一步生成`population`(作为x)
4. 确定个体适应度的量化评价方法，即确定出由目标函数值J(x)到个体适应度函数F(x)的转换规则；
   1. $F(x) = \frac1{J(x)}$
5. 设计遗传算子，即确定选择运算、交叉运算、变异运算等遗传算子的具体操作方法；
   1. 选择运算：sort
   2. 交叉运算：corssover
   3. 变异运算：mutation
6. 确定遗传算法的有关运行参数，即M,G,Pc,Pm等参数；
   1. M：种群数
   2. G：迭代数
   3. Pc：Possibility of crossover
   4. Pm: Possibility of mutaion
7. 确定解码方法，即确定出由个体表现型X到个体基因型x的对应关系或转换方法。
   1. `[1, 2, 4, 3]`-> `1->2->4->3->1`