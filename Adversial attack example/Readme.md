## Adversarial Attack

Instead of running a large volume of examples like in Bao Wang etal (https://arxiv.org/abs/1811.10745), we train both the plain vanilla CNN and SNN to the same level accuraccy on both the MNIST and FASHION MNSIT dataset. We show that the SNN performs better facing the adversarial attack.

The folders contain pretrained models together with the parameter file. One can also train the model from scratch by using the scripts given in the folders accordingly.

#### Attack the pretrained models: plain CNN and SNN 
##### MNIST dataset
Both CNN and SNN are trained to the same accuracy on the test dataset (98%+), we attack the dataset with varying $\epsilon$
![attack_mnist](https://user-images.githubusercontent.com/107137651/177045711-82a90cb6-d16b-4e38-a53d-74f259a0bc72.png)
##### FASHION-MNIST dataset
Both CNN and SNN are trained to the same accuracy on the test dataset (90%+), we attack the dataset with varying $\epsilon$
![attack_fashion_mnist](https://user-images.githubusercontent.com/107137651/177045744-c54d7493-cce5-438a-a20f-2c23d2da1204.png)


#### Adversial game: plain CNN and SNN 
While the attacker meddles with the underlying data, the model retrains based on such data. We test this procedure over both the plain CNN and the SNN models. This attack-retraining process is repeated for 5 epochs for the entire dataloader. One observes that the SNN is more robust to the data attack, and this phenomenon is getting more pronouced with increasing $\epsilon$. 
##### MNIST dataset
![attack_mnist_game](https://user-images.githubusercontent.com/107137651/177045939-60197fd1-af4c-4a4d-9eed-845f2043818b.png)
##### FASHION-MNIST dataset
![attack_fashion_mnist_game](https://user-images.githubusercontent.com/107137651/177045945-dba2666f-4e66-4f81-b14d-fa12f62eb5f9.png)
