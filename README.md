# Toxicity-Challenge
This repository contains the various approaches to solve the Kaggle competion to identify toxicity of comments in social media.
https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge.

Overview:
---------

1. This competition is a multi-class classification challenge where users are asked to classify text into 6 different     categories.
   Different platforms/sites can have different standards for their toxic screening process. Hence the comments are tagged in   the following five categories:

   1. toxic
   2. severe_toxic
   3. obscene
   4. threat
   5. insult
   6. identity_hate
   
  The tagging was done via crowdsourcing which means that the dataset was rated by different people.




2. I ran all my models in Google Colaboratory  https://colab.research.google.com/ which is a an absolutely free service running in cloud and provides a setup for running Machine Learning and Deep Learning projects. It is equipped with Python 3 and K80 GPU ,which can be run for 12 hrs continuously. For the Keras models that I ran ,used CuDNNLSTM and CuDNNGRU(Fast GPU cversion of native LSTM and GRU).



3. The dataset is an imbalanced one ,out of 159571 records present in dataset 143346 records are clean ,which means they were not classified to any of the category mentioned above.The classification across categories are mentioned below ,please note multiple tags are associated with comments.

   1. toxic         15294
   2. severe_toxic  1595
   3. obscene       8449
   4. threat        478
   5. insult        7877
   6. identity_hate 1405
   
4. For most of the models/embeddings that I tried pre-processing the data did not influence the score much for the Deep Learning models .   


5. Embedding : Used various pre-trained embedding vectors such as FastText, Glove Twitter,Google News Word2Vec, Resnet.
   Resnet seems to give the best result for a single model.
   
6. Concatenated Glove[300] and Resnet[300] vectors with a total dimension of 600 for the Embedding Layer ,did not give a better result .

7.Added NLTK POS Tag information to the concatenated vector of dimension 601 :
 Embedding Vector = Glove + Resnet + POS (300 + 300 + 1).
 This yielded a slighly better result in the private leaderboard.








|      Model                  | Private LB Score(25% Test Data)| Public LB Score(25% Test Data) 
| --------------------------- | -------------------------------| -------------------------------|
| Attention Model & Glove     |      0.9804                    |      0.9814
| Attention Model & ConceptNet|      0.9820                    |      0.9827
| Attention Model & FastText  |      0.9788                    |      0.9786
| Attention Model w/Data Augmn|      0.9781                    |      0.9782
| Pool Model w/Data Augm      |      0.9823                    |      0.9839
| With XGBoost                |      0.9696                    |      0.9703
| RandomForestClassifier      |      0.9404                    |      0.9396
| Logistic Regression         |      0.9739                    |      0.9736
