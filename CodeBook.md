# CodeBook for the tidy dataset


## Data source

This dataset is derived from the "Human Activity Recognition Using Smartphones Data Set"  available here: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones


## Experiment description

Note: This section is taken  from the Readme.txt  file of the original dataset

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details.

For each record it is provided:


- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope.
- A 561-feature vector with time and frequency domain variables.
- Its activity label.
- An identifier of the subject who carried out the experiment.


## Structure of Data

The dataset includes the following files:


- 'README.txt'

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

### Notes:

- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.


## Variables

Variables within the tidy data set are as examined as follows (taken from [1]).

The activity labels consist of WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING

The subjects who carried out the experiment are represented as a number from 1 to 30.

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals).

Signals were used to estimate variables of the feature vector for each pattern: [XYZ] is used to denote 3-axial signals in the X, Y and Z directions.

For each measurement the mean, stddev, and mean frequency were calculated.

SubjectID, Class_Name, tBodyAcc_mean_X, tBodyAcc_mean_Y, tBodyAcc_mean_Z, tBodyAcc_std_X, tBodyAcc_std_Y, tBodyAcc_std_Z, tGravityAcc_mean_X, tGravityAcc_mean_Y, tGravityAcc_mean_Z, tGravityAcc_std_X, tGravityAcc_std_Y, tGravityAcc_std_Z, tBodyAccJerk_mean_X, tBodyAccJerk_mean_Y, tBodyAccJerk_mean_Z, tBodyAccJerk_std_X, tBodyAccJerk_std_Y, tBodyAccJerk_std_Z, tBodyGyro_mean_X, tBodyGyro_mean_Y, tBodyGyro_mean_Z, tBodyGyro_std_X, tBodyGyro_std_Y, tBodyGyro_std_Z, tBodyGyroJerk_mean_X, tBodyGyroJerk_mean_Y, tBodyGyroJerk_mean_Z, tBodyGyroJerk_std_X, tBodyGyroJerk_std_Y, tBodyGyroJerk_std_Z, tBodyAccMag_mean, tBodyAccMag_std, tGravityAccMag_mean, tGravityAccMag_std, tBodyAccJerkMag_mean, tBodyAccJerkMag_std, tBodyGyroMag_mean, tBodyGyroMag_std, tBodyGyroJerkMag_mean, tBodyGyroJerkMag_std, fBodyAcc_mean_X, fBodyAcc_mean_Y, fBodyAcc_mean_Z, fBodyAcc_std_X, fBodyAcc_std_Y, fBodyAcc_std_Z, fBodyAcc_meanFreq_X, fBodyAcc_meanFreq_Y, fBodyAcc_meanFreq_Z, fBodyAccJerk_mean_X, fBodyAccJerk_mean_Y, fBodyAccJerk_mean_Z, fBodyAccJerk_std_X, fBodyAccJerk_std_Y, fBodyAccJerk_std_Z, fBodyAccJerk_meanFreq_X, fBodyAccJerk_meanFreq_Y, fBodyAccJerk_meanFreq_Z, fBodyGyro_mean_X, fBodyGyro_mean_Y, fBodyGyro_mean_Z, fBodyGyro_std_X, fBodyGyro_std_Y, fBodyGyro_std_Z, fBodyGyro_meanFreq_X, fBodyGyro_meanFreq_Y, fBodyGyro_meanFreq_Z, fBodyAccMag_mean, fBodyAccMag_std, fBodyAccMag_meanFreq, fBodyBodyAccJerkMag_mean, fBodyBodyAccJerkMag_std, fBodyBodyAccJerkMag_meanFreq, fBodyBodyGyroMag_mean, fBodyBodyGyroMag_std, fBodyBodyGyroMag_meanFreq, fBodyBodyGyroJerkMag_mean, fBodyBodyGyroJerkMag_std, fBodyBodyGyroJerkMag_meanFreq




Details about Files to be used in analysis from Source Data

Common Files - features.txt: 561 rows of 2 varibles (feature Identifier and feature Name) -  activity_labels.txt: 6 rows of 2 variables (activity identifier and activity name)

Test Dataset - xTest.txt: 2947 rows of 561 measurement variables. These are measurement variables listed in features.txt - yTest.txt: 2947 rows of 1 variables. This is the activity Identifier -  subjectTest.txt: 2497 rows of 1 variable (subject Identifier)

Training Dataset - xTrain.txt: 7352 rows of 561 measurement variables. These are measurement variables listed in features.txt - yTrain.txt: 7352 rows of 1 variables. This is the activity Identifier - subjectTrain.txt: 7352 rows of 1 variable (subject Identifier)

## Map of aggregated Data

Variable Names	subjectId	activityId	(variable names from features.txt)
Data	subjectTest.txt	yTest.txt	xTest.txt
Data	subjectTrain.txt	yTrain.txt	xTrain.txt
Requirements & Details of Transformations through run_analysis.R script

## Requirements

run_analysis.R script has the following requirements to perform transformation on UCI HAR Dataset.

Merges the training and the test sets to create one data set.
Extracts only the measurements on the mean and standard deviation for each measurement.
Uses descriptive activity names to name the activities in the data set
Appropriately labels the data set with descriptive activity names.
Creates a second, independent tidy data set with the average of each variable for each activity and each subject.
Detailed Functions of run_analysis.R Script

Downloads the dataset from the URL mentioned above and unzips it to create UCI HAR Dataset folder
Imports "test" and "train" datsets and creates data frames from then and then Merges the training and the test sets
to create one data frame.
Extracts a subset of data with only the measurements on the mean "mean()" and standard deviation "std()" for each measurement. Also excludes meanFreq()-X measurements or angle measurements where the term mean exists resulting in
66 measurement variables.
Updates the variable names in dataframe variable names for data fame to improve readibility
Appropriately labels the data set with descriptive activity names in place of activity Ids
Reshapes dataset to create a data frame with average of each measurement variable for each activity and each subject
Writes new tidy data frame to a text file to create the required tidy data set file of 180 observations and 68 columns (2 columns for activityName and subjectID and 66 columns for measurement variables)
Transformations Performed on the original dataset.

Merging the training and the test sets to create one data set.




## Transformations

Training and test data set rows were appended and then a unified data set created from the source files.

Measurements were extracted for mean, standard deviation for each measurement.

variable/column names were labeled with descriptive cleaner names.

Results were output as an independent tidy data set at ./data/TidyDataSet.txt
