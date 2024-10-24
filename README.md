# Introduction 

code of HetGNN in KDD2019 paper: Heterogeneous Graph Neural Network 

# How to use

```python
python HetGNN.py [parameters]
python HetGNN.py --cuda 1  #enable GPU

#test data used in academic_test folder (academic-2 data used in this paper, T_s = 2012): (author) A_n - 28646, (paper) P_n - 21044, (venue) V_n - 18
#test data link: https://drive.google.com/file/d/1N6GWsniacaT-L0GPXpi1D3gM2LVOih-A/view?usp=sharing
```

# Data requirement

`a_p_list_train.txt`: paper neighbor list of each author in training data

`p_a_list_train.txt`: author neighbor list of each paper in training data

`p_p_citation_list.txt`: paper citation neighbor list of each paper 

`v_p_list_train.txt`: paper neighbor list of each venue in training data

`p_v.txt`: venue of each paper

`p_title_embed.txt`: pre-trained paper title embedding

`p_abstract_embed.txt`: pre-trained paper abstract embedding

`node_net_embedding.txt`: pre-trained node embedding by network embedding

`het_neigh_train.txt`: generated neighbor set of each node by random walk with re-start 

`het_random_walk.txt`: generated random walks as node sequences (corpus) for model training

# Model evaluation for different applications

1. link prediction (author-author collaboration, type-1)

    - step1: run `input_data_class.a_a_collaborate_train_test()` in `input_data_process.py` to set author-author collaboration train/test data

    - step2: run `[author collaboration link prediction] part` in `application.py` to obtain evalution result 

2. link prediction (author-paper citation, type-2)
    
    - step1: run `input_data_class.a_p_citation_train_test()` in `input_data_process.py` to set author-paper citation train/test data

    - step2: run `[author paper citation link prediction] part` in `application.py` to obtain evalution result 

3. node recommendation (venue recommendation)

    - step1: run `input_data_class.a_v_train_test()` in `input_data_process.py` to set author-venue train/test data

    - step2: run `[venue recommendation] part` in `application.py` to obtain evalution result 

4. node classification/clustering (author classification/clustering)

    - step1: run [author classification/clustering] part in `application.py` to obtain evalution result 

# Others

1. `raw_data_process.py`: raw data (academic_small.txt) processing and data preparation

2. `input_data_process.py`: generating het_rand_walk for model training, train/test data for different tasks, etc. 

3. `DeepWalk.py`: generating pre-train node embedding

4. If you find code useful, please consider citing our work.

Heterogeneous Graph Neural Network

Zhang, Chuxu and Song, Dongjin and Huang, Chao and Swami, Ananthram and Chawla, Nitesh V.

Proceedings of the 25th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining, KDD '19

5-5 For more information, contact: Chuxu Zhang (chuxuzhang@gmail.com)

