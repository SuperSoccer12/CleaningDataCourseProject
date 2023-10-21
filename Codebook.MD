## Data <a name="data"></a>

The `TidyData.txt` data file is a text file, containing space-separated values.

The first row contains the names of the variables, which are listed and described in the [Variables](#variables) section, and the following rows contain the values of these variables. 


## Variables <a name="variables"></a>

Each row contains 79 averaged signal measurements grouped by subject and activity.

## Transformations <a name="transformations"></a>

The following transformations were applied to the source data:

- 1. The training and test sets were merged to create one data set.
- 2. The measurements on the mean and standard deviation (i.e. signals containing the strings `mean` and `std`) were extracted for each measurement, and the others were discarded.
- 3. The activity identifiers (originally coded as integers between 1 and 6) were replaced with descriptive activity names.
- 4. The variable names were replaced with descriptive variable names, using the following set of rules:
	- Special characters (i.e. `(`, `)`, and `-`) were removed
	- The initial `f` and `t` were expanded to `Frequency` and `Domain` respectively.
	- `Acc`, `Gyro`, `Mag`, `Freq`, `mean`, and `std` were replaced with `Accelerometer`, `Gyroscope`, `Magnitude`, `Frequency`, `Mean`, and `StandardDeviation` respectively.
	- Replaced (supposedly incorrect as per source's `features_info.txt` file) `BodyBody` with `Body`.
- 5. From the data set in step 4, the final data set was created with the average of each variable for each activity and each subject.

The collection of the source data and the transformations listed above were implemented by the `run_analysis.R` R script (see `README.md` file for usage instructions)
