# What does epochs have to do with fitting?

During your training process, the network learns on the given data. The speed and amount it learns is dependend on many parameters. The one we are looking at here is the epoch. So what does epoch mean and how does it influence the learning-process?
The training loop consists of several steps (compare the pytorch tutorial page: https://docs.pytorch.org/tutorials/beginner/introyt/trainingyt.html):
- Loading the data
- Calculating predictions from the input batch
- Compares the predictions with the labeld data (calculating a loss)
- Calculates the backward greadients over the learning weights
- Performs one learning step through the optimizer

One cycle of this workflow is then called a epoch. Since the network is learning after each epoch, it becomes better and better at the task at hand. But why can this be a problem? Given enough time the network can learn arbitrary many features of the training data. This leads to a near perfect prediction of the training set, but is disatvantageous for the generalization. If that happens, it is called overfitting.
On the contratry, if the network doesn't have enough time, e.g. epochs, to learn the needed things out ouf the training data, it also won't be able to predict anything on the validation or test data.
So how can you identify overfitting, underfitting and right fitting?
 


## Overfitting

Overfitting occurs when a machine learning model learns not only the underlying patterns in the training data but also the noise and random fluctuations. As a result, the model performs very well on the training set but poorly on unseen data. This usually happens when the model is too complex relative to the amount or quality of training data or if the network was trained on too many epochs. Overfitting can be detected by monitoring a widening gap between training and validation performance. Common techniques to prevent overfitting include using simpler models, applying regularization, and increasing the size or diversity of the training dataset.

## Underfitting
 
 Underfitting happens when a machine learning model is too simple to capture the underlying patterns in the data. It results in poor performance on both the training set and unseen data. This often occurs when the model lacks the capacity to learn complex relationships or when it's not trained long enough. Underfitting can be recognized by high error rates and little difference between training and validation losses. To address underfitting, one can use more complex models, reduce regularization, provide more relevant features or increase the epochs to give the model more time to learn.

## Right Fitting
Right fitting, or good generalization, occurs when a machine learning model captures the underlying patterns in the training data without memorizing noise. The model performs well on both the training set and unseen (validation or test) data. This balance indicates that the model is neither too simple nor too complex for the task. It suggests the model has learned meaningful representations that generalize beyond the training examples. Achieving right fitting often involves careful model selection, appropriate regularization, enough training time (epochs), and sufficient, high-quality data.



```{tableofcontents}
```