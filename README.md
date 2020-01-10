# NeurIPS

## Reproducibility Challenge @ NeurIPS 2019
This project is submitted to [Reproducibility Challenge @ NeurIPS 2019](https://reproducibility-challenge.github.io/neurips2019/). Reproducibility Challenge @ NeurIPS 2019 is the most recent edition of the reproducibility challenge for members of the machine learning community to dive deep into cutting-edge research by aiming to re-implement parts of a paper. This project is based on the paper [Learning Imbalanced Datasets with Label-Distribution-Aware Margin Loss](https://arxiv.org/abs/1906.07413) with the focus on algorithm re-implementation and baseline improvement. A general scheme for baseline improvement with learning rate step decay and triangular policy is proposed in this project.

## Abstract
Most state-of-the-arts classifiers assume a relatively balanced class distribution and equal mis-classification cost. Training with imbalanced data has encountered a significant difficulty of low attainable results. Although many previous work has addressed various strategies to tackle this issue, these techniques usually come with different drawbacks and the outcome is still very limited. Cao et al. introduced two new techniques, label-distribution-aware margin loss (LDAM) and deferred re-weighting(DRM), which have been claimed to acieve better performance gains over the existing techniques. In this work, we re-produced the baseline experiments reported in the authors' work with IMDB and CIFAR-10 benchmarks. We performed extensive hyper-parameter tuning on these models and outperformed the original reported results. We also proposed a general scheme for baseline improvement with learning rate step decay and triangular policy. Based on the improved results, we studied how different techniques affect the performance when learning imbalanced data, including class balanced re-weighting, class balanced re-sampling and borderline-SMOTE. 

## Experiment Result at a Glance
In this work, we reproduced and inspected a subset of the baseline experiments in Cao et al.'s work and extended the baseline experiments with SMOTE oversampling experiment. Our work consists of two groups of experiments: one groups was based on IMDB movie reviews and another one was based on CIFAR-10. With the same hyper-parameters, we produced similar results as reported in the original paper. We analyzed the learning behaviour for the baselines and proposed a scheme for hyper-parameter tuning to improve the baseline results. For IMDB experiments, the fine tuning of bidirectional LSTM was able to improve around 1\% compared to the top reported result. We also investigated in the performance of traditional linear models, such as Logistic Regression, Naive Bayes, etc. For CIFAR-10 experiments, our method of learning rate step decay with triangular policy in the last stage of training was able to increase the accuracy on all the baseline models. With stronger model performance, we performed detailed studies on these baseline models to understand how different techniques affect the performance when learning imbalanced data. Finally, we incorporate our scheduling method with deferred re-weighting (DRW). We demonstrate a process of finding the optimal DRW or DRS stage transition point. With the same experiment setting, our procedure was able to improve around 2\% compared to the reported results.

### Parameter Setting and Results for IMDB experiments
ERM: BatchSize = 128, Max Feature = 8000, Epoch = 2. Re-samping: BatchSize = 128, Max Feature = 10000, Epoch = 4. Re-weighting: BatchSize = 128, Max Feature = 10000, Epoch = 5. SMOTE: BatchSize = 128, Max Feature = 10000, Epoch = 3. Adam Optimizer with default setting. 
<p float="center">
    <img src="/results/re1.png" >
</p>

### Imbalanced CIFAR-10 Experiments Results
<p float="center">
    <img src="/results/re2.png" >
</p>



