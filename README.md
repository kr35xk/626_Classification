# 626_Classification

There are two parts of my code. The first part is binary-classification and the second part is multi-classification.

# Binary Classification

Firstly, I created a 'y' variable based on the score of 'activity' where 0 for static activities and 1 for dynamic activities and I would use it to classify each row. I checked that there's no 'NA' in the data, so I save some preprocessing work to do.

Then, I split the training data so I could have a training and testing data to see the accuracy of the results. I used two methods for this part, one is logistic classification and the other is random forest. Here, random forest serves as my baseline algorithm. I got an accuracy of 0.9992 which is already really high. Then, I ran the logistic model where I got an accuracy of 1. Since this is higher than the random forest result, I used logistic to predict final result for the testing data.

# Multiple Classification

Firstly, I created a 'y' variable based on the score of 'activity' where each y is the same as activity except that when activity is greater than 6, the score of y is 7. I also take away 'subject' and 'activity' since I don't think they would help with the training and testing process.

Then, I did feature selection by using correlation matrix to pick out the most correlated variables as I worry about collinearity, and I generated a dataset where the variables are not highly correlated. I also saved a dataset where the variables are all there, so with the two I could compare their training and testing result. I split the two dataset separately. 

I tried out many algorithms. 

The first one is logistic. I had two types of codes for logistic as there exist different methods in r online. For both methods, I applied it to both selected and full data. By comparison, the second method produced higher accuracy and for both methods, full data has higher accuracys.

The second one is decision tree. I tried three types of codes for decision tree as there exist different methods in r online. For the first one, I used cross validation to resample the data, grid over various maxdepth, and applied it on both selected and full data. The result wasn't good enough as the highest accuracy for both were less then 0.9. The same for the second and third approach as their result were nearly the same. Yet, still, full data has higher accuracys.

The third one is random forest. I applied it to both selected and full data. Both produced high accuracy from 0.97+ to 0.98+ and full data has a higher accuracy result.

The forth one is SVM. I applied it to both selected and full data while setting kernel to be 'linear' and cost to be 1. Both produced high accuracy from 0.96+ to 0.98+ and full data has a higher accuracy result.

The fifth one is Neural Network. I applied it to both selected and full data. Both produced accuracy from 0.93+ to 0.95+ and full data has a higher accuracy result.

The sixth one is KNN. I applied it to both selected and full data. Both produced accuracy from 0.93+ to 0.95+ and full data has a higher accuracy result.

Then, I did an ensemble of the best predicted results from each model, and used majority voting to pick out a new column of predicted results. I compared a few combination of choices by changing whether to use predicted result of random forest from a selected data or a full data, and whether to use predicted result of knn from a selected data or a full data, and whether to add results from both knn models. Based the accuracy result, I chose to ensemble the predicted results of the test data from each model trained by full data, and I added the predicted result of knn trained by a selected data, and also a random forest prediction that I submitted before which got an accuracy of 0.94+ which I think is okay and may help with the overall accuracy.

Finally, I saved the result into a separate txt file.
