# Geohackaton 2022 - Midnight Spirit

Author :
Maulana Hutama ()
Loris Alif Syahputra
Hadyan Pratama
Sathes Kumar
Stallone Teng


Missing traces is one of a real-world problem that has been facing by geoscientist. One of the case is that there is gas chimney overlay above the horizon makes the surface below become blurry. By addressing this problem, we come up with solution using supervised machine-learning method called as Generative Adversiral Network (GAN) pix2pix. We are using this method since its applicaton is still new in geoscience problem.

pix2pix GAN model we used are based on the code by Jason Brownlee from his blogs on https://machinelearningmastery.com/

Original paper: https://arxiv.org/pdf/1611.07004.pdf
Github for original paper: https://phillipi.github.io/pix2pix/

Generator:    
The encoder-decoder architecture consists of:
encoder:
C64-C128-C256-C512-C512-C512-C512-C512
decoder:
CD512-CD512-CD512-C512-C256-C128-C64

In this page, we provide several item such as,
<ul>
  <li>environment in .yml format</li>
  <li>notebook file for example of the application in .ipynb (include generate training data)</li>
  <li>prediction Quality Control (frequency spectrume and x-correlation)</li>
</ul>
  
First thing first, we do not provide any data in this github page. But in the notebook code, we have already introduced the cell to import in .segy format using segysak. Then the training start by nullify some traces inside of our interest seismic data.

# image1

By training default from the program, if you are using python with CUDA environment, it will need 20 - 30 minutes (if not, you will need around 1 hour++). The quality control of the data can be defined as two part, the first one is,
  1. There is less amplitude spectrum difference between the original and the predicted seismic data
  2. Cross-correlation between predicted and true data in the missing traces is having average at ~85%.
  
Altough in our usage we still using 256 x 256 pixels, we are encourage to the reader to try yourself to increase that pixels.

Big thanks to GeoHackaton 2022 committee to provide excellent competition and provide us powerful VM. 

Regards,
Midnight Spirit


