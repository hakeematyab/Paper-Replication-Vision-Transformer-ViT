<!-- PROJECT LOGO -->
<div align="center">
  <a href="https://github.com/hakeematyab/Paper-Replication-Vision-Transformer-ViT">
    <img src="https://github.com/user-attachments/assets/dec6eba5-fd35-4b2a-b7d3-fa102bcce857" alt="Logo" width="350" height="350">
  </a>
</div>


# Paper Replication: Vision Transformer (ViT)
### Atyab Hakeem

This project replicates the results of the paper ["An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale"](https://arxiv.org/pdf/2010.11929). The goal is to validate the performance of Vision Transformer (ViT) on image classification tasks using CIFAR-10.

## Background

**Architecture Details - ViT-Base**
- Layers: 12  
- Hidden size: 768  
- MLP size: 3072  
- Heads: 12  
- Params: 86M  

**Training Details**
- Train Dataset: JFT-300M  
- Optimizer: Adam  
  - Beta1: 0.9  
  - Beta2: 0.999  
  - Weight decay: 0.1  
- LR Scheduler: Linear warmup and decay  
- Batch size: 4096  
- Dropout: Yes  

**Fine-tuning Details (Higher Resolution)**
- Fine-tune Dataset: CIFAR-10  
- Optimizer: SGD + Momentum  
- Batch size: 512  
- Callbacks: Early stopping

**Proposed Benefits**
- Outperforms CNNs with less compute  
- Hybrids (CNN inputs + Transformer) work well for smaller ViT variants but not for larger ones  

## My Replication

These are the details of my implementation:

- Framework: PyTorch  
- Optimizer: AdamW  
- Learning Rate: 3e-4  
- Weight Decay: 1e-3  
- Batch Size: 1024  
- Gradient Norm Clipping: 10.0  
- Scheduler: Cosine Annealing LR  
- Epochs: 142  
- Number of Parameters: **8.45M**  
- VCallbacks: Early stopping, MLFlow experiment tracking.
Training was performed on a CUDA-enabled GPU. The model architecture and hyperparameters were chosen based on the original paper and optimized to match the training setup as closely as possible. The training script used gradient clipping and a learning rate scheduler to stabilize the training process.

## Results

- **Validation Accuracy on CIFAR-10:** 70% (No pretraining)  

## Socials
### Atyab Hakeem
<a href="https://www.linkedin.com/in/hakeem-atyab/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="mailto:hakeem.at@northeastern.edu"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://github.com/hakeematyab" title="Hakeem Atyab on GitHub">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
