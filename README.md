# Macro-Micro-Fusion-Network
WThis is our Pytorch implementation for our WWW 2021 full paper:
> Shuqing Bian, Wayne Xin Zhao, Kun Zhou, Xu Chen, Jing Cai, Yancheng He, Xinji Luo, and Ji-Rong Wen (2021). "A Novel Macro-Micro Fusion Network for User Representation Learning on Mobile Apps." In WWW 2021.


## Overview
we presented a Macro-micro Fusion Network **MFN** for user representation learning on mobile apps. We proposed two major extensions for information fusion between macro and micro views. First, we designed a fusion network that is able to align the semantics of app categories with those of item categories. Second, we further utilized the mutual information maximization technique to improve the learning of the fusion network. Extensive experi- ments conducted on three downstream tasks have demonstrated the effectiveness of our proposed approach.

<img src="https://github.com/fancybian/Macro-Micro-Fusion-Network/blob/main/MFN_model.png" width = "800px" align=center />

## Requirements
- Python 3.6
- Pytorch >= 1.4

Notice: For sequencial recommendation models, we use the first version of RecBole v0.1.1 to do our experiments. The more details are on [RecBole](https://github.com/RUCAIBox/RecBole). 


## Parameter Settings
For user activity prediction and user attribute prediction, we adopt the evaluation metrics including AUC, Accuracy, Precision, Recall and F1. we split the dataset into train, validation, and test sets with an approximate ratio of 8:1:1. For item recommendation, we employ Top-k Hit Ratio (HR@k), Top-k Normalized Discounted Cumulative Gain (NDCG@k) to evaluate the performance. We report results on HR@{5, 10} and NDCG@{5, 10}, we apply the leave-one-out strategy for evaluation. Concretely, for each user interaction sequence, the last item is used as the test data, the item before the last one is used as the validation data, and the remaining data is used for training.

The dimensionality of embeddings (including items and apps) is set to 200. We set the number of Transformer layers is set as 2. We use the Adam optimizer with a learning rate of 0.001 on GPU (TITAN Xp), where the batch size is set as 256 and 512 in the training and the evaluation stage, respectively. 


## Acknowledgement
Any scientific publications that use our codes should cite the following paper as the reference:
````
@inproceedings{Bian-WWW-2021,
    title = "A Novel Macro-Micro Fusion Network for User Representation Learning on Mobile Apps",
    author = {Shuqing Bian and
              Wayne Xin Zhao and
              Kun Zhou and
              Xu Chen and
              Jing Cai and 
              Yancheng He and
              Xinji Luo and
              Ji{-}Rong Wen},
    booktitle = {{WWW}},
    year = {2021},
}
````
If you have any questions for our paper or codes, please send an email to bianshuqing@ruc.edu.cn.
