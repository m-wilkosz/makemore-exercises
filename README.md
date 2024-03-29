### **Lecture 1**
[Video](https://www.youtube.com/watch?v=PaCmpygFfXo)\
Exercises:\
E01: train a trigram language model, i.e. take two characters as an input to predict the 3rd one. Feel free to use either counting or a neural net. Evaluate the loss; Did it improve over a bigram model?\
E02: split up the dataset randomly into 80% train set, 10% dev set, 10% test set. Train the bigram and trigram models only on the training set. Evaluate them on dev and test splits. What can you see?\
Answer: Dev and test losses are about the same. Both are slightly lower than the train loss, as regularization was applied during traininig.\
E03: use the dev set to tune the strength of smoothing (or regularization) for the trigram model - i.e. try many possibilities and see which one works best based on the dev set loss. What patterns can you see in the train and dev set loss as you tune this strength? Take the best setting of the smoothing and evaluate on the test set once and at the end. How good of a loss do you achieve?\
Answer: Greater regularization strength causes higher train loss. Dev loss reaches the minimum at ~0.005 and continues to raise as regularization strength rises. Too large regularization can cause underfitting. Best regularization strength allowed to achieve loss ~2.24.\
E04: we saw that our 1-hot vectors merely select a row of W, so producing these vectors explicitly feels wasteful. Can you delete our use of F.one_hot in favor of simply indexing into rows of W?\
E05: look up and use F.cross_entropy instead. You should achieve the same result. Can you think of why we'd prefer to use F.cross_entropy instead?
Answer: For efficiency and numerical stability.

### **Lecture 2**
[Video](https://www.youtube.com/watch?v=TCH_1BHY58I)\
Exercises:\
E01: Tune the hyperparameters of the training to beat my best validation loss of 2.2\
E02: I was not careful with the intialization of the network in this video. (1) What is the loss you'd get if the predicted probabilities at initialization were perfectly uniform? What loss do we achieve? (2) Can you tune the initialization to get a starting loss that is much more similar to (1)?\
E03: Read the Bengio et al 2003 paper (link above), implement and try any idea from the paper. Did it work?\
