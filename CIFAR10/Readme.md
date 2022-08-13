## Training on CIFAR10 dataset
We show that our neural network with the new optimization procedure achieves 93~94% (which is human level accuracy) test accuracy on CIFAR10 dataset in 30 epochs. One can fine tune the 
neural network/parameters etc. to achieve better results. 

Simply fix 
$$\sigma = 0$$ or one can set it to a small constant to obtain similar results. 


Our NN structure is similar to ResNet9: it has nine layers with ResNet connection Blocks. The training time is 20+mins, while the testing accuracy is still comparable to the benchmark ResNet result. 

| |SNN| VGG16| ResNet18| ResNet18| ResNet101 | 
|--|-- |--|--|--|--|
|Accuracy|93.42% | 92.64\%|93.02\%|93.02\%|93.75\%|
