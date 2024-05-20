# Flickr8k-Image-Captioning

## creating an image captioning Deep learning model trained on Flickr8k dataset 
## for sample tuns and calculated loss and accuracies refer to [**Kaggle NoteBook**](https://www.kaggle.com/code/karimfathy054/image-captioning-models-cnn-lstm)

## Model Architecture:
experimented with 2 concepts for the architecture which are (injection model,Merge model) that are present in **[What is the( Role of Recurrent Neural Networks (RNNs) in an Image Caption Generator?](https://aclanthology.org/W17-3506) (Tanti et al., INLG 2017)** and **[Where to put the Image in an Image Caption Generator](https://arxiv.org/abs/1703.09137)
Marc Tanti (1), Albert Gatt (1), Kenneth P. Camilleri (1) ((1) University of Malta)**

### Injection model:

a CNN is used to extract image features out of the image as a vector that is used to (initiate Hidden states for RNN layer/use it as start of the sequence for RNN layer/concatenate it with word embeddings used in RNN sequence)

an LSTM layer is used for the RNN(layer) to train on sentences sequences

Teacher forcing method is used to train the lstm layer by giving it the substrings from the reference caption and expect the next word to that substring as an output

### Merge model:

a CNN is used to extract image features out of the image only

LSTM layer trains on sequences of words related to the given references (captions for images)

the output of LSTM layer is (added/concatenated)  to the resulted image feature vector and are passed to ad decoder

the decoder is a network that consists of fully connected layers with non-linear activation functions("relu","softmax")


