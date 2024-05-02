# NLPProj
To reproduce our results you can just run the cells in order.
The main library we use is sklearn, but we also have some functions from pyenchant and graphviz.

The hyperparemeters we use for the random forest are $max_depth = 60$ and $random_state = 0$

Download Dataset Here: https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction 

For preprocessing we first run all of our feature functions over the entire data set (Note: this can take a few minutes) and then we create our train validate and test split using train_test_split from the sklearn library. Then we seperate the labels from the features and run our random forest classifier on them. Preprocessing for our collected data is the same process. 

Important detail: The last two cells are commented out because we used them to create graphics for our slides. They were run using a clf that was trained using a small dataset as to make them readable. If you run them as they are currently it will be applied to our clf that was trained on the 18k dataset and it will likely take forever or never finish.

**Results**
On our test set we achieved a Matthew's Coefficient of 0.6532969152617716 and an F1 score of 0.5925925925925926. However, these values varied a lot and because of the random nature of the model, you may see scores between .40 all the way up to .9 in the most extreme cases. We tested the average F1 and Matthew's Coefficient values over 50 iterations (where in each iteration we train a fresh model and test it) and the average was a matthew's coefficient of 0.6147827214902594 and an f1 of 0.5820644723586522

On our real world data we achieved an F1 score of .166 and a Matthew's coeefficient of .263. 

