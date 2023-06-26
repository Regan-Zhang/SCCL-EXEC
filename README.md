# SCCL-EXEC

This repository contains the **execuatable code** for paper [Supporting Clustering with Contrastive Learning (NAACL 2021)](https://aclanthology.org/2021.naacl-main.427.pdf) Dejiao Zhang, Feng Nan, Xiaokai Wei, Shangwen Li, Henghui Zhu, Kathleen McKeown, Ramesh Nallapati, Andrew Arnold, and Bing Xiang.

#### Please refer to my blog https://blog.csdn.net/weixin_43594279/article/details/131250346?spm=1001.2014.3001.5502 for more details！

## Getting Started

### Dependencies:
    python==3.6.13 
    pytorch==1.6.0. 
    sentence-transformers==2.0.0. 
    transformers==4.8.1. 
    tensorboardX==2.4.1
    pandas==1.1.5
    sklearn==0.24.1
    numpy==1.19.5

### SCCL with explicit augmentations 

In additional to the original data, SCCL requires a pair of augmented data for each instance. 

The data format is (text, text1, text2) where text1 and text2 are the column names of augmented pairs. 
 See our NAACL paper for details about the learning objective. 

Step-1. download the original datastes from https://github.com/rashadulrakib/short-text-clustering-enhancement/tree/master/data

step-2. then obtain the augmented data using the code in ./AugData/

step-3 run the code via the following:

```python
python main.py  --objective SCCL --augtype explicit --eta 10 --batch_size 400 --max_iter 3000
```



## Citation:

```bibtex
@inproceedings{zhang-etal-2021-supporting,
    title = "Supporting Clustering with Contrastive Learning",
    author = "Zhang, Dejiao  and
      Nan, Feng  and
      Wei, Xiaokai  and
      Li, Shang-Wen  and
      Zhu, Henghui  and
      McKeown, Kathleen  and
      Nallapati, Ramesh  and
      Arnold, Andrew O.  and
      Xiang, Bing",
    booktitle = "Proceedings of the 2021 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies",
    month = jun,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.naacl-main.427",
    doi = "10.18653/v1/2021.naacl-main.427",
    pages = "5419--5430",
    abstract = "Unsupervised clustering aims at discovering the semantic categories of data according to some distance measured in the representation space. However, different categories often overlap with each other in the representation space at the beginning of the learning process, which poses a significant challenge for distance-based clustering in achieving good separation between different categories. To this end, we propose Supporting Clustering with Contrastive Learning (SCCL) {--} a novel framework to leverage contrastive learning to promote better separation. We assess the performance of SCCL on short text clustering and show that SCCL significantly advances the state-of-the-art results on most benchmark datasets with 3{\%}-11{\%} improvement on Accuracy and 4{\%}-15{\%} improvement on Normalized Mutual Information. Furthermore, our quantitative analysis demonstrates the effectiveness of SCCL in leveraging the strengths of both bottom-up instance discrimination and top-down clustering to achieve better intra-cluster and inter-cluster distances when evaluated with the ground truth cluster labels.",}

