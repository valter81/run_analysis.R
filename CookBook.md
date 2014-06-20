CookBook
Dataset and variable description  
=============

Both files test and trainning contains Data Sets of an experimentcarried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist.

Using the Samsung Galaxy SII embedded accelerometer and gyroscope, was captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

For each record in the dataset in each file -training and testing- it is provided as an attribute information:

Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration
Triaxial Angular velocity from the gyroscope
A 561-feature vector with time and frequency domain variables
Its activity label
An identifier of the subject who carried out the experiment



The Input dataset includes the following files:
=========================================

- 
'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 


Procedure
=================

1.  We need to read X_train.txt, Y_train.txt, and subject_train.txt files from the data folder where they are located, and store them in trainData, trainLabel and trainSubject variables. The same procedure must be done for X_test.txt, Y_test.txt and subject_test.txt and store them in testData, testLabel and testsubject variables

2. We need to concatenate the test and train Data. In order to make this happen, concatenate testData to trainData into a dataframe simply called Info. Also, the subjects and the labels need to be contatenated too; therefore, we need to concatenate testSubject and trainSubject to a subject data frame; and the trainLabel and testLabel to a label data frame

3. We need to read the features.txt file and select only the measurements on the mean and standard deviation and place them in to a vector variable called features; then we need to clean the names of the features selected  -Remove the spaces and "-" from each name

4.We need to read the activites lables stored in the activity_labels.txt file and assigned to the activities vector. Also, we need to remove the undersocre and make set all activies lables lowercase. 

5. We need to subset the Info data frame based on the features vector defined above and called it Info_subset

6. We need to add to the Info_subset the subjects and the activity label data and saved under the "merged_data.txt" name
  
7. We need to generate an independent tidy data set called "data_with_means.txt" file with the average of each measurement for each activity and each subject. 


Notes:
======
- 
Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

For more information about this dataset contact: activityrecognition@smartlab.ws
