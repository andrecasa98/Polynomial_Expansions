# Polynomial_Expansions

The following repo, include the implementation of a NLP model that can predict expanded formulas, given their factorized ones.

I first did some exploratory data analysis on the provided data in the EDA.py file.

To tackle the problem of sequence prediction, I've implemented a Seq2Seq encoder-decoder model, as the literature suggested. I've trained it for 100 epochs to try to maximize the prediction cross-entropy accuracy, with an overall result of 98.1% on the training set and 98.7% on the validation data (I achieved a better accuracy for the validation data using dropout layers).

The model predicts accurately the second-order and the zero-order terms of the expansions, but sometimes it fails in predicting the coefficients of the first-order term (the middle tokens). This is the consequence of using BiLSTM on the whole sequence, since the information gets poorer when propagated through the sequence. The solution would be to use a self-attention layer, which I haven't used since it's a method I'm still trying to get more confident with.
