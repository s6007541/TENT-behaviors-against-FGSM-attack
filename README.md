# TENT-behaviors-against-FGSM-attack
This project mainly observed the result of one of the common baseline of test time adaptation method, TENT.
Tent: Fully Test-time Adaptation by Entropy Minimization
https://arxiv.org/abs/2006.10726

FGSM attack : Fast gradient sign method
The fast gradient sign method works by using the gradients of the neural network to create an adversarial example. For an input image, the method uses the gradients of the loss with respect to the input image to create a new image that maximises the loss. 

https://www.tensorflow.org/tutorials/generative/adversarial_fgsm

The diagrams below show the experiment setting.
![Screenshot 2566-04-26 at 17 21 17](https://user-images.githubusercontent.com/31609767/234544103-d3928da3-b5c6-490b-a0f6-1a1d948ff261.png)
![Screenshot 2566-04-26 at 17 38 49](https://user-images.githubusercontent.com/31609767/234544114-cfff7581-8412-4463-83cc-d23deef94096.png)

The results of difference between accuracy of benign and accuracy of attacked samples are shown below.

| method  | Second Header |
| ------- | ------------- |
| Src     | Content Cell  |
| TENT    | Content Cell  |
