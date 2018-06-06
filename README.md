# Toxicity-Challenge
This repository contains the various approaches to solve the Kaggle competion to identify toxicity of comments in social media.
https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge.
This competition is a multi-class classification challenge where users are asked to classify text into 6 different categories.

Overview:

1. I ran all my models in Google Colaboratory  https://colab.research.google.com/ which is a an absolutely free service running in cloud and provides a setup for running Machine Learning and Deep Learning projects. It is equipped with Python 3 and K80 GPU ,which can be run for 12 hrs continuously. For the Keras models that I ran ,used CuDNNLSTM and CuDNNGRU(Fast GPU cversion of native LSTM and GRU).

2.








|      Model                  | Private LB Score(25% Test Data)| Public LB Score(25% Test Data) 
| --------------------------- | -------------------------------| -------------------------------|
| Attention Model & Glove     |      0.9804                    |      0.9814
| Attention Model & ConceptNet|      0.9820                    |      0.9827
| Attention Model & FastText  |      0.9788                    |      0.9786
| Attention Model w/Data Augmn|      0.9781                    |      0.9782
| Pool Model w/Data Augm      |      0.9823                    |      0.9839
| With XGBoost                |      0.9696                    |      0.9703
