# About

This project is focused on creating a model for recognizing type of tea based on pictures. This project implements few different approaches:

* Classic models (SVM, Logistic regression) based on data obtained from histograms of picures

* Classic models based on PCA obtained from histograms

* CNN on quanized images

* Mulitlayer Neural Network based on histograms

* Multilayer Neural Network based on PCA from histograms

## Data

Data consits of pictures of two types of teas: green and black.
Pictures has been obtained from website of polish tea shop. Images has been quantizied, so they take up less space and are less power consuming when it comes to processing.

Example of input image (processed and downsized):

![image](https://user-images.githubusercontent.com/94312553/222429674-5d5e6fad-240f-4e41-822e-5799ca30b4d8.png)


number of black tea pictures: 93
number of green tea pictures: 70

Example of input image:

## Histogram

In order to use classic statistical models on pictures, histogram has been used. Each color channel has beed divided into 17 buckets containing number of pixels with given intensity of color. Therefore, for each picture there were in total 51 new features.

## PCA

Since the number of features increased dramatically, PCA has been used to reduce the dimensionality of the feature space.
From the principal components analysis, it turned out that 4 components explain more than 82% of variance, hence 4 components re used in further analysis.

![397eadb7-db07-4d19-8f97-44df24d1eaea](https://user-images.githubusercontent.com/94312553/222427420-a41c5c62-f302-4386-b202-6f2910004ce3.png)

## Classic models - PCA

First approach for classifying pictures was to use SVM and LogReg on data obtained from histograms.
Result of both models can be seen below.

**SVM**

![image](https://user-images.githubusercontent.com/94312553/222428326-eece93c4-b988-41db-8be5-bdfb2b3b9f21.png)


**Logistic Regression**

![image](https://user-images.githubusercontent.com/94312553/222428157-6b76f6cc-645d-4056-8b67-ef1d4c624ee8.png)

## Classic models 

Since results of models using PCA's were not satisfactory, it has been decided to use original histogram's data, as well.

**SVM**

![image](https://user-images.githubusercontent.com/94312553/222428877-fae567d8-ff78-453d-8777-c8bec09e08ce.png)


**Logistic Regression**

![image](https://user-images.githubusercontent.com/94312553/222428822-c477d41f-3ac2-44fa-b684-c4fbfd3ee2f8.png)

Unfortunatelly, it was even worse...

## CNN

After not so great result of classical aproaches, it has been decided to use neural networks. This part shows results of RNN trained on downsized pictures.

Example of (even more) downsized picture:

![image](https://user-images.githubusercontent.com/94312553/222429497-bc8b1a32-87a0-46e1-88a3-1fd59142fc34.png)

**Training process**

![image](https://user-images.githubusercontent.com/94312553/222430120-6136ce5c-3cad-463f-b9b4-38a0aa061ed9.png)
![image](https://user-images.githubusercontent.com/94312553/222430162-fb134f5c-79fb-4b9f-87c8-6c280761d3d4.png)

CNN gave really good results on test dataset. Details can be found in the picture below.

![image](https://user-images.githubusercontent.com/94312553/222430409-ef599b32-d275-406a-860c-9a774c573bfd.png)

## MLP

Since CNN gave good results, I decided to experiment with NNs a little bit more. In that part MLP has been used trained on original data based on histograms.

![image](https://user-images.githubusercontent.com/94312553/222430881-5020783e-9d21-4f83-8cce-deaddc15f5f7.png)
![image](https://user-images.githubusercontent.com/94312553/222430916-58f2867f-ed7b-40af-ada9-ae8162f9c3e0.png)

In that case training process were not stable at all, so result might be misleading, even though it looks really good.

![image](https://user-images.githubusercontent.com/94312553/222431120-9bc41eb1-475b-4182-872f-12eb5ef3eb2a.png)

## Conclusion

CNN seems to be the most suitable for this type of scenarions (not really suprising), but result of classical approches might be usefull as well, especially considering the facts that it takes much more time to train this model and it uses much less computing power.


