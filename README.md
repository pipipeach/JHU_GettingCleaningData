*This Github repository contains the required scripts and this readme [README.md](https://github.com/lindangulopez/JHU_GettingCleaningData/edit/master/README.md) file, 
necessary for creating a tidy data set for an android sensor motion and posture study, as per the [getting-and-cleaning-data-course-project's](https://www.coursera.org/learn/data-cleaning/home/welcome) specifications, it is one of four files for the assignment submission.*

# The Johns Hopkins University Getting and Cleaning Data Course is the third course in the [Data Science Specialization](https://www.coursera.org/specializations/jhu-data-science). 

It builds on:
- Course 1: [The Data Scientist's Toolbox](https://www.coursera.org/learn/data-scientists-tools?specialization=jhu-data-science) 
In this course you will get an introduction to the main tools and ideas in the data scientist's toolbox, it gives an overview of 
the data, questions, and tools that data analysts and data scientists work with. There are two components to this course. The first 
is a conceptual introduction to the ideas behind turning data into actionable knowledge. The second is a practical introduction to 
the tools that will be used in the program like version control, markdown, git, GitHub, R, and RStudio.

- Course 2: [R Programming](https://www.coursera.org/learn/r-programming?specialization=jhu-data-science). Will teach you to program 
in R and how to use R for effective data analysis. You will learn how to install and configure software necessary for a statistical 
programming environment and describe generic programming language concepts as they are implemented in a high-level statistical language 
and get practical skills in statistical computing which includes programming in R, reading data into R, accessing R packages, writing 
R functions, debugging, profiling R code, and organizing and commenting R code. Topics in statistical data analysis will provide 
working examples.


## About the Getting and Cleaning Data: 
- It is taught by Jeff Leek, Brian Caffo and Roger D. Peng who are Professors from the [Johns Hopkins School of Public Health](http://www.jhsph.edu/)
- you wil learn how to obtain data from the web, from APIs, from databases and from colleagues in various formats. The main aim was to understand 
the basics of data cleaning and how to make data “tidy”. Tidy data dramatically speeds up downstream data analysis tasks as well as the components 
of a complete data set including raw data, processing instructions, codebooks, and processed data, and is the focus of this:

# The final course assignment, is shared in this repository.


## caseSTUDY: 
- An "Activities of Daily Living", ADL, study gathered Android motion and posture sensors data as two data sets, a test and a train set, see data 
description below.

## mainOUTPUT: 
- A tidy csv dataset, "HAR-subject_activity_mean.txt", was prepared for future analysis, for the ADL study.

## keySTEPS:
-The multiple text files were converted into one dataset with headers, with logical English names, that is with activity descriptions rather than 
numeric codes. The test and train datasets were combined in the resuting tidy dataset,  "HAR-subject_activity_mean.txt"

# Tidy Assignment Project Files:
- a code book [CodeBook.md](https://github.com/lindangulopez/JHU_GettingCleaningData/blob/master/CodeBook.md) which lists the variables of the tidy data set.
- there is R script [run_analysis.R](https://github.com/lindangulopez/JHU_GettingCleaningData/blob/master/run_analysis.R) which transforms the given data to a tidy data set.
- and the tidy data [HAR-subject-activity-mean.txt](https://github.com/lindangulopez/JHU_GettingCleaningData/blob/master/HAR-subject-activity-mean.txt) which is produced as an output from the R script.

### Other Files: 
- Tidy data as a csv file [HAR-subject-activity-mean.csv](https://github.com/lindangulopez/JHU_GettingCleaningData/blob/master/HAR-subject-activity-mean.csv) which is easy on the eyes and useful for quick data analysis with csv tools.
- The Code Book as a web document, a metadata file for statisticians as the [codebook_tidydf](https://raw.githubusercontent.com/lindangulopez/JHU_GettingCleaningData/master/codebook_tidydf.html).

**If you run into any problem feel free to contact me:@lindangulopez**

### You must:   
- Make sure that the dplyr package and library(data.table) and library(reshape2) are installed, before running the script. 
- Please download & source the file "run_analysis.R" from this repository.
- You must set your directory on the abovementioned R script, before you run it.


***Please see the detailed project description below, to find out how to install the necessary packages and set your directory.***

### The R Script will run these steps: 
- Step 1. It will get this [data](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

- Step 2. It will unzip the folder in your working directory, you will see these files:
  * activity_labels.txt
  * features.txt
  * subjects_train.txt
  * X_test.txt
  * y_test.txt
  * subjects_train.txt
  * X_train.txt
  * y_train.txt
  
- Step 3. The script will carry out a step wise transformation to tidy the given data, see details below.
  
- Step 4. When done it will generate a csv file, "HAR-subject-activity-mean.txt", the tidy dataset.

# Results
- A dataframe containing the tidy data set, as defined in CodeBook.md, is returned. The same data set is also saved as a csv format file, named
"HAR-subject_activity_mean.txt", to the working directory.

- What's next:
[exploratory-data-analysis](https://www.coursera.org/learn/exploratory-data-analysis?specialization=jhu-data-science); 
[reproducible-research](https://www.coursera.org/learn/reproducible-research); 
[statistical-inference](https://www.coursera.org/learn/statistical-inference); 
[regression-models](https://www.coursera.org/learn/regression-models)
[practical-machine-learning](https://www.coursera.org/learn/practical-machine-learning); [data-products](https://www.coursera.org/learn/data-products); 
[data-science-project](https://www.coursera.org/learn/data-science-project).


#### Detailed Project Description: 

- Goal: get Android motion and posture sensors data ready for analysis

- Created tidy data with [dplyr](https://dplyr.tidyverse.org/), see [data-transformation-cheatsheet-thumbs](https://github.com/rstudio/cheatsheets/blob/master/data-transformation.pdf).

- About the Data: 
A Human Activity Recognition database was built from the recordings of 30 subjects performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors.The data was collected from Samsung Galaxy S accelerometer's [motion & position sensors](https://www.mobileprocessing.org/sensors.html). 

The experiments were carried out with a group of volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing the smartphone on their waist. 

Using its embedded accelerometer and gyroscope, the scientists captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments were video-recorded to label the data manually. 

The obtained dataset was randomly partitioned into two sets, (i) 70% of the volunteers were selected for generating the training data, (ii)  30% of the volunteers were selected for the test data.

- A Code book was created with the DataMaid Library
- Function call: `dataMaid::makeDataReport(data = tidydf, mode = c("summarize", "visualize", "check"), smartNum = FALSE, file = "codebook_tidydf.Rmd", checks = list(character = "showAllFactorLevels", factor = "showAllFactorLevels", labelled = "showAllFactorLevels", haven_labelled = "showAllFactorLevels", numeric = NULL, integer = NULL, logical = NULL, Date = NULL), listChecks = FALSE, maxProbVals = Inf, codebook = TRUE, reportTitle = "Codebook for tidydf
- then edited and saved as CodeBook.md


- Full Instructions, please follow Steps: 

STEP 1: First setup the ecosystem of packages to work with tidy data dplyr, a part of the tidyverse, in R,  must be installed for the script to run. 
The easiest way to get dplyr is to install the whole tidyverse:install.packages("tidyverse")
Alternatively, install just dplyr:install.packages("dplyr")
dplyr is a grammar of data manipulation, providing a consistent set of verbs that help you solve the most common data manipulation challenges:

STEP 2: Download "run_analysis.R", source the script "run_analysis.R", in R or RStudio , edit the **data.dir = path.expand("~/to/your/directory")**
- Now you can run the script it will, download and unzip the [unzipped folder](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) in your working directory by running the R script.


STEP 3: The script, "run_analysis.R", will also open the the "run_analysis.R" file into the working directory. Santity check: you should have the following files in your working directory, if not edit the line the **data.dir = path.expand("~/to/your/directory"): **
- /train/X_train.txt
- /test/X_test.txt
- features.txt
- /test/y_test.txt
- /train/y_train.txt
- /test/subject_test.txt
- /train/subject_train.txt

- The R script will perform the following step wise transformation, format the feature list with clear variable names, rename the columns of both data frames, subset the dataset, to keep only columns with mean and standard deviation, merge the test and train data frames, with the dplyr package.

STEP 4:The merged data frame by subject and activity and written to a tidy dataset, "HAR-subject-activity-mean.txt", saved in the working directory.**

**YOUR TIDY DATA SET READY FOR ANALYSIS**

- you can work with it as it is or 
- save it as a csv file.

If you run into any problem feel free to contact me:@lindangulopez







