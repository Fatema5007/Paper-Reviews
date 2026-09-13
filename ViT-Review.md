# Vision Transformer (ViT) Paper Study Notes

This study explores the 2020 paper by Alexey Dosovitskiy et al. introducing the Vision Transformer (ViT), with a core focus on understanding how a pure Transformer architecture can be applied directly to images for image recognition tasks.

The main problem addressed in the paper is that computer vision has long been dominated by Convolutional Neural Networks (CNNs). While researchers tried combining self-attention with CNNs or replacing certain components, a pure Transformer relying solely on attention mechanisms had not been scaled effectively for large image recognition tasks.

To solve this, the authors introduced the Vision Transformer architecture. Instead of processing pixels or convolutions, the model splits an image into fixed-size patches (such as 16x16 pixels), flattens them, and maps them through a linear projection to treat them like words (tokens) in an NLP model. Standard learnable 1D position embeddings are added to retain spatial awareness, and an extra learnable class token is prepended to the sequence for final classification.

The study highlights a crucial trade-off regarding inductive bias: Vision Transformers lack the built-in inductive biases of CNNs, such as locality and translation equivariance. As a result, when trained on mid-sized datasets like ImageNet, ViT models tend to underperform compared to standard ResNets. 

However, the picture changes dramatically when models are trained on massive datasets (such as Google's JFT-300M or ImageNet-21k). The authors demonstrated that large-scale pre-training trumps inductive bias. When pre-trained at a massive scale and fine-tuned on downstream tasks, ViT achieves excellent results that match or beat state-of-the-art convolutional networks while requiring substantially fewer computational resources to train.
