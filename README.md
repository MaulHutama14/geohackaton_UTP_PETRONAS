# Geohackaton 2022 - Midnight Spirit

Author : <br>
+ [Maulana Hutama](https://www.linkedin.com/in/maulanahutama14/) <br>
+ [Loris Alif](https://www.linkedin.com/in/lorisalif/) <br>
+ [Hadyan Pratama](https://www.linkedin.com/in/hadyanpratama/) <br>
+ [Sathes Kumar](https://www.linkedin.com/in/skss/) <br>
+ [Stallone Teng](https://www.linkedin.com/in/stallone-teng-b417334a/) <br>

# Description - GAN Pix2Pix

Missing traces is one of a real-world problem that has been facing by geoscientist. One of the case is that there is gas chimney overlay above the horizon makes the surface below become blurry. By addressing this problem, we come up with solution using supervised machine-learning method called as Generative Adversiral Network (GAN) pix2pix. We are using this method since its applicaton is still new in geoscience problem.

pix2pix GAN model we used are based on the code by Jason Brownlee from his blogs on https://machinelearningmastery.com/

Original paper: https://arxiv.org/pdf/1611.07004.pdf <br>
Github for original paper: https://phillipi.github.io/pix2pix/

Generator:    
The encoder-decoder architecture consists of: <br>
encoder: <br>
C64-C128-C256-C512-C512-C512-C512-C512 <br>
decoder: <br>
CD512-CD512-CD512-C512-C256-C128-C64 <br>

In this page, we provide several item such as,
<ul>
  <li>environment in .yml format</li>
  <li>notebook file for example of the application in .ipynb (include generate training data)</li>
  <li>prediction Quality Control (frequency spectrume and x-correlation)</li>
</ul>

# Main Process
  
First thing first, we do not provide any data in this github page. But in the notebook code, we have already introduced the cell to import in .segy format using segysak. Then the training start by nullify some traces inside of our interest seismic data.
<p align="center">
  <img src="https://github.com/MaulHutama14/geohackaton_UTP_PETRONAS/blob/main/training_test.png" width="300" height="300">
</p>
By training default from the program, if you are using python with CUDA environment, it will need 20 - 30 minutes (if not, you will need around 1 hour++). The quality control of the data can be defined as two part, the first one is,
<ol>
  <li>There is less amplitude spectrum difference between the original and the predicted seismic data</li>
  <li>Cross-correlation between predicted and true data in the missing traces is having average at ~85%.</li>
</ol>
<p align="center">
  <img src="https://github.com/MaulHutama14/geohackaton_UTP_PETRONAS/blob/main/blind_test.png" width="250" height="150">
</p>
<p align="center">
  <img src="https://github.com/MaulHutama14/geohackaton_UTP_PETRONAS/blob/main/frequency_spectrume.png" width="300" height="250">
  <img src="https://github.com/MaulHutama14/geohackaton_UTP_PETRONAS/blob/main/x_correlation.png" width="300" height="250">
</p>
  
Altough in our usage we still using 256 x 256 pixels, we are encourage to the reader to try yourself to increase that pixels.

Big thanks to GeoHackaton 2022 committee to provide excellent competition and provide us powerful VM. 

Cheers,<br>
Midnight Spirit


