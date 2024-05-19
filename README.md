# EncryptedTextClassifier

This repo stores notebooks of the experiments for the following task:

- Datasets: each entry in the dataset starts with a binary label (0 or 1) followed by a sentence-level ciphertext. 
- Task: make predictions on the unlabeled test set.

## Best Method
FastText + BiLSTM
- Trained a FastText model on all sentences in the training data from scratch to create the embedding matrix. Each ciphertext word has a vector representation generated by the FastText model. The sentence representation is the concatenation of the vector of each word in the sentence.
- In the classifier, there are two layers of bidirectional LSTM with 300 neurons and 0.2 dropout. Then there is a fully-connected layer with softmax activation to generate the result. The learning objective is to minimize the cross entropy loss.
- Training loss: 0.0687, training accuracy 0.9743, validation loss: 0.4797, validation accuracy: 0.8924.
  
<img width="600" alt="loss_acc_graph" src="https://github.com/cherylcy/EncryptedTextClassifier/assets/55656554/2059f39d-c386-4bbb-a022-9d38ba00b0ba">

## Other Methods
- TF-IDF + MLP
- LSTM
