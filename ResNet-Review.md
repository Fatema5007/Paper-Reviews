# ResNet paper study notes

Read the 2016 paper by kaiming he about deep residual learning. Basically I wanted to understand why deep neural networks fail after some layers. 

So the main problem they talked about is degradation. When we add too many layers (like 56 layers vs 20 layers), the model performance actually drops and training error
goes up. Its not because of overfitting.The real issue is that gradients vanish when going way too deep, so early layers just stop learning anything useful.

To solve this vanishing gradient stuff, kaiming he introduced identity shortcut connections. The formula is H(x) = F(x) + x. Here x is the raw input. Even if the
intermediate layers F(x) give zero gradients or fail to learn, the input x can still flow ahead through this bypass highway. It doesnt add extra parameters or make
it computationally heavy.

They tested this framwork on a 34-layer network to make it ResNet-34 and it worked way better than the plain model. Then they built ResNet-152. This model won 
1st place in ImageNet 2015 with a 3.57% error rate which is crazy good.

This is super important for my future research goals in medical imaging and oral cancer detection. Since medical image features need stable gradients across deep
networks, understanding these residual blocks gives me a solid foundation for building deep architectures later.
