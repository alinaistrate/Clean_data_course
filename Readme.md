

# Getting and Cleaning Data Course Project

This repository hosts the R code and documentation files for the Data Science's track course "Getting and Cleaning data", available in coursera.

## Files

`CodeBook.md`  gives a basic description of the data set as well as the transformations performed to clean up the data.

`run_analysis.R` contains all the code to perform the analyses described in the 5 steps. They can be launched in RStudio by just importing the file.

The equirements of the project were:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Each step is explained in the comment lines in `run_analysis.R`

The output of the 5th step is called `tidy.csv`, and uploaded in the course project's form.
