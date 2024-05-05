## Data Splitting in Machine Learning
Why do we split the data? In order to train a model, we need two things: Training data and Testing data. Let's explore some methods to achieve this using Scikit-learn.

<h3>Simple Splitting:</h3>
<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/b1e84b62-1930-401a-86ca-546e85cd242f">

Using the sklearn library, we can import train_test_split method from sklearn.model_selection.
We can determine the percentage of the splitted data, for example, 80% for the training data and 20% for the testing data.

<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/cd004e8c-4331-46d4-86db-f8abf3579c16">

As easy as it is to use, it has many disadvantages:
•	Eliminating data that could have been used for training the model.
•	Producing results that can differ for a particular train-test split.
•	We can't easily adjust hyperparameters.
•	Not having a portion of data that can report a performance metric on truly 'unseen' data.

<h3>Train | Validation | Test</h3>

<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/49094575-c6e3-43a9-ae4d-b9c1f5bc27de">
If we want truly fair and final performance metrics, we should get these metrics from a final test set that we do not allow ourselves to adjust hyperparameters on.

The Train | Validation method helps us train the data and adjust the hyperparameters without worrying about data leakage from the test set.


In this method, we split the dataset into:
•	Training set
•	Validation set
•	Test set (Hold-out set)

We train the model on the training set and tune hyperparameters while assessing model performance using metrics. As a final step, we evaluate the model on the test set to determine its true performance.

To achieve this in Python with Scikit-learn, we simply call the train_test_split() function twice:

•	Once to split off a larger training set

•	Second time to split the remaining data into a validation set and a test set

<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/e3c1287e-cb84-4641-9ab3-a2bfb5dd9071">

---

<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/b355353e-735f-49bf-ba87-7377dce1ff75">

Now, we have training, validation, and test sets.


<h3>K-Fold Split Method</h3>

<img width="1163" alt="mlp_kan_compare" src="https://github.com/Ob1ida/Data-Splitting-in-Machine-Learning/assets/96666263/10e6ee35-9c4d-4ca5-97c9-366e3f51de92">


This method is unique because we can train the model on the entire dataset.


In this method, we determine how many folds we want. In the first fold, we split Fold 1 and train the model on the other parts, testing it on Fold 1. In the second fold, we repeat the same process.

After completing folding and testing, we have five error values. Now, we take the average and compare it to the error value of the test set.

To achieve this in Python, we can use the cross_val_score function, which allows for K-Fold cross-validation to be performed on any model.

<h5>Note:</h5> To see how these methods work with models, check the files.

