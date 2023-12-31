# CleaningDataCourseProject

## The original data
The original data set is obtained from the Human Activity Recognition Using Smartphones Data Set in UCI Machine Learning Repository. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. This kind of data coming from wearable computing is used by companies like Fitbit, Nike, and Jawbone Up racing to develop the most advanced algorithms to attract new users. A full description is available at the site where the data was obtained:
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The data for the project are in the following zip file :
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
When unzipped they are included in the working directory, in the folder "UCI HAR Dataset". 
The details of the files included in the zipped file are available in the CodeBook, based on the file features.txt which has been made usin. This folder comprises two more folders named "train" and "test" where the data to be used for the analysis are incuded. These folders include also a folder called "Inertial Signals" which is not included in the dataset.


The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:
======================================

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

## Processing
I created the script "run_analysis.R" which does the following:
1. It merges the training and the test sets to create one data set. The files used are txt files in the unzipped directories "train" and "test" with names starting with "subject_" with subject IDs, "X_" with measurements and "y_" with labels. They are read seperately and then bound together for "test" and "train" and finally bound together to form "alldata".

2. It extracts only the columns that include the measurements on the mean and standard deviation for each measurement, together with the key columns presenting the subject ID and the Activity. The columns extracted are those having the terms mean() or std() in the name of the variable.

3. Uses descriptive activity names to name the activities in the data set.

4. Appropriately labels the data set with descriptive variable names. The replacement uses the structure of the variable names.

5. From the data set in step 4, it creates a second, independent tidy data set with the average of each variable for each activity and each subject.

## Files submitted
The following files have been included in this repo: 
1) the script "run_analysis.R" 
2) a code book "CodeBook.MD" that describes the variables, the data, and 
3) the tidy data set "tidyData.txt" produced by the script as indicated below, 
4) the present "README.md" file



Notes: 
======
- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

For more information about this dataset contact: activityrecognition@smartlab.ws

License:
========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.
