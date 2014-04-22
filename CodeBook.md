##Description of datasets and code

#Code (run_analysis.R)

This code downloads initial .zip file to a default working directory and unzips it to the directory 'project' placed within a working directory.

The code uses 'plyr' package for some computations. It checks automaticallty whether the package is installed or not. If not, 'plyr' package is installed.

The code then compiles a required tidy dataset from test and training datasets and writes it to a file 'entireset_mean_sd.csv' (see description below).

Finally, the code creates a reduced dataset with feature-specific mean values for each subject and activity. Resulting dataset is written to a file 'reducedset_mean_sd.csv' (see decsription below).

It takes some time to execute the code, especially regarding downloading a .zip archive (depends on speed of your internet conection) and reading initial test and training datasets (c. 1min each on a 8GB RAM coreI5 machine).

#Tidy dataset (entireset_mean_sd.csv)

First two columns of this dataset explicitly describe a type of activity and subject tested for each observation (row). Subsequent 66 columns report mean and sd measures for each observation. Column names correspond to those described in 'features_info.txt' file found in './project/UCI HAR Dataset' directory.

Dataset is not sorted and test set is simply placed below training set row-wise.

#'Small' tidy dataset (reducedset_mean_sd.csv)

This dataset is created using a tidy dataset described above. It averages all observations corresponding to a specific subject and activity type for every feature. Rows represent features, row names (again) correspond to those described in 'features_info.txt' file. Columns represent a 'subject-activity' pair and are explicitly named as '<SUBJECT>.<ACTIVITY>'.
