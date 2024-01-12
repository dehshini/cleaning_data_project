====================================================
Human Activity Recognition Using Smartphones Dataset
====================================================

The experiments were video recorded and data labeled manually. The obtained dataset was randomly partitioned into two sets, 70% used for training and 30% for testing. These were saved as X_test.txt and X_train.txt.

########################################
Process of the run_analysis.r script ###
########################################
-read in the features names used by the researches
-label the activities performed 
-read in the subject identifier IDs from the test and train data sets.
-read the test data in as "x_test" with the features named appropriately  
-read the train data in as "x_train" with the features named appropriately
-the order of the activities performed in the train and test datasets are read in
-the order of the activities are merged with the corresponding dataset, data not sorted.
-the subjects who performed the various activities (identified by unique IDs) are added to the train and test datasets. These new datasets are labeled as x_test and x_train
-the activity labels are added to the datasets. The new sets are called x_test2 and x_train2
-combine the test and train datasets into one set called "allsubjects". Write this into a new txt file called "allsubjects.txt"

create tidyset with the mean and std features only
-a regular expression that matches "mean" or "std" anywhere in the feature names list is run and the new list of feature indexes is saved in the object "mean_std_features"
-In the "allsubjects" dataframe, the features occupy the 4th column to the last column. To get a dataframe that contains the features that were mean/std features, Subset the "allsubjects" dataframe and include the first three columns and the columns that match the mean/std regex. This dataframe is saved in an object called "mean_std_data"

Lastly, create a tidyset. group the features by subjects and the activity performed and return a mean of each feature. 
-the "mean_std_data" dataframe is grouped by subject(IDs) and the activity the subject performed.
-The mean of each column of data for the activity for each subject is returned. 
-This data is saved in an object "tidy_data1" and saved in a file "tidydata.txt"


##########
Summary ##
##########
These two datasets were combined into one large dataset called "allsubjects.txt"
For each record provided in the "allsubjects" dataset, there is :
- An identifier of the subject who carried out the experiment.
- An identifier of the activity performed
- a label of the activity performed
- A 561-feature vector with time and frequency domain variables, with each feature labeled according to how the experimenters labeled it 

The features selected for this database and their naming conventions were maintained from the experimenters datasets.

The following description was adapted from the original database.

====================================================================================
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz were captured. 

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
====================================================================================

