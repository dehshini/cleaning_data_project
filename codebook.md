codebook

y_train is the list of labels of the training set from the experimenters
y_test is the list of labels of the testing set from the experimenters
y_test1 is the activity labels with the activity IDs for the testing set
y_train1 is the activity lables with the activity IDs for the training set

features is the list of feature labels and their corresponding IDs
activities is the list of activities performed by the subjects

subject_test is the list of subject IDs for the test set 
subject_train is the list of subject IDs for the train set

X_train is the labeled training dataset with the subject who performed it and the activity performed
X_test is the labeled testing dataset with the subject who performed it and the activity performed

allsubjects is the merged training and testing datasets.

mean_std_features is a vector of integers indicating the indices of the mean/std features in the allsubjects set. 

mean_std_data is the dataset containing features that were calculated as a mean/standard deviation of other features.

tidy_data1 is the dataset with the average of each variable for each activity and each subject in a wide format. 