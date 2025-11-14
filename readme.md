 The task for this project is to classify a short WAV audio file into one of five classes. The solution is a combination of feature-engineered ML pipeline and a neural network classifier.
Preprocessing Techniques

Label Encoding

In order to train, we converted class names into integer labels.

Feature Scaling =  StandardScaler is used to normalize all MFCC features. Neural networks tend to perform much better when the inputs are normalized.

Feature Engineering Approach

The main features used are the MFCC's, or Mel-Frequency Cepstral Coefficients.

These summarize important frequency information, and are widely used in audio processing.

Averaging the MFCC's along the time axis allows us to have a fixed length feature vector for each audio file.

For audio that is missing or unreadible, we insert a vector of zeroes to keep the feature size constant.


#Model Architecture
This model is a fully-connected feed-forward neural network with an input layer, dense hidden layer with ReLU activation, dropout for regularization, another dense layer and finally a classification layer with 5 output units.
#Strategy

Loss function: CrossEntropyLoss Optimizer: Adam Batch size: 32 Epochs: 50 Accuracy metric used on both train and validation sets Then we monitored validation accuracy and saved checkpoints for the best model. This will help prevent overfitting obviously.
