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




| Attack generated from nth model  | 0 | 320 | 640 | 960 | 1280 | 1600 | 1920 | 2240 | 2560 | 2880 | 3200 | 3520 | 3840 | 4160 | 4480 | 4800 | 5120 | 5440 | 5760 | 6080 | 6400 | 6720 | 7040 | 7360 | 7680 | 8000 | 8320 | 8640 | 8960 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Src (benign) | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 | 22.3 |
| Src (attack)     | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 | 1.3 |
| Src accuracy degrades    | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 | 21.0 |
| TENT (benign) | 65.9 | 68.0 | 69.9 | 70.7 | 71.2 | 71.6 | 71.4 | 72.4 | 72.7 | 72.8 | 72.9 | 73.0 | 73.0 | 72.9 | 73.0 | 73.4 | 73.7 | 73.9 | 74.0 | 73.9 | 73.4 | 73.9 | 74.1 | 74.6 | 73.9 | 73.9 | 73.5 | 73.4 | 73.8
| TENT (attack)     | 17.3 | 19.1 | 20.0 | 22.3 | 23.5 | 26.0 | 28.1 | 28.9 | 29.6 | 31.7 | 32.2 | 33.2 | 33.1 | 33.5 | 35.0 | 35.2 | 35.6 | 36.1 | 37.6 | 37.8 | 38.5 | 38.9 | 38.7 | 38.9 | 39.9 | 40.1 | 40.9 | 40.7 | 40.2
| TENT accuracy degrades    | 248.6 | 48.9 | 49.9 | 48.4 | 47.7 | 45.6 | 43.3 | 43.5 | 43.1 | 41.1 | 40.7 | 39.8 | 39.9 | 39.4 | 38.0 | 38.2 | 38.1 | 37.8 | 36.4 | 36.1 | 34.9 | 35.0 | 35.4 | 35.7 | 34.0 | 33.8 | 32.6 | 32.7 | 33.6

The graph below shows the smaller gap of accuracy degradation from FGSM attack as we adapted model with more benign samples.
<img width="541" alt="Screenshot 2566-04-26 at 19 34 17" src="https://user-images.githubusercontent.com/31609767/234549898-e03436c9-0372-458a-b7ee-eab9d647195a.png">

We also explore the norm of the gradient of FGSM attack. 
The graph below shows the smaller norm of gradient from FGSM attack as we adapted model with more benign samples.

<img width="543" alt="Screenshot 2566-04-26 at 19 34 22" src="https://user-images.githubusercontent.com/31609767/234549915-a68cc987-c29c-432b-8dce-176207b015ad.png">

We can conclude that the adapted model become more and more robust to an attack. The more samples the model adapted, the more robust the model to the FGSM attack becomes.
