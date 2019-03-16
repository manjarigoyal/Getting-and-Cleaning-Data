1. The run_analysis.R script performs the data preparation and then followed by the following steps.

2. Download the dataset and extracted under the folder called UCI HAR Dataset.

3. Assign each data to following variables:

    features <- features.txt :                                                                                                                                                 
    activities <- activity_labels.txt : List of activities performed when the corresponding measurements were taken and its codes                                                                                                              
    subject_test <- test/subject_test.txt : contains test data of 9/30 volunteer test subjects being observed                                                                                                                               
    x_test <- test/X_test.txt : contains recorded features test data                  
    y_test <- test/y_test.txt : contains test data of activities’code labels                                  
    subject_train <- test/subject_train.txt : contains train data of 21/30 volunteer subjects being observed                          
    x_train <- test/X_train.txt : contains recorded features train data                                 
    y_train <- test/y_train.txt : contains train data of activities’code labels                                         

4. Merges both datasets to create one dataset:                                                                                                                                     
  X is created by merging x_train and x_test using rbind() function                                       
  Y is created by merging y_train and y_test using rbind() function                                               
  Subject is created by merging subject_train and subject_test using rbind() function                                     
  Merged_Data is created by merging Subject, Y and X using cbind() function                                                   

5. Extracts only the measurements on the mean and standard deviation for each measurement                                   
  TidyData is created by subsetting Merged_Data, selecting the following columns:                                               
      a. subject                                                                                        
      b. code                                                                                           
      c. the measurements on the mean and standard deviation (std) for each measurement                                                     

6. Label the data set with descriptive variable names and code column in TidyData renamed into activities                           
      a. All Acc in column’s name replaced by Accelerometer                                                                                           
      b. All Gyro in column’s name replaced by Gyroscope                                                                                                
      c. All BodyBody in column’s name replaced by Body                                         
      d. All Mag in column’s name replaced by Magnitude                                     
      e. All start with character f in column’s name replaced by Frequency                                        
      f. All start with character t in column’s name replaced by Time                                           

7. FinalData is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
8. Export FinalData into FinalData.txt file.                                                                                                                                                                                                     
