# Graph-Based-Feature-Selection-for-Dimensionality-Reduction
Graph Based Feature Selection is a new approach of reducing the dimensionality of a dataset using a Graph Based approach. The apporach tries to generate a Kruskal's minimum spanning tree of a graph where the features of the dataset are the vertices and the correlation among them are the weights of the edges. The edges having weights greater than the user defined threshold  are removed. Hence, reducing the dimension of the dataset.


Tools Used: Scikit-learn, Pandas, Numpy, Matplotlib, Networkx


# Steps performed to achieve dimensionality reduction via Graph Based Method:
1. Importing dataset and Data Preprocessing:
    - Naming the columns.
    - Imputation to treat Missing Values using imputer from scikit-learn library.
2. Normalization:
    - Values are rescaled so that they end up ranging between 0 and 1 using Normalizer from scikit-learn library.
    - Also known as min-max scaling.
3. Correlation matrix:
    - Correlation among the features are found using .corr() from pandas library.
4. Defining the Vertices and Weights:
    - The features or the columns are taken into a list to define Vertices.
    - Weights are stored into another list by extracting the upper triangular matrix from the correlation matrix.
5. ## The Graph Based Approach:
   ### Generating the Minimum Spanning Tree(MST) for the Graph using Krushkal's algorithm
      A spanning tree of a graph is a sub graph that is a tree and connects all the vertices without forming a loop. Number of vertices is same as the           original graph.
      Method:
      
      a. Sort all the edges in non-decreasing order of their weight.
      
      b. Pick the smallest edge. Check if it forms a cycle with the spanning tree formed so far. If cycle is not formed include this edge else discard it.
      
      c. Repeat Step b until there are (V-1) edges in the spanning tree.
      
6. Removing edges whose weights are greater than the threshold from the constructed MST
    - Cosidering the Threshold to be -0.31, the vertices associated with weight greater than this are dropped.
    - The remaining MST is printed after dropping the vertices.
7. The Final Reduced Dataset is displayed
