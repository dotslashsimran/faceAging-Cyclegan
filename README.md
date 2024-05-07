# FaceAging using CycleGANs

This repo is heavily based on Original CycleGAN implementation. Most of my work involves adding code to better handle the dataset I am working with, and adding a couple of small features that enables transfer learning.

In this project, I have proposed a simple, yet intuitive deep learning model based on CycleGAN that can generate predictive images of people's look after certain years based on their current images, without the need of paired dataset.

## Dataset
IMDB-WIKI-500k+ face images with age and gender labels - contains 500k+ images of celebrities from IMDb and Wikipedia. The metadata of this dataset contains the date of birth of the person portrayed in the image and the date of which the image was taken.
Cross-Age Celebrity Dataset (CACD) - contains 163k+ images of 2,000 celebrities. "The images are collected from search engines using celebrity name and year (2004-2013) as keywords. We can therefore estimate the ages of the celebrities on the images by simply subtract the birth year from the year of which the photo was taken."
Modeling and Implementation
We picked the CycleGAN model because we think it can solve two major problems we face:

Making sure the original image and the translated image represent the same person. Adversarial losses alone cannot guarantee that the learned function can map an individual input to a desired output. CycleGan regularizes the space of possible mapping by adding the cycle-consistency losses. Combining this loss with the adversarial losses on the domains “young” and “old”, it made sure that the transformed images still represent the same person in the original images.

Obtain photos of one person that were taken at different ages is challenging and expensive. Therefore, we need an algorithm that can pass around domain knowledges between groups without paired input-output examples. CycleGAN can capture characteristics of faces of young people portraited in one image collection and figure out how these characteristics can be applied to those facial images in a collection of old people.
