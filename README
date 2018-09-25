Disease Module Identification from Biological Interaction Networks Based on Singular Value Thresholding and Hierarchical Clustering

This is my solution (https://www.synapse.org/#!Synapse:syn7345978/wiki/407310) to Disease Module Identification DREAM Challenge (https://www.synapse.org/#!Synapse:syn6156761/wiki/400645)

Instructions:

1. How to directly run the code
The code is written in Python.
If you have installed Anaconda version of Python, then you do not need to install any additional packages.
If not, you may need to install the packages used in the code. 
The first seven lines of the code list all required packages, including numpy, scipy, and sklearn.

If you want to directly run the code without any changes and generate very similar results for final submission:
Please download the networks of sub-challenge 1 (https://www.synapse.org/#!Synapse:syn6188888) and put them in the directory subchallenge1/, 
and the networks of sub-challenge 2 (https://www.synapse.org/#!Synapse:syn6188889) and put them in the directory subchallenge2/.
Please do NOT change the file names, for example, 1_ppi_anonym_v2.txt

Now you can directly run the python code. And the results will be generated in the directory submitted/.
The .txt files are preditions. sub2_1000.txt is for subchallenge2. Other six .txt files are for subchallenge1.
The .pkl files are learned gene features (you can choose not to output them).


2. How to change the model parameters and perform experiments

The main function is:

sol_dream11(output_filename, input_filename='', M=None, include_diagonal = False, mat=None, directed = False, svd_k = 50, svd_maxiter = 100, svt_delta = 1.5, e=0.0001, svt_maxiter=100, save_feature=False, feature_filename='', n_neighbors = 100, n_clusters=1000, linkage='ward', module_size = 40, constraint2 = False, n_neighbors2=100)

## out_filename: a string, for example, 'submitted/1_ppi_480.txt'. This will save the preditions to the file name.
## input_filename: a string, here you can put the network filename, for example, 'subchallenge1/1_ppi_anonym_v2.txt'. If you want to preprocess the network data, then set the parameter M and/or mat.
## M: a 3*n numpy array (n is the number of lines in the network file). The first column is the source node, the second column is the target node, and the last column is the edge weight. It has the same format as the provided network files. 
## include_diagonal: True or False. If set True, we take the diagonal (all set to be 1) of adjacent matrix into consideration during SVT feature learning. In my final submission, I set it to be False for subchallenge1, but it should be better to set it to be True.
## mat: a N*N numpy array. Adjacency matrix. N is the number of the nodes in the network (NOT the number of lines in the network files). When you perform data preprocess, you can directly input mat without specifying input_filename and M. 
## directed: True or False. If True, the adjacency matrix will not be asymmetric. Otherwise, it will be symmetric. 
## svd_k: an integer. Top k largest singular values, e.g., 50, 100, 200, etc.
## svd_maxiter: an integer. The maximal number of iterations for svd. Default value: 100. Could be much higher. 
## svt_delta: a float number. The learning rate for SVT. Default: 1.5
## e: a float number. Error rate bound for stopping iteration. Default: 0.0001
## svt_maxiter: an integer. The maximal number of iterations for SVT. Default: 100. Could be much higher. 
## save_feature: True or false. If True, save feature files as a .pkl file.
## feature_filename: a string, eg, submitted/PPI1_feature.pkl. If save_feature=True, you need provide a file name.
## n_neighbors: an integer. The number of neighbors for connectivity matrix (add connectivity constraint to hierarchical clustering). Default: 100
## n_clusters: an integer. The number of clusters set for initial agglomerative clustering.
## linkage: {'ward', 'complete', 'average'}. Default: 'ward' 
## module_size: an integer. Used to determine the number of clusters for second level fine-grained hierarchical clustering. Default: 40. It is better to change this value for different networks.
## constraint2: True or False. If True, impose connectivity constraint for second level hierarchical clustering.
## n_neighbors2: an integer. If constraint2=True, we need also specify the number of neighbors to calculate connectivity matrix.


By changing the parameters of the this function, you can perform various experiments. 
Properly change the default parameters could get a much better results (since the default parameters for final submission have not been tuned)!


If you find any bug or have any comments, please contact Tianle Ma, tianlema@buffalo.edu

Thank you!
