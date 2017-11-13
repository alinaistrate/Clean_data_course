

```r
## STEP 0: load required packages
library(reshape2)

#Download and unzip the data 

if(!file.exists("./set_data")){dir.create("./set_data")
        fileUrl <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
        download.file(fileUrl,destfile="./set_data/Dataset.zip")
        unzip(zipfile="./set_data/Dataset.zip",exdir="./set_data")
}

## STEP 1: Merges the training and the test sets to create one data set

# read data into data frames
subject_train <- read.table("./set_data/UCI HAR Dataset/train/subject_train.txt")
subject_test <- read.table("./set_data/UCI HAR Dataset/test/subject_test.txt")

X_train <- read.table("./set_data/UCI HAR Dataset/train/X_train.txt")
X_test <- read.table("./set_data/UCI HAR Dataset/test/X_test.txt")

y_train <- read.table("./set_data/UCI HAR Dataset/train/y_train.txt")
y_test <- read.table("./set_data/UCI HAR Dataset/test/y_test.txt")

# add column name for subject files
names(subject_train) <- "subjectID"
names(subject_test) <- "subjectID"

# add column names for measurement files
featureNames <- read.table("./set_data/UCI HAR Dataset/features.txt")
names(X_train) <- featureNames$V2
names(X_test) <- featureNames$V2

# add column name for label files
names(y_train) <- "activity"
names(y_test) <- "activity"

# combine files into one dataset
train <- cbind(subject_train, y_train, X_train)
test <- cbind(subject_test, y_test, X_test)
combined <- rbind(train, test)


## STEP 2: Extracts only the measurements on the mean and standard
## deviation for each measurement.

# determine which columns contain "mean()" or "std()"
meanstdcols <- grepl("mean\\(\\)", names(combined)) | grepl("std\\(\\)", names(combined))

#  keep also  the subjectID and activity columns
meanstdcols[1:2] <- TRUE

# remove unnecessary columns
combined <- combined[, meanstdcols]


## STEP 3: Uses descriptive activity names to name the activities
## in the data set.
## STEP 4: Appropriately labels the data set with descriptive
## activity names. 

# convert the activity column from integer to factor
combined$activity <- factor(combined$activity, 
                 labels=c("Walking","Walking Upstairs", "Walking Downstairs", "Sitting", "Standing", "Laying"))


## STEP 5: Creates a second, independent tidy data set with the
## average of each variable for each activity and each subject.

# create the tidy data set
melted <- melt(combined, id=c("subjectID","activity"))
tidy <- dcast(melted, subjectID+activity ~ variable, mean)

# write the tidy data set to a file
write.csv(tidy, "tidy.csv", row.names=FALSE)
```


---
title: "run_analysis.R"
author: "alina"
date: "Sun Nov 12 21:29:37 2017"
---